---
layout: default
title: Overview
nav_order: 1
---

# Open Hardware Load Controller

FrothFET is a DC load controller for doing digital switching of loads on your boat. With this board, you can control almost any type of DC load on your boat.

## Specifications:

<a href="/docs/hardware/revision-f"><img src="/assets/FrothFET Rev F Finished.jpg" alt="FrothFET Board Assembled" class="img-main"></a>

* 8 x load driver channels with:
  * 20A max current per channel
  * Built-in ATC fuses with bypass mode
  * Current monitoring accurate to 0.01A
  * Firmware supports soft fuses to protect from overcurrent
  * Voltage sensing (run detection + fuse failure + bypass detection)
  * PCB made with heavy duty 2oz copper, 4 layers, and thick copper busbars
  * M4 (#8) screw terminals for secure and easy setup
  * dimmable LED support with gamma aware fading
* 12v to 30v supply voltage
  * Supports both lead acid and lithium battery systems in either 12v or 24v configuration
* 100A total system power (beefy copper busbar)
* easy system fusing with optional MEGA fuse on busbar.
* 2x cooling fan headers for standard 5v PC fans
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