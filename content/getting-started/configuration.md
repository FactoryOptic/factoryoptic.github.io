---
title: "Configuration"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 20
---

![sdcard](https://github.com/FactoryOptic/factoryoptic.github.io/blob/main/public/images/sdcard.png?raw=true)

On the side of the SYNCRO-LINK is an microSD slot.

The device should contain a card already, but if you need to replace, it should be formatted as FAT32 and can be up to 32GB.

In the SD card is a folder named 'config'. Inside this folder is the config files for the network.

### network.txt
This is the config file for the device network settings.

The file consists of the following 5 lines and can be edited with any text editor.

- Line 1 - IP address for device
- Line 2 - Network subnet
- Line 3 - Network Router
- Line 4 - DNS server
- Line 5 - static or DHCP

In the case of DHCP, it will initially ignore lines 1-4 and attempt to use them if DHCP fails.

Be advised, DHCP can take up to 60 seconds on power-up, so it is recommended that static IP is used.

Below is an example network.txt file

```
192.168.1.174
255.255.255.0
192.168.1.1
192.168.1.1
static
```

### dest.txt
This is the config file for the destination server.

The file consists of the following 2 lines and can be edited with any text editor.

- Line 1 - Destination IP address for the server
- Line 2 - UDP port on server to send to

Below is an example dest.txt file

```
192.168.1.191
3200
```