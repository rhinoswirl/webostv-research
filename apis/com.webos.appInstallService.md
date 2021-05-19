# com.webos.appInstallService

The AppInstallService is responsible for installing apps.

The `provides` array specifies the requirements that a service must have in order to call the bus method.

```js

METHODS AND SIGNALS REGISTERED BY SERVICE 'com.webos.appInstallService' AT HUB

  "/":
      "install": {"provides":["activities.callbacks","private","appinstalld.internal","all"]}
      "resume": {"provides":["private","appinstalld.internal","all"]}
      "createLSConfigFiles": {"provides":["private","appinstalld.internal","all"]}
      "status": {"provides":["activities.callbacks","private","appinstalld.internal","all"]}
      "remove": {"provides":["private","appinstalld.internal","all"]}
      "queryInstallCapacity": {"provides":["private","appinstalld.internal","all"]}
      "removeLSConfigFiles": {"provides":["private","appinstalld.internal","all"]}
      "cancel": {"provides":["private","appinstalld.internal","all"]}
      "installLocal": {"provides":["appinstalld.internal","all"]}
      "pause": {"provides":["private","appinstalld.internal","all"]}
  "/group":
      "install": {"provides":["private","appinstalld.internal","all"]}
      "status": {"provides":["private","appinstalld.internal","all"]}
      "queryInstallCapacity": {"provides":["private","appinstalld.internal","all"]}
  "/dev":
      "install": {"provides":["private","appinstalld.internal","ares.webos.cli","all"]}
      "remove": {"provides":["ares.webos.cli","all"]}

```