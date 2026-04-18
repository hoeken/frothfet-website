---
layout: default
title: Overview
nav_order: 1
---

# Open Hardware Load Controller

FrothFET is a DC load controller for doing digital switching of loads on your boat. With this board, you can control almost any type of DC load on your boat.

## Specifications:

<a href="/docs/hardware/revision-f"><img src="/assets/FrothFET Rev F Finished.jpg" alt="FrothFET Board Assembled" class="img-main"></a>

* 8 x separately controllable channels
* 20A current maximum per channel (with fans)
* Built-in ATC fuses with bypass mode
* Per channel current monitoring, accurate to 0.01A
* Soft fuses and short protection
* Run detection + Fuse failure + Bypass detection
* Heavy 2oz copper PCB + thick bus bars
* M4 (#8) screw terminals for secure and easy setup
* Dimmable controls for LED lighting
* 12v to 30v supply voltage (lead acid and lithium)
* 100A total system power (beefy copper busbar)
* easy system fusing with optional MEGA fuse on busbar.
* 2x cooling fan headers with PWM or on/off control
* 3D printable case w/ design files
* ESP32-S3 controller with WiFi, Bluetooth, USB-C, etc.

## Integrations
- MQTT publishing
- SignalK 
- Home Assistant
- HTTP/REST endpoints  
- WebSocket real-time control

### User Interface
![FrothFET - Typical interface](/assets/FrothFET UI.png)