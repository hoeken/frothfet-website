---
layout: default
title: Revision F
parent: Hardware
nav_order: 1
---

# Revision F

## Core capabilities:

<a href="/assets/FrothFET Rev F Finished.jpg"><img src="/assets/FrothFET Rev F Finished.jpg" alt="FrothFet Assembled Board" class="img-right"></a>

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

## Power Input

FrothFET can take power from 12v to 30v, which makes it compatible with both 12v and 24v systems, both lead acid and LFP battery systems.  

FrothFET has a positive and negative busbar.  The positive busbar is longer than the negative busbar.  On each busbar is a M8 bolt for attaching the main power cables.  The positive connection can also be fitted with a MEGA fuse.

Each busbar also has 8 connections to the board via M4 screws.  These screws are connected directly to the busbar and can be used for wiring your system.  DC loads can be grounded to an external ground, or wired to the bus bar connection for each channel.

{: .warning}
FrothFET does **NOT** have reverse polarity protection, so it is essential to make sure you do not mix up the positive and negative connections when powering the board.

## Rev F Pinout (click to enlarge)

[![FrothFET Rev F Pinout](/assets/FrothFET Rev F Pinout.png)](/assets/FrothFET Rev F Pinout.pdf)

## Source Files

* [FrothFET Github Repository](https://github.com/hoeken/frothfet)
* [FrothFET Rev F Schematic](https://github.com/hoeken/frothfet/blob/main/schematics/FrothFET%20Rev%20F.pdf)
* [3D Printable Case](https://github.com/hoeken/frothfet/blob/main/models/FrothFet%20Rev%20F%20Case.step)


# Manufacturing

If you would like to manufacture your own boards, follow the instructions below:

## Kicad File Preparation

- Install the Kicad `Fabrication Toolkit` plugin.
- From the PCB Editor, open `Tools -> External Plugins -> Fabrication Toolkit`
- Click `Generate` to create the production files.
- Upload the {board_name}.zip file in the first step of the JLC ordering process
- {board_name}_bom.csv file is the Bill of Materials for PCBA
- {board_name}_positions.csv file is the Component Placement file for PCBA

## JLCPCB Ordering Options

If no option is specified below, use the default options provided by JLCPCB.

### PCB

* PCB Color: Blue
* Surface Finish: ENIG
* Copper Weight: 2oz

### Assembly

* Depanel Boards: YES
* PCBA Remark - attach image below
* PCBA Remark - add the text below

```
After production, insert the following parts:
F??-F?? - LCSC ???
```

![Manufacturing Instructions](/assets/FrothFET Rev F PCBA Instructions.png)