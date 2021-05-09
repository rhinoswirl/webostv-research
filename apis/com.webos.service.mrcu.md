# com.webos.service.mrcu

Service URI - luna://com.webos.service.mrcu

This service is related with operations with the Magic Remote.

The official [Magic Remote API Reference](https://webostv.developer.lge.com/api/webos-service-api/magic-remote/) has information on pairing and fetching sensor data, but not mutch else.

When enabling magic remote IR control of appliances, LG's services are accessed to download new keycodes.

These are then stored in `/mnt/lg/user/irdbmanager (oss_audio_append_db.txt` and `setting/oss_setting_info_audio.txt`).

Some default codes are also present in `/usr/share/irdbmanager`.

The executable file that listens to these calls is located in `/usr/sbin/lginput2`.

## Methods

| Method                      | Description |
|-----------------------------|-------------|
| [enableDualPairing](enableDualPairing)            |             |
| [enablePrintRfStatus](enablePrintRfStatus)          |             |
|                             |             |
| [sensor/getSensorData](sensor-getSensorData)        |             |
| [sensor/resetQuaternion](sensor-resetQuaternion)      |             |
|                             |             |
| [cursor/setSlideMode](cursor-setSlideMode)         |             |
| [cursor/setAutoAlign ](cursor-setAutoAlign)        |             |
| [cursor/setPosition](cursor-setPosition)          |             |
| [cursor/setWakeUpCondition](cursor-setWakeUpCondition)    |             |
|                             |             |
| [startPairing](startPairing)                 |             |
| [isPaired](isPaired)                     |             |
| [subscribeRfStatus](subscribeRfStatus)            |             |
| [getPairingStatus](getPairingStatus)             |             |
| [getDeviceInfo](getDeviceInfo)                |             |
| [activateMrcu](activateMrcu)                 |             |
| [createToast](createToast)                  |             |
| [createAlert](createAlert)                  |             |
| [setSleepMode](setSleepMode)                 |             |
| [startFirmwareUpdate](startFirmwareUpdate)          |             |
| [enablePrintRfStatus](enablePrintRfStatus)          |             |
| [getConnectionStatus](getConnectionStatus)          |             |
| [activateMotionSensor](activateMotionSensor)         |             |
| [setHotkeyCursorPolicy](setHotkeyCursorPolicy)        |             |
| [getMotionEngineStatus](getMotionEngineStatus)        |             |
| [getPairingHistory](getPairingHistory)            |             |
| [getPairingHistoryCount](getPairingHistoryCount)       |             |
| [setPairingHistoryKeyCode](setPairingHistoryKeyCode)     |             |
| [enableAudioSinkMode](enableAudioSinkMode)          |             |
| [enableLoggingMotion](enableLoggingMotion)          |             |
|                             |             |
| [voice/subscribeDeviceStatus](voice-subscribeDeviceStatus)  |             |
| [voice/sendCommand](voice-sendCommand)            |             |
| [voice/setSharedMemory](voice-setSharedMemory)        |             |
| [voice/subscribeAudioStatus](voice-subscribeAudioStatus)   |             |
|                             |             |
| [sensor/getSensorData](sensor-getSensorData)         |             |
| [sensor/resetQuaternion](sensor-setCursorBounds)       |             |
| [sensor/setCursorBounds](sensor-setCursorBounds)       |             |
|                             |             |
| [ir/pushIrCodes](ir-pushIrCodes)              |             |
| [ir/saveIrCodes](ir-saveIrCodes)               |             |
| [ir/eraseIrCodes](ir-eraseIrCodes)             |             |
|                             |             |
| [cursor/setSlideMode](cursor-setSlideMode)          |             |
| [cursor/setAutoAlign](cursor-setAutoAlign)         |             |
| [cursor/setPosition](cursor-setPosition)          |             |
| [cursor/setSensitivity](cursor-setSensitivity)        |             |
| [cursor/setWakeUpCondition](cursor-setWakeUpCondition)    |             |
|                             |             |
| [hid/subscribeDevicesStatus](hid-subscribeDevicesStatus)  |             |
| [hid/connect](hid-connect)                 |             |
| [hid/disconnect](hid-disconnect)              |             |


