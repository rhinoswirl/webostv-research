# Receiving DIAL/SSDP

It is possible to configure a user-developed application to accept [DIAL](https://en.wikipedia.org/wiki/Discovery_and_Launch) start requests.

In your app's `appInfo.json`, add the following contents:

```json
    "dialAppName": "your-app-dial-name" 
```


E.g.: the official YouTube app has `"dialAppName": "youtube"`.



When multiple apps declare the same dialAppName, the system orders them lexicographically based on their IDs and the last one will be the one triggered via DIAL (com.youtube.adfree < youtube.leanback.v4 < youtube.leanforward).

YouTube and Netflix apps have some special handling, but they still can be overriden by an unofficial app.

