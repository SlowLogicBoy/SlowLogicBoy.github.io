---
layout: post
title:  "ESP-01 Relay Module Notes"
---

# ESP-01 Wifi Relay module

If you don't have this, don't buy. It's a hassle to control, you occupy 2 pins when you can control simple relay with a single pin.
It's worth buying if it contais more then 2 relays, however good luck discovering what commands open and close which relay...

![ESP8266-01 Wifi Relay Module Image](assets/ESP8266-01_Wifi_Relay_Module.jpg)

I don't remember where I got these uart codes to control this relay, but you can find these on the internets.

Controlling this with ESPHome:
```yaml
esphome:
  name: relay_controller
  platform: ESP8266
  board: esp01

# ...

# Stuff to control this relay:
uart:
  tx_pin: GPIO1
  rx_pin: GPIO3
  baud_rate: 9600
  
switch:
  - platform: template
    id: relay1
    name: "relay1 switch"
    turn_on_action:
      - uart.write: [0xA0, 0x01, 0x01, 0xA2]
      - switch.template.publish:
          id: relay1
          state: ON
    turn_off_action:
      - uart.write: [0xA0, 0x01, 0x00, 0xA1]
      - switch.template.publish:
          id: relay1
          state: OFF
```
