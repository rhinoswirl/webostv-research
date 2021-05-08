# Userscripts in apps

Userscript present in [webOSUserScripts/userScript.js](https://github.com/webosose/wam/blob/f7c68dbeb744e8af66e4a83507b3d429dd692b2f/src/core/WebAppManagerConfig.cpp#L71-L73) will be [loaded as a userscript](https://github.com/webosose/wam/blob/f7c68dbeb744e8af66e4a83507b3d429dd692b2f/src/core/WebPageBase.cpp#L476-L486) in app webviews / frames. (including frames in origins outside of app root)

Example app: https://github.com/FriedChickenButt/youtube-webos