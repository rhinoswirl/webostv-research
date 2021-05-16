# Increase pmlogd logging

pmlogDaemon logs only topics and events of those topics listed in `/etc/PmLogDaemon/whitelist.txt`.

Its configuration can be managed in `/etc/pmlog.d/`.

[I am not sure if all events are sent to this logger. I think that, for example, `console.log`s are not logged here.]

In old versions of webOS (how old?) and in non-prod builds of pmlogDaemon it is possible to change the behaviour of pmlogd to enabling logging of all logs by running the following commands.

```sh
luna-send -n 1 -f 'luna://com.webos.pmlogd/setdevlogstatus' '{"recordDevLogs":false}'
luna-send -n 1 -f 'luna://com.webos.pmlogd/getdevlogstatus' '{}'
```

In newer versions, that is no longer possible ([source](https://github.com/openwebos/pmlogdaemon/commit/7c1ddcbbcfde9f81dec87a635e251540556710b6)) and the logging needs to be predent in the whitelist file.

The whitelist consists on a set of items in the format `<context> <msg_id>` with no leading or trailing white space, and a single space between them, such as:

```
com.palm.app.settings TIMEZONE_CHANGED
AppInstallD APP_INSTALLED
com.webos.app.livetv LIVE_MENU
```

You can find applications logging events by searching for strings such as:

```
printNormalLog("NL_MENU_CLICK", {"menu_name": "add"});
```

The whitelist can be updated by rebooting the TV or calling `luna-send -n 1 luna://com.webos.pmlogd/enableNewWhitelist '{}'`.

## Preventing logs from being sent to LG

pmlogd will log the events listed in the whitelist to `/var/log/messages`.

These and other logs will periodically be sent to LG unless the following directories are mounted as unwritable:

```
/var/spool/rdxd/
/var/spool/uploadd/pending/
/var/spool/uploadd/uploaded/
```

If you use RootMy.Tv `start-devmode.sh` script, the immutable mounts are already done.

However, because the system may try to move some of the log files to these locations, it is possible that some of the logs may be lost.
