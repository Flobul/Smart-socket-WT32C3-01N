# Smart-socket-WT32C3-01N

This Wi-Fi socket is originally sold with SmartLife/Tuya firmware. While functional, some users prefer alternative firmware for enhanced customization and features. Here's a guide on how to replace the original firmware with OpenBeken or Tasmota firmware for better control and functionality.  
It contains a BL602 chip, with energy meter BL0937.
Here is a way to put OpenBeken firmware instead: https://www.elektroda.com/rtvforum/topic4020634.html

## Original Firmware: SmartLife/Tuya

### Advantages
- True Local Access: No need for constant cloud connection.
- MQTT Support: Allows integration with home automation systems like Home Assistant or OpenHAB.
- Tasmota-like Functionality: Simplified configuration and control interface.
### Disadvantages
- Random Watchdog Reboots: Stability issues that can interrupt usage.
- No Bluetooth Support: Limited functionality for devices requiring BLE.

## Upgrading to WT32C3-01N

To overcome the limitations of the original firmware, you can replace the socket's circuit board with a WT32C3-01N module. This module includes Bluetooth and Wi-Fi capabilities and is compatible with Tasmota firmware.

### Required Components
1. WT32C3-01N Module: A versatile chip that supports BLE and Wi-Fi.
2. Soldering Equipment: To replace the original circuit.
3. Firmware Tools: For flashing Tasmota firmware onto the WT32C3-01N.

## Replacement Process

1. Flashing the WT32C3-01N Module
Before installation, the WT32C3-01N module must be flashed with a compatible firmware. Use the following binary for Tasmota:
[Tasmota Special Firmware - WT32C3](https://github.com/Jason2866/Tasmota-specials/blob/firmware/firmware/tasmota32/other/tasmota32c3-bluetooth.factory.bin)

2. Soldering
Locate the original circuit board (SM-028_V1.3) in the socket.
Remove the original board and solder the WT32C3-01N in place. Ensure proper alignment with the equivalent pin order for seamless integration.
Required pins: RX, TX, GND, 3V3, IO9 (to GND on boot)
4. Configuring Tasmota
After installing the new board, configure the socket with the following Tasmota template:
```
{"NAME":"WT32C3-01N BLE Relay","GPIO":[0,544,0,2656,224,2624,320,0,0,0,2720,1,1,1,0,0,0,0,1,1,1,32],"FLAG":0,"BASE":1}
```
This template maps the GPIO pins to the correct functions for relay control, energy monitoring, and other features.

## Power Monitoring Calibration

The WT32C3-01N module contains a BL0937 chip for power monitoring. Calibration is required to ensure accurate readings. Use the following commands in the Tasmota console to adjust the calibration parameters:
```
PowerSetCal 8512
VoltageSetCal 1533
CurrentSetCal 3400
```
Adjust these values based on your specific device and usage to improve accuracy.


## Benefits of Upgrading

- Enhanced Stability: Tasmota eliminates the random reboots caused by the original firmware.
- Bluetooth Support: Unlocks BLE capabilities for further integrations.
- True Customization: Access advanced features like timers, automations, and OTA updates.
- Integration with Home Automation: Full MQTT support allows seamless integration with platforms like Home Assistant.

## Additional Resources

- [OpenBeken Documentation]([https://duckduckgo.com](https://www.elektroda.com/rtvforum/topic4020634.html)): Learn more about OpenBeken firmware and its features.
- [Tasmota Documentation](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://tasmota.github.io/docs/&ved=2ahUKEwiBmNrI65eKAxUgdqQEHTzOAxEQFnoECA0QAQ&usg=AOvVaw0S1uTSMPQYl1XrlfGiXq98): Comprehensive guide to Tasmota configuration and usage.

If you have any issues or suggestions, feel free to open an issue in this repository. Happy hacking!
