# Scheduled tasks and triggers

> **Warning:** Untested

## Activity Manager

The Activity Manager ([com.webos.service.activitymanager (webosose)](https://www.webosose.org/docs/reference/ls2-api/com-webos-service-activitymanager/), [com.palm.activitymanager (webosTV)](https://webostv.developer.lge.com/api/webos-service-api/activity-manager/)) is responsible for coordinating work in the system and is able to start any dynamic service that needs to wake up when certain conditions are met.

For this to work, it is necessary to create an Activity, which represents some specific item of work in the system. It works like a scheduler that tracks events described in an Activity and reacts to them based on the Activity's specification.

The system has some of these activities present in `/etc/palm/activities`.

Here is an example of a file that will start an service automatically when Internet connection is enabled:

```json
{
    "activity" : {
        "name" : "com.example.service.auto.start",
        "description" : "Start example service when network enabled",
        "trigger" : {
            "method" : "luna://com.palm.connectionmanager/getstatus",
			"where" : {
				"or": {
					"prop" : ["isInternetConnectionAvailable"],
					"op" : "=",
					"val" : true
				}
			},
            "params" : {"subscribe":true}
         },
        "callback" : {
            "method" : "luna://com.example.service/start"
        },
        "type" : {
            "foreground" : true,
            "explicit" : true
        }
    },
    "replace" : true,
    "start" : true
}
```

Example code to create activity with a combined trigger:

```sh
# luna-send -i -f luna://com.webos.service.activitymanager/create '{
  "activity": {
    "name": "browser restart",
    "description":"",
    "type": { "foreground":true, "continuous": true },
    "callback": {
      "method": "luna://com.webos.service.applicationmanager/launch",
      "params": { "id": "com.webos.app.enactbrowser" }
    },
    "trigger": {
      "and": [
        {
          "method": "luna://com.webos.service.applicationmanager/getAppLifeStatus",
          "params": { "subscribe": true },
          "where": {
            "and": [
              { "op": "=", "prop": "appId", "val": "com.webos.app.enactbrowser" },
              { "op": "=", "prop": "status", "val": "stop"}
            ]
          }
        },
        {
          "method": "luna://com.webos.service.connectionmanager/getstatus",
          "params": { "subscribe": true },
          "where": { "prop": "isInternetConnectionAvailable", "op": "=", "val": true }
        }
      ]
    }
  },
  "start": true,
  "subscribe": true
}'
```

```json
# Response:

{
  "activityId": 85,
  "returnValue": true,
  "subscribed": true
}

# Subscription response:

{
  "event": "start",
  "activityId": 85,
  "returnValue": true,
  "subscribed": true
}
```

Example code to create a scheduled activity inside a service:

```js
// Create a scheduled activity with callback
var request = webOS.service.request("luna://com.palm.activitymanager", {
    method: "create",
    parameters: {
        "activity": {
            "name": "ScheduledActivityWithCallback",
            "description": "Test create of scheduled activity with callback",
            "type": {
                "foreground": true
            },
                        "schedule": {
                                "start": "2015-02-15 00:05:00"
                        },
                        "callback": {
                                "method": "luna://com.webos.audio/setMuted",
                                "params": {
                                    "muted": "true"
                                }
                        }
        },
        "start": true,
        "subscribe": true
    },
    onSuccess: function (inResponse) {
        if (!inResponse.event) {
            console.log("The scheduled Activity is created");
            // To-Do something
        } else {
            console.log("Received event: " + inResponse.event);
            console.log("Audio will be muted");
            // To-Do something
        }
    },
    onFailure: function (inError) {
        console.log("Failed to create the Activity");
        console.log("[" + inError.errorCode + "]: " + inError.errorText);
        // To-Do something
        return;
    }
});
```

## webos-preload-manager



There is also `webos-preload-manager` (`com.webos.service.preloadmanager`; `/usr/bin/webos-preload-manager`), which is a service responsible for preloading components, which exposes the following methods:

```
"com.webos.service.preloadmanager/getPreloadPolicy"
"com.webos.service.preloadmanager/setPreloadPolicy"
"com.webos.service.preloadmanager/setPreloadStatus"
```

The configuration is stored in a `.json` file (see `/etc/configd/layers/base/com.webos.service.preloadmanager.json`) with the following format:

```json
{
    "id" : "app-id",
    "staticPriority" : 10,
    "requiredMemory" : 100,
    "preloadType" : "periodic",
    "preloadMode" : "partial",
    "isEnabled" : true,
    "isPinUp" : true
},
```

The output when trying to start the service manually:

```
webos-preload-manager (LS2 dynamic service)
Note:
 - This service preloads webos components based on user usage information
 - This service is a dynamic service to save system resources
 - Configuration file format should be JSON format
Examples:
Start app preloading
 $ webos-preload-manager
Start app preloading with verbose mode
 $ webos-preload-manager --verbose
Start app preloading with custom conf file
 $ webos-preload-manager --conf=/var/my.json
 ```