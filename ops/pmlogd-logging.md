# Increase pmlogd logging

> This doesn't work anymore on newer webos/pmlogd versions

By default pmlogdaemon logs only topics listed in /etc/PmLogDaemon/whitelist.txt.

To enable all logging use:

```sh
luna-send -n 1 -f 'luna://com.webos.pmlogd/setdevlogstatus' '{"recordDevLogs":false}'
luna-send -n 1 -f 'luna://com.webos.pmlogd/getdevlogstatus' '{}'
```

After enabling all devlogs specific contexts can be adjusted using PmLogCtl.

(note: you most probably want to disable rdxd first, as per rootmytv immutable mounts...)