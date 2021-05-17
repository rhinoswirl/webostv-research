# Receiving DIAL/SSDP

DIAL allows launching a TV app using your phone. It is possible to configure a user-developed application to accept [DIAL](https://en.wikipedia.org/wiki/Discovery_and_Launch) start requests.

SSDP is advertised on 36866.

To register an app for DIAL, add the following contents to your app's `appInfo.json`:

```json
    "dialAppName": "your-app-dial-name" 
```

You can also allow your app to automatically turn on the TV by adding `"wolwowlan": true` to the manifest file.

```json
"wolwowlan":true
```

You are able to communicate with your service using the following endpoints:

```
# Get app info
GET http://your-tv-ip-address:18181/apps/<your-app-dialAppName>
```

```
# Launch app
POST http://your-tv-ip-address:18181/apps/<your-app-dialAppName>/run
```

```
# Hide app
POST http://your-tv-ip-address:18181/apps/<your-app-dialAppName>/hide
```

```
# Stop app
DELETE http://your-tv-ip-address:18181/apps/<your-app-dialAppName>
```

YouTube and Netflix apps have some special handling that allows them to be launched with additional parameters, which is not applicable to third-parties.

When multiple apps declare the same dialAppName, the system orders them lexicographically based on their IDs and the last one will be the one triggered via DIAL (e.g.: com.youtube.adfree < youtube.leanback.v4 < youtube.leanforward).


