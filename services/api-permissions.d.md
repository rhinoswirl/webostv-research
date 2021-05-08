# client-permissions.d

**Type:** Directory

**Location(s):**

```
/var/luna-service2/
/var/luna-service2-dev/
/usr/share/luna-service2/
```

**Description:**

Contains several JSON files related with permissions of the service.

I am not sure on the exact meaning of them.

Contents of `/var/luna-service2-dev/api-permissions.d/org.webosbrew.hbchannel.service.api.json` (formatted):

> **Warning:** the contents of this file may have been changed and not reflect the original status of the hbchannel.service after a clean install!


```json
{
	"org.webosbrew.hbchannel.service.group": ["org.webosbrew.hbchannel.service/*"],
	"ares.webos.cli": ["org.webosbrew.hbchannel.service/*"]
}
```


Contents of `/var/luna-service2/api-permissions.d/com.palmdts.devmode.service.api.json` (formatted):

```json
{
    "com.palmdts.devmode.service.group": ["com.palmdts.devmode.service/*"]
}
```

Contents of `/usr/share/luna-service2/api-permissions.dls2-internal.api.json`:

```json
{
  "private": [
    "*/com/palm/luna/private/*"
  ],
  "public": [
    "*/com/palm/luna/private/ping",
    "*/com/palm/luna/private/cancel"
  ]
}
```

## Notes

- Why is hbchannel registered here but not any of my other homebrew apps? Was it related with any of the changes I've made in `client-permissions.d`?
- The only service in `/var/luna-service2/api-permissions.d/` is the devmode. Shouldn't there be other apps here?