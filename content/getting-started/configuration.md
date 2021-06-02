---
title: "Configuration"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 20
---

![sdcard](https://github.com/FactoryOptic/factoryoptic.github.io/blob/main/public/images/sdcard.png?raw=true)

On the side of the SYNCRO-LINK is an microSD slot with a factory installed memory card.

The device should contain a card already, but if you need to replace, it should be formatted as FAT32 and can be up to 32GB.

In the SD card is a folder named 'config'. Inside this folder is the config files for the network.

A fresh copy of the SD Card can be found [here](https://github.com/FactoryOptic/syncrolinkSDCard)

```
sd card
|   readme.md #this file
+---config
    |---dest.txt #required
    |---NETWORK.LOG #optional, will be created if missing and appended to if exists
    |---network.txt #required
    |---ntp.txt #optional
    |---stream.txt #optional
```

### network.txt
This is the config file for the SYNCRO-LINK network settings.

The file consists of the following 5 lines and can be edited with any text editor.

- Line 1 - IP address for SYNCRO-LINK
- Line 2 - Network subnet
- Line 3 - Network DHCP server or Router IP address
- Line 4 - DNS server
- Line 5 - static or DHCP

In the case of DHCP, it will initially ignore lines 1-4 and attempt to use them if DHCP fails.

DHCP can take up to 60 seconds on power-up, so it is recommended that static IP is used.

Below is an example network.txt file

```
192.168.1.100
255.255.255.0
192.168.1.1
192.168.1.1
static
```

### dest.txt
This is the config file for the destination server, which is the machine running the Unreal Engine plugin or other software that is waiting to accept UDP packets.

The file consists of the following 2 lines and can be edited with any text editor.

- Line 1 - Destination IP address for the server
- Line 2 - UDP port on server to send to (1024 - 65535)

Below is an example dest.txt file

```
192.168.1.200
20000
```

### ntp.txt (optional)
The SYNCRO-LINK doesn't contain a battery backed up real time clock, but can connect to an NTP server for getting updated time of day upon powerup. This is not required for operation, but for the LOG file timestamp.

If ntp.txt file doesn't exist, SYNCRO-LINK will attempt to obtain time from pool.ntp.org. If SYNCRO-LINK is on an air-gapped network or doesn't have internet access (recommended configuration), simply setup any linux machine to be an NTP server and use that IP address, if needed.

Note: If the request for NTP time fails, SYNCRO-LINK will default to Jan 1, 2019.

The file consists of the following 1 line and can be edited with any text editor.

Line 1 - IP address for NTP server
Below is an example ntp.txt file

```
192.168.1.10
```

### stream.txt (optional)
This is the config file for user selecting the streaming format. 

If file doesn't exist, SYNCRO-LINK will default to F3. 

The file consists of one line and can be edited with any text editor.

Line 1 - hex value of streaming format
Below is an example stream.txt file
```
F3
```