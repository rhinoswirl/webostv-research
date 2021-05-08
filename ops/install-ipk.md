# Download and install an ipk in (root) shell

```
curl -L https://github.com/mariotaku/moonlight-tv/releases/download/v0.6.0/com.limelight.webos_0.6.0_arm.ipk -o /media/internal/downloads/app.ipk && \
luna-send -i -f luna://com.webos.appInstallService/dev/install '{"id":"com.limelight.webos","ipkUrl":"/media/internal/downloads/app.ipk","subscribe":true}'
```