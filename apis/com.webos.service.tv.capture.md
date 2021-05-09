# com.webos.service.tv.capture

## Methods

com.webos.service.tv.capture/createHandle
com.webos.service.tv.capture/destroyHandle
com.webos.service.tv.capture/execute
com.webos.service.tv.capture/executeOneShot
com.webos.service.tv.capture/getClipRegions
com.webos.service.tv.capture/getOptions
com.webos.service.tv.capture/getProperties
com.webos.service.tv.capture/isLocked
com.webos.service.tv.capture/lock
com.webos.service.tv.capture/setClipRegions
com.webos.service.tv.capture/setOptions
com.webos.service.tv.capture/setOutput
com.webos.service.tv.capture/setProperties
com.webos.service.tv.capture/unlock


### executeOneShot

```
luna-send -n 1 -f 'luna://com.webos.service.tv.capture/executeOneShot' '{"path":"/tmp/capture.png","method":"DISPLAY","format":"PNG"}'
# Supported formats: BMP, JPG, PNG, RGB, RGBA, YUV422
# Supported methods: SCREEN/DISPLAY (alias?), SCREEN_WITH_SOURCE_VIDEO, VIDEO, GRAPHIC, SOURCE/SCALER (alias?)
```

**Note:** this is also available over SSAP as: ssap://tv/executeOneShot - returns imageUri attribute with HTTP link

Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)