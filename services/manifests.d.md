# manifests.d

**Type:** Directory

**Location(s):**

```
/var/luna-service2/
/var/luna-service2-dev/
/usr/share/luna-service2/
```

**Description:**

Contains JSON files related with an app's manifest.

Contents of `/var/luna-service2-dev/manifests.d/org.webosbrew.hbchannel.json` (formatted):

> **Warning:** the contents of this file may have been changed and not reflect the original status of the hbchannel after a clean install!

```json
{
	"id": "org.webosbrew.hbchannel",
	"serviceFiles": ["/var/luna-service2-dev/services.d/org.webosbrew.hbchannel.service.service"],
	"roleFiles": ["/var/luna-service2-dev/roles.d/org.webosbrew.hbchannel.service.service.json", "/var/luna-service2-dev/roles.d/org.webosbrew.hbchannel.app.json"],
	"apiPermissionFiles": ["/var/luna-service2-dev/api-permissions.d/org.webosbrew.hbchannel.service.api.json"],
	"version": "0.0.1",
	"clientPermissionFiles": ["/var/luna-service2-dev/client-permissions.d/org.webosbrew.hbchannel.service.service.json", "/var/luna-service2-dev/client-permissions.d/org.webosbrew.hbchannel.app.json"]
}
```