## <a name="enableDualPairing"></a> enableDualPairing

See [official docs](https://webostv.developer.lge.com/api/webos-service-api/magic-remote/?wos_flag=enabledualpairing#enabledualpairing).


## <a name="enablePrintRfStatus"></a> enablePrintRfStatus


## <a name="sensor-getSensorData"></a> getSensorData

See [official docs](https://webostv.developer.lge.com/api/webos-service-api/magic-remote/?wos_flag=getsensordata#getsensordata).



## <a name="sensor-resetQuaternion"></a> resetQuaternion

See [official docs](https://webostv.developer.lge.com/api/webos-service-api/magic-remote/?wos_flag=resetquaternion#resetquaternion).


## <a name="cursor-setSlideMode"></a> setSlideMode


## <a name="cursor-setAutoAlign"></a> setAutoAlign


## <a name="cursor-setPosition"></a> setPosition


## <a name="cursor-setWakeUpCondition"></a> setWakeUpCondition


## <a name="startPairing"></a> startPairing


## <a name="isPaired"></a> isPaired


## <a name="subscribeRfStatus"></a> subscribeRfStatus


## <a name="getPairingStatus"></a> getPairingStatus


## <a name="getDeviceInfo"></a> getDeviceInfo


## <a name="activateMrcu"></a> activateMrcu


## <a name="createToast"></a> createToast


## <a name="createAlert"></a> createAlert


## <a name="setSleepMode"></a> setSleepMode


## <a name="startFirmwareUpdate"></a> startFirmwareUpdate


## <a name="enablePrintRfStatus"></a> enablePrintRfStatus


## <a name="getConnectionStatus"></a> getConnectionStatus


## <a name="activateMotionSensor"></a> activateMotionSensor


## <a name="setHotkeyCursorPolicy"></a> setHotkeyCursorPolicy


## <a name="getMotionEngineStatus"></a> getMotionEngineStatus


## <a name="getPairingHistory"></a> getPairingHistory


## <a name="getPairingHistoryCount"></a> getPairingHistoryCount


## <a name="setPairingHistoryKeyCode"></a> setPairingHistoryKeyCode


## <a name="enableAudioSinkMode"></a> enableAudioSinkMode


## <a name="enableLoggingMotion"></a> enableLoggingMotion


## <a name="voice-subscribeDeviceStatus"></a> voice/subscribeDeviceStatus


## <a name="voice-sendCommand"></a> voice/sendCommand


## <a name="voice-setSharedMemory"></a> voice/setSharedMemory


## <a name="voice-subscribeAudioStatus"></a> voice/subscribeAudioStatus


## <a name="sensor-getSensorData"></a> sensor/getSensorData


## <a name="sensor-resetQuaternion"></a> sensor/resetQuaternion


## <a name="sensor-setCursorBounds"></a> sensor/setCursorBounds


## <a name="ir-pushIrCodes"></a> ir/pushIrCodes


```bash
luna-send -a 'important-dunno-why-lol' -n 1 -f 'luna://com.webos.service.mrcu/ir/pushIrCodes' '{ "irCodes": "0xaa 0x00 0x00 0x00 0x0c 0x94 0x00 0x00 0x58 0x0f 0x02 0x00 0xa2 0x00 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x04 0x1a 0x07 0x07 0x81 0x2d 0x07 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 0x07 0x81 0x2d 0x07 0x07 0x81 0x13 0x03 ", "irCodeCount": 174 }'
```

**TODO:** research what's the actual encoding scheme


## <a name="ir-saveIrCodes"></a> ir/saveIrCodes


## <a name="ir-eraseIrCodes"></a> ir/eraseIrCodes


## <a name="cursor-setSlideMode"></a> cursor/setSlideMode


## <a name="cursor-setAutoAlign"></a> cursor/setAutoAlign


## <a name="cursor-setPosition"></a> cursor/setPosition


## <a name="cursor-setSensitivity"></a> cursor/setSensitivity


## <a name="cursor-setWakeUpCondition"></a> cursor/setWakeUpCondition


## <a name="hid-subscribeDevicesStatus"></a> hid/subscribeDevicesStatus


## <a name="hid-connect"></a> hid/connect


## <a name="hid-disconnect"></a> hid/disconnect

