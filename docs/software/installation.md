---
layout: default
title: Firmware Installation
parent: Software
nav_order: 1
---

# Firmware Installation

## Upload Firmware

<a href="https://firmware.frothfet.com"><img src="/assets/provisioning.png" alt="Provisioning UI" class="img-right"></a>

If your board does not come pre-programmed, you will need to upload the firmware.

1. Open the [Firmware Helper](https://firmware.frothfet.com) page
1. Select your board revision
1. Select your firmware version
1. Click **Install Firmware**
1. Select your serial port, click upload
1. Board will reboot, beep, and status will show as <span class="bg-blue-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BLUE</span> on success

## WiFi Provisioning

1. Power your board through USB or external power.
	* The status led should show as <span class="bg-blue-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">BLUE</span> (ready to pair)
1. Open the [Firmware Helper](https://firmware.frothfet.com) page
1. Select either **Configure via BLE** or **Configure via Serial**
1. Enter your WiFi credentials
	* Status led will turn <span class="bg-green-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">GREEN</span> on success.
1. Open your browser to [http://frothfet.local](http://frothfet.local)

{: .note }
If your WiFi changes or the board cannot connect to WiFi, the status led will turn <span class="bg-red-000 text-grey-lt-000" style="border-radius:12px;padding:0.1em 0.5em;">RED</span>  You can hold the **BOOT** button for 10 seconds to switch back into provisioning mode.

## Firmware Update Methods

* Update the firmware using OTA from the web interface
* Use the Firmware Helper linked above to choose a specific version
* Compile from source using instructions below

## Development / Building From Source

1. Clone the [firmware repository](https://github.com/hoeken/frothfet-firmware)
1. Run `npm install` in the repository to get some dev tools
1. Plug your computer into the board
1. Open the repository in VSCode
1. Install the Platformio plugin if needed
1. At the bottom, select your board from the build environments
1. Build and/or upload firmware with the arrow in the upper right.

### ArduinoOTA

This allows you to upload new firmware over wifi from VSCode.

1. Enable Arduino OTA in **Settings -> Miscellaneous** on the board
1. Edit **platformio.ini** and add this to the bottom of your desired board [env:] section

```
; OTA Upload Config, auth password is your admin password
upload_protocol = espota
upload_port = frothfet.local
upload_flags = 
 	--auth=admin
 	--port=3232
```