# com.webos.service.tvpower

## Methods

com.webos.service.tvpower/power/getClientList
com.webos.service.tvpower/power/getPowerOnReason
com.webos.service.tvpower/power/getPowerState
com.webos.service.tvpower/power/powerOff
com.webos.service.tvpower/power/powerOn
com.webos.service.tvpower/power/reboot
com.webos.service.tvpower/power/registerActiveStandbyRequest
com.webos.service.tvpower/power/registerPowerOffRequest
com.webos.service.tvpower/power/registerPrepareActiveStandby
com.webos.service.tvpower/power/registerPreparePowerOff
com.webos.service.tvpower/power/registerPreparePowerOn
com.webos.service.tvpower/power/registerPrepareResume
com.webos.service.tvpower/power/registerPrepareSuspend
com.webos.service.tvpower/power/registerScreenSaverRequest
com.webos.service.tvpower/power/registerSuspendRequest
com.webos.service.tvpower/power/responseActiveStandbyRequest
com.webos.service.tvpower/power/responsePowerOffRequest
com.webos.service.tvpower/power/responsePrepareActiveStandby
com.webos.service.tvpower/power/responsePreparePowerOff
com.webos.service.tvpower/power/responsePreparePowerOn
com.webos.service.tvpower/power/responsePrepareResume
com.webos.service.tvpower/power/responsePrepareSuspend
com.webos.service.tvpower/power/responseScreenSaverRequest
com.webos.service.tvpower/power/responseSuspendRequest
com.webos.service.tvpower/power/sendActiveStandbyRequestAck
com.webos.service.tvpower/power/sendPowerOffRequestAck
com.webos.service.tvpower/power/sendPrepareActiveStandbyAck
com.webos.service.tvpower/power/sendPreparePowerOffAck
com.webos.service.tvpower/power/sendPreparePowerOnAck
com.webos.service.tvpower/power/setPowerInitState
com.webos.service.tvpower/power/setPowerOnReason
com.webos.service.tvpower/power/setScreenBlock
com.webos.service.tvpower/power/turnOffScreen
com.webos.service.tvpower/power/turnOnScreen
com.webos.service.tvpower/power/turnOnScreenSaver



```
# Suspend / resume
luna-send -i 'luna://com.webos.service.tvpower/power/getPowerState' '{"subscribe":true}'

```