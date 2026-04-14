---
layout: default
title: API & Integrations
parent: Software
nav_order: 4
---

# API & Integrations

## MQTT

Publishes all available information under topic: `yarrboard/frothfet/*`

### Home Assistant

To use FrothFET with Home Assistant, follow these steps:

* Install the Mosquitto Broker (MQTT server) app in Home Assistant.
* Enable MQTT discovery in Home Assistant
* In FrothFET, enable MQTT and the Home Assistant features
* In Home Assistant, it should show the discovered watermaker

[Download the Home Assistant dashboard YAML here](/assets/brineomatic-home-assistant.yaml)

![Home Assistant Dashboard](/assets/brineomatic home assistant dashboard.png)

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
{"cmd":"set_channel","id":0,"state":true,"user":"admin","pass":"admin"}
{"cmd":"login","user":"admin","pass":"admin"}
{"cmd":"set_channel","id":0,"state":true}
{"cmd":"set_channel","id":0,"duty":0.99}
{"cmd":"set_channel","id":0,"duty":0.5}
{"cmd":"set_channel","id":0,"duty":0.1}
{"cmd":"set_channel","id":0,"state":false}
```

For detailed information on the Brineomatic specific protocol, see ```src/controllers/PWMChannelController.cpp```

Visit the [YarrboardFramework documentation](https://github.com/hoeken/YarrboardFramework#protocol) page for more details on the underlying protocol.

## SignalK
All the same data as MQTT, but in SignalK delta format with the `???/frothfet/*` path.