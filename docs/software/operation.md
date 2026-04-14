---
layout: default
title: Operation
parent: Software
nav_order: 3
---

# Operation

You can access the firmware at [http://frothfet.local](http://frothfet.local) ([http://frothfet](http://frothfet) on Android) or by entering the IP address.  The IP address and hostname are printed out over the serial port at startup.  You should see an interface similar to this:

![FrothFET UI](/assets/frothfet-ui.png)

## Load Control

Interaction with FrothFET is limited to turning a load on or off, changing the brightness (or pwm) of a light, or resetting a tripped or blown channel.

## Channel Modes

A channel can be in one of the following states:

- **OFF** - Load is disconnected from supply voltage.
- **ON** - Load is connected to supply voltage.
- **BYPASSED** - Channel is off, but voltage is detected on the output side.
- **TRIPPED** - Software overcurrent limit exceeded, channel turned off.  Click to reset.
- **BLOWN** - Channel is on, but no voltage detected on output side.  Check for shorts, replace fuse and click to reset.
- **OVERHEAT** - Channel is too hot, temporarily disabled.  Install cooling fans or wait for temperature to drop.