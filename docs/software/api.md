---
layout: default
title: API & Integrations
parent: Software
nav_order: 4
---

# API & Integrations

## MQTT

Publishes all available information under topic: `yarrboard/frothfet/pwm/{channel-key}/*`

| Field | Type | Description |
|---|---|---|
| `state` | string | <span class="bg-green-100 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">ON</span> / <span class="bg-grey-lt-200 text-grey-dk-200" style="border-radius:12px;padding:0.1em 0.5em;">OFF</span> / <span class="bg-yellow-100 text-grey-dk-300" style="border-radius:12px;padding:0.1em 0.5em;">TRIPPED</span> / <span class="bg-red-100 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BLOWN</span> / <span class="bg-blue-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BYPASSED</span> / <span style="background-color:#f97316;color:#fff;border-radius:12px;padding:0.1em 0.5em;">OVERHEAT</span> |
| `source` | string | What last changed the channel state (e.g. `manual`, `mqtt`, `serial`, `timer`) |
| `duty` | float | PWM duty cycle from 0.0 to 1.0 - Only present if the channel is dimmable. |
| `voltage` | float | Channel voltage in volts |
| `current` | float | Channel current in amps |
| `wattage` | float | Channel power in watts |
| `temperature` | float | Channel temperature in °C |
| `aH` | float | Accumulated amp-hours since last reset |
| `wH` | float | Accumulated watt-hours since last reset |

### Home Assistant

To use FrothFET with Home Assistant, follow these steps:

* Install the Mosquitto Broker (MQTT server) app in Home Assistant.
* Enable MQTT discovery in Home Assistant (Settings → Devices & Services → MQTT)
* In FrothFET, enable MQTT and the Home Assistant features
* In Home Assistant, it should show the discovered FrothFET device
* Each channel will be listed as an appropriate entity that can be controlled by Home Assistant.
* FrothFET also provides voltage, current, and wattage for each channel as entities.

## Raw API

The protocol for communicating with Yarrboard is entirely based on JSON messages. Each request to the server should be a single JSON object, and the server will respond with a JSON object.

The protocol works over the following transport layers:

* HTTP API
* Websockets
* USB Serial
* MQTT

Here are some example commands you could send:

```
{"cmd":"ping"}
{"cmd":"get_config","value":true,"user":"admin","pass":"admin"}
{"cmd":"set_channel","key":"galley-light","state":true,"user":"admin","pass":"admin"}
{"cmd":"login","user":"admin","pass":"admin"}
{"cmd":"set_channel","key":"galley-light","state":true}
{"cmd":"set_channel","key":"galley-light","duty":0.99}
{"cmd":"set_channel","key":"galley-light","duty":0.5}
{"cmd":"set_channel","key":"galley-light","duty":0.1}
{"cmd":"set_channel","key":"galley-light","state":false}
```

For detailed information on the FrothFET PWM protocol, see ```src/controllers/PWMChannelController.cpp```

Visit the [YarrboardFramework documentation](https://github.com/hoeken/YarrboardFramework#protocol) page for more details on the underlying protocol.

## SignalK
All the same data as MQTT, but in SignalK delta format. The specific SignalK path is coming soon.