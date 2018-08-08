# node-red-tzone
This is a draft flow for working with [Tzone Digital Technology](http://en.tzonedigital.cn/en/) BT04 and BT05 BLE temperature/humidity sensors. The subflow contains a function to demarshal the advertised binary 0xCBFF Service Data into a readable json structure.

For the flow I use the following setup

* Raspberry Pi3 (BLE built-in). You can also use a lower model with compatible BLE dongle, or take a different route altogether on the host sysem;
* You'll need the [EspruinoHub](https://github.com/espruino/EspruinoHub) for bridging BLE advertising data to local MQTT
* A [Mosquitto](https://mosquitto.org) server to receive the published BLE messages. The Node-Red flow will subscribe onto specific BLE (mac address) topics to receive the advertising data. Take a look at the EspuinoHub page for more details.

This flow only dumps readable json from various sensors into a debug node. You can work from there to send your data somewhere upstream.

