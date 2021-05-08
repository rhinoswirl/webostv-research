# com.webos.service.tv.capture



```
luna-send -n 1 -f 'luna://com.webos.service.tv.capture/executeOneShot' '{"path":"/tmp/capture.png","method":"DISPLAY","format":"PNG"}'
# Supported formats: BMP, JPG, PNG, RGB, RGBA, YUV422
# Supported methods: SCREEN/DISPLAY (alias?), SCREEN_WITH_SOURCE_VIDEO, VIDEO, GRAPHIC, SOURCE/SCALER (alias?)
```

**Note:** this is also available over SSAP as: ssap://tv/executeOneShot - returns imageUri attribute with HTTP link

Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)