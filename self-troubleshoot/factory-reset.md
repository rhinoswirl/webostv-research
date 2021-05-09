# Factory Reset / First Start

Did your TV just opened the first use app by itself after some changes you've made? It happened to me after making some changes to the filesystem while doing my research.

The TV checks if it is properly initialized by checking if `/var/luna/preferences/ran-firstuse` exists.

If that file does not exist, the TV will display the First-Time Setup screen.

There are several situations on how this can happen, the most common being the user clicking the factory reset option in settings.

However, the TV may send you back to this screen after a boot if the following situations occurr:

- Lack of space for the db8 maindb 
- db8 maindb is corrupted or luna is not running

The database is checked by `/etc/init/db8-maindb.conf`.

## Lack of space for the db8 maindb

If during initialization, `/var/db` contain less 4.5% of free space, the system will perform a factory reset and reboot by executing the following commands (in `/usr/lib/db8/bin/errorNoSpace.bash`):

```
mkdir -p /mnt/lg/cmn_data/db8 || true
touch /mnt/lg/cmn_data/db8/errorNoSpace || true
rm -f /var/luna/preferences/ran-firstuse || true
rm -rf /var/db/main/* || true
sync

PmLogCtl log DB8 crit "mojodb-luna [] DB8 DBGMSG {} [upstart_maindb] No space left for maindb"
/usr/bin/luna-send -n 1 luna://com.webos.service.tv.systemproperty/doUserDefault '{}'
```

Upon rebooting, you will see the getting started screen.

## Currepted db8 maindb database (or luna bus not running)

Upon booting, the system tries to check the health status of the `maindb` (`/usr/bin/check_settings_db_health.py`).

For this, it calls `luna://com.webos.settingsservice/getSystemSettings` to check for the country and locale settings.

If the process does not return correct information, the system will assume that the database is corrupted (even though this can also just be a problem in luna-bus not working correctly, as was my case).

Upon this failure, it will create the `/mnt/lg/cmn_data/settingsservice/factory_reset` file and run `/usr/lib/db8/bin/errorOpenMainDb.bash`.

This script will perform the following operations:

1. Make a database (`/var/db/main`) backup to `/mnt/lg/cmn_data/db8/corrupted_maindb.tar.bz2` if there is enough free space.
2. Delete `var/db/main`.
3. Delete `/var/luna/preferences/ran-firstuse`
4. Call `/usr/bin/luna-send -n 1 luna://com.webos.service.tv.systemproperty/doUserDefault '{}'`.

If ls-hubd (luna) is dead for some reason, this will actually create some weird inconsistent results, as the execution of `luna://com.webos.service.tv.systemproperty/doUserDefault` will not be possible. See notes below.


## Notes

In my case, I was faced with a weird behavior where ls-hubd was crashing during startup. Because of that, the database check failed upon starting the TV and so it triggered the behaviour for reparing a corrupted database.

Because luna was not running, the TV couldn't run `luna://com.webos.service.tv.systemproperty/doUserDefault` and thus I ended up with a system in an inconsistent state, where I had to run the first time setup, but could quit and all my apps and options were still there.

In this state, some of my apps are not working properly:

- I can't connect my smartphone to the TV; it always gives me the following error in my phone: "There is a problem with the PIN input field of TV. Please try again.".
- When I try to cast something to YouTube, the app itself does not open and I need to open it manually. Upon doing so, I always get a prompt to send an error report to Google.

This leads me to believe that something is not setted up properly, but I am not sure what.
