# Potentially hackable apps

My starter (triggered by pressing clock on home screen) → /usr/palm/applications/com.webos.app.mystarter/qml/main.qml
    
Screensaver (fireworks) → /usr/palm/applications/com.webos.app.screensaver/qml/main.qml

Home screen layout → seems like all .qml files are bundled in surface-manager-starfish (managed to extract it without filenames with binwalk - someone needs to make some qt resources unpacker) - but it also accepts an env variable with custom .qml startup file.

Credits: [Informatic](https://gist.github.com/Informatic/1983f2e501444cf1cbd182e50820d6c1)