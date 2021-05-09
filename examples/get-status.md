# Getting system status

You can query the system to get some details of its status, such as:

## Applications

Get currently running application:

```
luna-send -i 'luna://com.webos.applicationManager/getForegroundAppInfo' '{"subscribe":true}'
```
