# com.webos.service.tv.broadcast

There seems to be an api for controlling the current broadcast and simulate a TV remote.

There is a patent around how this service works that exposes several technical details: https://patents.google.com/patent/KR20150101367A/en


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