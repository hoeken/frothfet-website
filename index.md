---
layout: default
title: Overview
nav_order: 1
---

# Open Hardware Load Controller

FrothFET is a DC load controller for doing digital switching of loads on your boat. With this board, you can control almost any type of DC load on your boat.

## Specifications:

<a href="/docs/hardware/revision-f"><img src="/assets/FrothFET Rev F Finished.jpg" alt="FrothFET Board Assembled" class="img-right"></a>

* 8 x separately controllable load driver channels with:
  * 20A current maximum per channel (with fans!)
  * Built-in ATC fuses with bypass mode
  * Current monitoring accurate to about 0.01A on each channel
  * Firmware supports soft fuses to protect from overcurrent per-channel and overall
  * Voltage sensing (run detection + fuse failure + bypass detection)
  * PCB made with heavy duty 2oz copper, 4 layers, and thick copper busbars to handle big loads
  * M4 (#8) screw terminals for secure and easy setup
  * dimmable with PWM control
* 12v to 30v supply voltage (supports both lead acid and lithium battery systems in either 12v or 24v configuration)
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