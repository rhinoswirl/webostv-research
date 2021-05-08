# services.d

**Type:** Directory

**Location(s):**

```
/var/luna-service2/
/var/luna-service2-dev/
/usr/share/luna-service2/
```

**Description:**

Contains JSON files related with [D-Bus](https://en.wikipedia.org/wiki/D-Bus) service definition.

Contents of `/var/luna-service2-dev/services.d/org.webosbrew.hbchannel.service.service`:


```
[D-BUS Service]
Name=org.webosbrew.hbchannel.service
Exec=/media/developer/apps/usr/palm/services/org.webosbrew.hbchannel.service/run-js-service -n /media/developer/apps/usr/palm/services/org.webosbrew.hbchannel.service
Type=dynamic
```

**Note:** 

In all services, the `run-js-service` executable is executed from `/usr/bin/run-js-service`. This is the default behaviour in webOS.

Here the contents were modified for running a different executable related with the Homebrew channel project.