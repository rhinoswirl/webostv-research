# roles.d

**Type:** Directory

**Location(s):**

```
/var/luna-service2/
/var/luna-service2-dev/
/usr/share/luna-service2/
```

**Description:**

Contains JSON files related with app and service roles.

Contents of `/var/luna-service2-dev/roles.d/org.webosbrew.hbchannel.app.json` (formatted):


```json
{
	"appId": "org.webosbrew.hbchannel",
	"type": "regular",
	"allowedNames": ["org.webosbrew.hbchannel-*"],
	"permissions": [
		{
			"service":"org.webosbrew.hbchannel-*",
			"outbound":["*"]
		}
	]
}
```


Contents of `/var/luna-service2-dev/roles.d/org.webosbrew.hbchannel.service.json` (formatted):


```json
{
	"appId": "org.webosbrew.hbchannel.service",
	"type": "regular",
	"allowedNames": ["org.webosbrew.hbchannel.service"],
	"permissions": [
		{
			"service":"org.webosbrew.hbchannel.service",
			"outbound":["*"]
		}
	]
}
```
