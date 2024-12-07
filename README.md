# Smart-socket-WT32C3-01N

This Wi-Fi socket is sold with SmartLife/Tuya firmware.
Here is a way to put OpenBeken firmware instead: https://www.elektroda.com/rtvforum/topic4020634.html

Advantages:
- True local access (no cloud)
- MQTT
- Tasmota-like

Disadvantages:
- Watchdog reboot on failure randomly
- No bluetooth

Found a module (WT32C3-01N) that can replace the original ciruit (SM-028_V1.3) and has equivalent pins order.  
WT32C3-01N must be flashed with https://github.com/Jason2866/Tasmota-specials/blob/firmware/firmware/tasmota32/other/tasmota32c3-bluetooth.factory.bin  

Once soldered to the socket, here is the Tasmota template: `{"NAME":"WT32C3-01N BLE Relay","GPIO":[0,544,0,2656,224,2624,320,0,0,0,2720,1,1,1,0,0,0,0,1,1,1,32],"FLAG":0,"BASE":1}`

