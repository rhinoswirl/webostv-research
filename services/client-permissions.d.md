# client-permissions.d

**Type:** Directory

**Location(s):**

```
/var/luna-service2/
/var/luna-service2-dev/
/usr/share/luna-service2/
```

**Description:**

Contains several JSON files related with permissions of services and apps.

Contents of `/var/luna-service2-dev/client-permissions.d/org.webosbrew.hbchannel.app.json` (formatted):

> **Warning:** the contents of this file may have been changed and not reflect the original status of the hbchannel.service after a clean install!


```json
{
  "org.webosbrew.hbchannel-*": ["public", "org.webosbrew.hbchannel.service.group"]
}
```


Contents of `/var/luna-service2-dev/client-permissions.d/org.webosbrew.hbchannel.service.service.json` (formatted):

> **Warning:** the contents of this file may have been changed and not reflect the original status of the hbchannel.service after a clean install!


```json
{
  "org.webosbrew.hbchannel.service*": ["public"]
}
```




Contents of `/var/luna-service2/client-permissions.d/com.palmdts.devmode.app.json` (formatted):

```json
{
  "com.palmdts.devmode-*": ["public", "com.palmdts.devmode.service.group"]
}
```


Contents of `/var/luna-service2/client-permissions.d/com.palmdts.devmode.service.json` (formatted):

```json
{
  "com.palmdts.devmode.service*": ["public"]
}
```

Contents of `/usr/share/luna-service2/client-permissions.d/luna-service2.perm.json`:

```json
{
  "*": ["luna.internal.public"],
  "com.webos.monitor*": ["luna.internal"],
  "com.webos.lunasend-*": ["all"]
}
```

Contents of `/usr/share/luna-service2/client-permissions.d/com.webos.exampleapp.qmlapp.client.negative.one.app.json`:
```json
{
    "com.webos.exampleapp.qmlapp.client.negative.one-*": [
        "private",
        "public"
    ]
}
```
