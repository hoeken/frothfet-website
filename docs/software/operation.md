---
layout: default
title: Operation
parent: Software
nav_order: 3
---

# Operation

You can access the firmware at [http://frothfet.local](http://frothfet.local) ([http://frothfet](http://frothfet) on Android) or by entering the IP address.  The IP address and hostname are printed out over the serial port at startup.  You should see an interface similar to this:

![FrothFET UI](/assets/FrothFET UI.png)

## Load Control

You can turn a load on/off by clicking the button with its name.  If a load is dimmable, it will have a slider that you can use to adjust the duty cycle / brightness.

If a load enters the <span class="bg-yellow-100 text-grey-dk-300" style="border-radius:12px;padding:0.1em 0.5em;">TRIPPED</span> or <span class="bg-red-100 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BLOWN</span> state, you can click the button to reset the channel.  Make sure to investigate the cause of the trip or the state of the fuse before switching the load back on.

## Channel Modes

A channel can be in one of the following states:

- <span class="bg-grey-lt-200 text-grey-dk-200" style="border-radius:12px;padding:0.1em 0.5em;">OFF</span> - Load is disconnected from supply voltage.
- <span class="bg-green-100 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">ON</span> - Load is connected to supply voltage.
- <span class="bg-blue-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BYPASSED</span> - Channel is off, but voltage is detected on the output side.
- <span class="bg-yellow-100 text-grey-dk-300" style="border-radius:12px;padding:0.1em 0.5em;">TRIPPED</span> - Software overcurrent limit exceeded, channel turned off.  Click to reset.
- <span class="bg-red-100 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BLOWN</span> - Channel is on, but no voltage detected on output side.  Check for shorts, replace fuse and click to reset.
- <span style="background-color:#f97316;color:#fff;border-radius:12px;padding:0.1em 0.5em;">OVERHEAT</span> - Channel is too hot, temporarily disabled.  Install cooling fans or wait for temperature to drop.

**TODO** - add a screenshot of page with all the states demonstrated.