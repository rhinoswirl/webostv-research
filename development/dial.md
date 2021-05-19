# Receiving DIAL/SSDP

DIAL/SSDP allows launching a TV app using your phone. It is possible to configure a user-developed application to accept [DIAL](https://en.wikipedia.org/wiki/Discovery_and_Launch) start requests.

To register an app for DIAL, add the following contents to your app's `appInfo.json`:

```json
    "dialAppName": "your-app-dial-name" 
```

You can also allow your app to automatically turn on the TV by adding `"wolwowlan": true` to the manifest file.

```json
"wolwowlan":true
```

`com.webos.service.dial` starts SSDP and HTTP servers on port 36866 (both in the same port?). This port is advertised to the exterior.

The system also has a "YouTube Port" in 18181 which can reply to commands similar to the following:

> **Warning:** Untested!

```
# Get app info
GET http://localhost:18181/apps/<dialAppName>
```

```
# Launch app
POST http://localhost:18181/apps/<dialAppName>/run
```
development/dial.md
```
# Hide app
POST http://localhost:18181/apps/<dialAppName>/hide
```

```
# Stop app
DELETE http://localhost:18181/apps/<dialAppName>
```

YouTube and Netflix apps have some special handling that allows them to be launched with additional parameters, which is not applicable to third-parties.

When multiple apps declare the same dialAppName, the system orders them lexicographically based on their IDs and the last one will be the one triggered via DIAL (e.g.: com.youtube.adfree < youtube.leanback.v4 < youtube.leanforward).


