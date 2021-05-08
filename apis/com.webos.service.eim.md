# com.webos.service.eim

This service seems to be registered with configuring input sources of the TV (and maybe other things?).

## Adding sources

We can create our own input source entry that launches our app by declaring the following in the app's manifest (`appInfo.json`):

```json
    "supportGIP": true,
    "largeIcon": "" # needs to be set (otherwise eim just crashes)
```

When starting up an app following call needs to be executed to register it:

```js
webOS.service.request("luna://com.webos.service.eim", {
  method: "addDevice",
  parameters: {
    "appId": "org.webosbrew.hbchannel", // your application ID, required
    "pigImage": "", // required, preview image rendered in "All inputs", relative to main application directory, can be just an empty string
    "type": "MVPD_IP", // optional, no idea (can be MVPD_IP or MVPD_RF)
    "showPopup": true, // optional, shows a toast with info that default input has been changed to label
    "label": "application name", // optional, used in toast message only
    "description": "testing", // optional, description rendered in "All inputs"
  },
  onSuccess: function (res) { console.info('success:',res); },
  onFailure: function (res) { console.info('failure:', res); }
 });
 ```

## Removing sources

`luna://com.webos.service.eim/deleteDevice {"appId":"..."}` call can be used to unregister an app.

This also works over `luna-send-pub` for any app, as long as its `appinfo.json` is properly set up, in case anyone wants to debug this manually. (source app ID is not verified)