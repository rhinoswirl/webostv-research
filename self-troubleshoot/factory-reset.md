# Factory Reset / First Start

The TV is "kinda" able to self troubleshoot itself and trigger a factory reset when certain conditions are met.

The TV will display the First-Time Setup screen if if `/var/luna/preferences/ran-firstuse` does not exists.

There are several situations that can lead to the absense of `/var/luna/preferences/ran-firstuse`, the most common being the user clicking the factory reset option in settings.

However, the TV may send you back to this screen after a boot if the following situations occurr:

- Lack of space for the db8 maindb 
- db8 maindb is corrupted
- ls-hubd not running on startup

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

## Corrupted db8 maindb database

Upon booting, the system tries to check the health status of the `maindb` (`/usr/bin/check_settings_db_health.py`).

For this, it calls `luna://com.webos.settingsservice/getSystemSettings` to check for the country and locale settings.

If the process does not return correct information, the system will assume that the database is corrupted.

Upon this failure, it will create the `/mnt/lg/cmn_data/settingsservice/factory_reset` file and run `/usr/lib/db8/bin/errorOpenMainDb.bash`.

This script will perform the following operations:

1. Make a database (`/var/db/main`) backup to `/mnt/lg/cmn_data/db8/corrupted_maindb.tar.bz2` if there is enough free space.
2. Delete `var/db/main`.
3. Delete `/var/luna/preferences/ran-firstuse`
4. Call `/usr/bin/luna-send -n 1 luna://com.webos.service.tv.systemproperty/doUserDefault '{}'`.


## ls-hubd not running on startup

If `ls-hubd` is not running on startup, the TV will still check for the status of the `maindb`. However, because checking for the status of the database requires calling `luna://com.webos.settingsservice/getSystemSettings` and `ls-hubd` is dead, it will fail and trigger the factory reset procedure as if maindb was corrupted.

Because `ls-hubd` is dead, this will actually create some weird inconsistent results, as the execution of `luna://com.webos.service.tv.systemproperty/doUserDefault` will not be possible.

This will send you to the first time setup screen upon next reboot, but you may experience some issues such as the difficulty of selecting locale settings if `ls-hubd` is not running.

Assuming that you can finish the setup, your database will now be in a clean state, but all your app preferences will still be on the TV. As a result, you may experience the following issues:

- Unable to connect to Second-Screen App. The phone will display a message similar to: "There is a problem with the PIN input field of TV. Please try again.".
- Some services will not work properly (because they are not registered in maindb?)
    - Homebrew channel service will never create an activity
    - The YouTube Mobile app will recognize the TV as "YouTube on TV" instead of using the TV's model number
    - YouTube will not open automatically when a cast session is started and when opened manually will prompt to send an error report to Google.
