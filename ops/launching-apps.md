# Launching apps via shell

It is possible to launch apps from the shell by running:

```
luna-send -n 1 -f luna://com.webos.service.applicationManager/launch '{"id":"com.webos.app.screensaver"}' 
```

Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)