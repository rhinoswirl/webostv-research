# com.webos.service.tv.broadcast

There seems to be an api for controlling the current broadcast and simulate a TV remote.

There is a patent around how this service works that exposes several technical details: https://patents.google.com/patent/KR20150101367A/en


## Methods


com.webos.service.tv.broadcast/changeChannel
com.webos.service.tv.broadcast/changeChannelDown
com.webos.service.tv.broadcast/changeChannelPrevious
com.webos.service.tv.broadcast/changeChannelUp
com.webos.service.tv.broadcast/changePlaySpeed
com.webos.service.tv.broadcast/changeVolatileChannel
com.webos.service.tv.broadcast/checkPipHotkey
com.webos.service.tv.broadcast/close
com.webos.service.tv.broadcast/getBroadcastState
com.webos.service.tv.broadcast/getChannelChangeResult
com.webos.service.tv.broadcast/getChannelState
com.webos.service.tv.broadcast/getCurrentChannel
com.webos.service.tv.broadcast/getPipeline4BootUp
com.webos.service.tv.broadcast/getPipelineTemporary
com.webos.service.tv.broadcast/getVodPauseState
com.webos.service.tv.broadcast/halt
com.webos.service.tv.broadcast/open
com.webos.service.tv.broadcast/pause
com.webos.service.tv.broadcast/pause1
com.webos.service.tv.broadcast/pin
com.webos.service.tv.broadcast/resume
com.webos.service.tv.broadcast/seek
com.webos.service.tv.broadcast/startMVPD
com.webos.service.tv.broadcast/stop


```js
	webOS.service.request('luna://com.webos.service.tv.broadcast', {
		method: "changeChannelUp",
		parameters: {
			"broadcastId": mediaId
		},
		onSuccess: function (res) {
			console.log('channel change successed');
			window.close();
		},
		onFailure: function (res) {
			console.log('channel change failed');
			console.log(res.errorText);
			$("footer").show();
			//window.close();
		},
	});
```


```js
webOS.service.request('luna://com.webos.service.tv.broadcast', {
		method: "changeChannelDown",
		parameters: {
			"broadcastId": mediaId
		},
		onSuccess: function (res) {
			console.log('channel change successed');
			window.close();
		},
		onFailure: function (res) {
			console.log('channel change failed');
			$("footer").show();
			//window.close();
		},
	});
```