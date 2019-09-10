# Tasmota switch as binary_sensor
### Can be REED, PIR, button, switch, at pin status change send mqtt message 

## Tasmota configuration
Configure module with Switch1 to corrisponding GPIO in console.

Configure MQTT topic camera/sensori.

> ON \<trigger\> DO \<command\> [ENDON | BREAK]
  
```
SwitchTopic 0
SwitchMode1 1
Rule1 on switch1#state do publish stat/camera/motion/STATE %value% endon
Rule1 1
```

can be multiple rules in the same rule set

```
SwitchTopic 0
SwitchMode1 1
SwitchMode2 1
Rule1 on switch1#state do publish stat/camera/motion/STATE %value% endon on switch2#state do publish stat/camera/door/STATE %value% endon
Rule1 1
```

## Home Assistant configuration
```
binary_sensor:
  - platform: mqtt
    name: "Camera movimento"
    state_topic: "stat/camera/motion/STATE"
    availability_topic: "tele/camera/sensori/LWT"
    payload_on: "1"
    payload_off: "0"
    device_class: motion
  - platform: mqtt
    name: "Camera porta"
    state_topic: "stat/camera/door/STATE"
    availability_topic: "tele/camera/sensori/LWT"
    payload_on: "1"
    payload_off: "0"
    device_class: door
```

https://www.home-assistant.io/components/binary_sensor/
