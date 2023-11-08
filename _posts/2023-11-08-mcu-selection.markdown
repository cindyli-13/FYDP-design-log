---
layout: post
title:  "MCU Selection"
date:   2023-11-08 14:19:00 -0400
categories: jekyll update
---

For compute we want to take advantage of the Wi-Fi and Bluetooth capabilities of the ESP32 families of microcontrollers. Specifically, we chose the ESP32-S3 microcontroller since it is the most high-end family out of the ESP32 microcontrollers. With its dual-core CPUs, we can potentially run our Wi-Fi processing on one core and sensor processing on the other core.

The ESP32-S3-WROOM-2 module includes onboard antenna, flash, and SRAM, which can be easily integrated into our custom PCB design.

![esp32-s3-wroom-2]({{site.baseurl}}/assets/images/ESP32-S3-WROOM-2-N16R8V_SPL.png)

For development, we will use the ESP32-S3-DevKitC-1 which embeds the ESP32-S3-WROOM-2 module.

![esp32-s3-devkitc-1]({{site.baseurl}}/assets/images/esp32-s3-devkitc-1-v1-isometric.png)

### References
- [ESP32-S3-WROOM-2 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-2_datasheet_en.pdf)
