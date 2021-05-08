# groups.d

**Type:** Directory

**Location(s):**

```
/usr/share/luna-service2/
```

**Description:**

I believe this is related to what an app or service from a given group is actually allowed to perform on the system.

It contains the following files:

```
drwxr-xr-x    2 root     root           159 Jan  7 01:57 .
drwxr-xr-x    9 root     root           212 Jan  7 01:33 ..
-rw-r--r--    1 root     root           269 Jan  7 01:05 activitymanager.groups.json
-rw-r--r--    1 root     root          6031 Jan  7 01:04 all.groups.json
-rw-r--r--    1 root     root           251 Jan  7 01:04 appinstalld.groups.json
-rw-r--r--    1 root     root           136 Jan  7 01:05 configurator.groups.json
-rw-r--r--    1 root     root            99 Jan  7 01:04 db8.groups.json
```


`all.groups.json`:

```json
{
  "private": {
    "description": "Group for system level inter-service communications (compatibility support)",
    "public": false
  },
  "public": {
    "description": "Group of API available for almost any service (compatibility support)",
    "public": false
  },
  "all": {
    "description": "Global group provides full access to all services",
    "public": false
  },
  "signals.all": {
    "description": "Allows register signals and subscribe to signals on Luna service",
    "public": false
  },
  "signals.all.subscribe": {
    "description": "Allows subscribe to signals on Luna service",
    "public": true
  },
  "luna.internal.public": {
    "description": "Allows access to implicit service methods call and ping in /com/palm/luna/private",
    "public": false
  },
  "luna.internal": {
    "description": "Allows access to all implicit service methods in /com/palm/luna/private",
    "public": false
  },
  "activities": {
    "description": "Allows create activities to applications",
    "public": true
  },
  "activities.manage": {
    "description": "Allows create and manage activities",
    "public": false
  },
  "applications": {
    "description": "Full access to applications management functions",
    "public": true
  },
  "applications.dev": {
    "description": "Applications debug functions for development",
    "public": false
  },
  "applications.internal": {
    "description": "Applications management, installation and upgrading APIs",
    "public": false
  },
"applications.launch": {
    "description": "Launch and close applications",
    "public": true
  },
  "applications.query": {
    "description": "Query applications status and information",
    "public": true
  },
  "bluetooth.manage": {
    "description": "Manage bluetooth connections",
    "public": true
  },
  "bluetooth.query": {
    "description": "Query bluetooth service information",
    "public": true
  },
  "database": {
    "description": "Access to data storage services",
    "public": true
  },
  "database.internal": {
    "description": "Full access to webOS data storage services",
    "public": false
  },
  "devices": {
    "description": "Devices management services",
    "public": false
  },
  "eventmonitor.plugins" : {
    "description": "Event monitor plugin callback methods",
    "public": false
  },
  "filecache": {
    "description": "Query and manage filecache service",
    "public": true
  },
  "hub.configuration": {
    "description": "Allows services to change hub configuration",
    "public": false
  },
  "keymanager": {
    "description": "Allows applications to manage security requests through security key",
    "public": true
  },
  "media": {
    "description": "Full access to media services (manage audio, images, camera etc)",
    "public": false
  },
  "media.play": {
    "description": "Media playback functions",
    "public": false
  },
  "media.record": {
    "description": "Media recording functions",
    "public": false
  },
  "media.pipeline": {
    "description": "Media pipeline functions",
    "public": false
  },
  "networking": {
    "description": "Query and manage network services",
    "public": true
  },
  "networking.internal": {
    "description": "Full access to networking tools and management APIs",
    "public": false
  },
  "networking.query": {
    "description": "Query network and internet connection status",
    "public": true
  },
  "nfc.manage": {
    "description": "Manage NFC service",
    "public": false
  },
  "nfc.query": {
    "description": "Query NFC service",
    "public": true
  },
  "notifications": {
    "description": "Full access to system notifications",
    "public": false
  },
  "notifications.manage": {
    "description": "Manage system notifications",
    "public": true
  },
  "notifications.query": {
    "description": "Query system notifications",
    "public": true
  },
  "security": {
    "description": "Full access to security services",
    "public": false
  },
  "security.public": {
    "description": "Security services available to applications",
    "public": true
  },
  "sensors": {
    "description": "Full access to sensors service",
    "public": false
  },
  "sensors.query": {
    "description": "Query for sensors information",
    "public": true
  },
  "sensors.manage": {
    "description": "Execute methods which will change internal properties of sensors",
    "public": true
  },
  "services": {
    "description": "General software services on webOS platform",
    "public": false
  },
  "settings": {
    "description": "Read and modify system preferences and settings",
    "public": true
  },
  "settings.read": {
    "description": "Read system preferences and settings",
    "public": true
  },
  "system": {
    "description": "General system services provide full control over system",
    "public": false
  },
  "system.debug": {
    "description": "Logging, development and debug APIs",
    "public": false
  },
  "system.devmode": {
    "description": "Access to developer mode functionality",
    "public": false
  },
  "system.remote": {
    "description": "System services for remote applications",
    "public": false
  },
  "telephony": {
    "description": "Full access to telephony service",
    "public": false
  },
  "testing": {
    "description": "Examples and emulation services (for testing purposes only)",
    "public": false
  },
  "time": {
    "description": "Time management functions",
    "public": true
  },
  "time.query": {
    "description": "Time query functions",
    "public": true
  },
  "tv": {
    "description": "General TV APIs",
    "public": false
  },
  "tv.management": {
    "description": "TV management services",
    "public": false
  },
  "tv.services": {
    "description": "Software services for TV",
    "public": false
  },
  "tv.settings": {
    "description": "Query and change settings for TV",
    "public": false
  },
  "ux.control": {
    "description": "UI control and manipulation services",
    "public": false
  }
}

```
