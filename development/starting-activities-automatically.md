# Starting activities automatically

**Note:** This page is for documentation purposes. It is not clear if it is possible for user-installed apps to be part of the autostart list.

It is possible to create some rules that will allow the autostart of certain services based on a set of conditions being met.

The system has some of these activities present in `/etc/palm/activities`.

Here is an example of a file that will start an service automatically when Internet connection is enabled:

```
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

There is also `webos-preload-manager` (`com.webos.service.preloadmanager`; `/usr/bin/webos-preload-manager`), which is a service responsible for preloading components, which exposes the following methods:

```
"com.webos.service.preloadmanager/getPreloadPolicy"
"com.webos.service.preloadmanager/setPreloadPolicy"
"com.webos.service.preloadmanager/setPreloadStatus"
```

The configuration is stored in a `.json` file (see `/etc/configd/layers/base/com.webos.service.preloadmanager.json`) with the following format:

```
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