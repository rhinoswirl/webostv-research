# com.webos.applicationManager



```sh
# Get currently running application
luna-send -i 'luna://com.webos.applicationManager/getForegroundAppInfo' '{"subscribe":true}'

# List all apps
luna-send -i 'luna://com.webos.applicationManager/listApps' '{"subscribe":true}'

# List only devmode apps
luna-send -i 'luna://com.webos.applicationManager/dev/listApps' '{"subscribe":true}'

```

Below is a list of methods and signals registered by this service.

The `provides` array specifies the requirements that a service must have in order to call the bus method.

```js

METHODS AND SIGNALS REGISTERED BY SERVICE 'com.webos.applicationManager' AT HUB

  "/":
      "getForegroundAppInfo": {"provides":["private","activities.callbacks","configurator.callbacks","all","applications.internal"]}
      "moveLaunchPoint": {"provides":["private","all","applications.internal"]}
      "listAllHandlersForMimeByVerb": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "getAppLifeEvents": {"provides":["private","all","applications.internal"]}
      "listLaunchPoints": {"provides":["private","configurator.callbacks","all","applications.internal"]}
      "listApps": {"provides":["private","activities.callbacks","configurator.callbacks","all","applications.internal"]}
      "removeLaunchPoint": {"provides":["private","all","applications.internal"]}
      "searchApps": {"provides":["private","all","applications.internal"]}
      "registerVerbsForRedirect": {"provides":["private","all","applications.internal"]}
      "lockApp": {"provides":["private","all","applications.internal"]}
      "getAppLifeStatus": {"provides":["private","activities.callbacks","all","applications.internal"]}
      "closeByAppId": {"provides":["private","activities.callbacks","all","applications.internal"]}
      "getAppBasePath": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "registerApp": {"provides":["private","applications","public","all","applications.internal"]}
      "getAppInfo": {"provides":["private","all","applications.internal"]}
      "getHandlerForUrlByVerb": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "changeRunningAppId": {"provides":["private","all","applications.internal"]}
      "listAllHandlersForUrlPattern": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "running": {"provides":["private","activities.callbacks","all","applications.internal"]}
      "launchVirtualApp": {"provides":["private","all","applications.internal"]}
      "registerNativeApp": {"provides":["private","applications","public","all","applications.internal"]}
      "launch": {"provides":["private","activities.callbacks","configurator.callbacks","applications","public","ares.webos.cli","all","applications.launch","applications.internal"]}
      "notifySplashTimeout": {"provides":["private","all","applications.internal"]}
      "getHandlerForUrl": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "getHandlerForMimeType": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "mimeTypeForExtension": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "listAllHandlersForMultipleUrlPattern": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "getAppStatus": {"provides":["private","configurator.callbacks","all","applications.internal"]}
      "addVirtualApp": {"provides":["private","all","applications.internal"]}
      "registerVerbsForResource": {"provides":["private","all","applications.internal"]}
      "notifyAlertClosed": {"provides":["private","all","applications.internal"]}
      "removeVirtualApp": {"provides":["private","all","applications.internal"]}
      "getHandlerForMimeTypeByVerb": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "listAllHandlersForMime": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "listAllHandlersForUrlByVerb": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "listAllHandlersForMultipleMime": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "listExtensionMap": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "updateLaunchPoint": {"provides":["private","all","applications.internal"]}
      "open": {"provides":["private","applications","public","all","applications.launch","applications.internal"]}
      "listAllHandlersForUrl": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "getAppLoadStatus": {"provides":["private","public","all","applications.internal"]}
      "pause": {"provides":["private","all","applications.internal"]}
      "addLaunchPoint": {"provides":["private","all","applications.internal"]}
      "getHandlerForExtension": {"provides":["private","applications","public","all","applications.query","applications.internal"]}
      "closeAllApps": {"provides":["private","all","applications.internal"]}
      "onLaunch": {"provides":["private","all","applications.internal"]}
      "close": {"provides":["private","all","applications.internal"]}
      "isPromotionalAppOn": {"provides":["private","applications","public","all","applications.internal"]}
  "/dev":
      "closeByAppId": {"provides":["ares.webos.cli","all"]}
      "listApps": {"provides":["private","applications.dev","ares.webos.cli","all","applications.internal"]}
      "running": {"provides":["private","applications.dev","ares.webos.cli","all","applications.internal"]}
```