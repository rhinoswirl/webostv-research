# appInfo.json

The `appInfo.json` is the app manifest file.

The only relevant thing I want to add here for now is:

```
"requiredPermissions": ["all"],
"visible":false,
"trustLevel":"default",
```

Where in `requiredPermissions`, it is possible to set an array of system permissions that will be appeneded to the app permissions (will it also work for services in that app?).

`visible` is responsible the visibility of the app in the launcher.

`trustLevel`, which can be one of:

- `default` (default): Adds the `public` permission to the app service permissions
- `trusted`: For system apps, adds the `private` permission to the service permissions
- `netcast`: Prevents the app from talking to the luna bus