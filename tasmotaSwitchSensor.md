# Tasmota switch publish MQTT 
### Can be REED, PIR, button, switch, at pin status change send mqtt message 

## Tasmota configuration
Configure module with Switch1 to corrisponding GPIO in console

> ON <trigger> DO <command> [ENDON | BREAK]
  
```
SwitchTopic 0
SwitchMode1 1
Rule1 on switch1#state do publish cmnd/PIR/camera/STATE %value% endon
Rule1 1
```

can be multiple rules in the same rule set

```
SwitchTopic 0
SwitchMode1 1
SwitchMode2 1
Rule1 on switch1#state do publish cmnd/PIR/camera/STATE %value% endon on switch2#state do publish cmnd/REED/camera/STATE %value% endon
Rule1 1
```
