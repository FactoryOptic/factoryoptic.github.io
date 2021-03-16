---
title: "Unreal Engine"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 30
---

At the moment, Factory Optic is working on an Unreal Engine Plugin that supports all the available data from the lens. This will be complted by product launch.

In the meantime, we are supporting an Open Source plugin.

### UE4.25 install
- Download the 4.25 plugin here: http://loledvirtual.com/documentation/files/unreal/LONET-Unreal-Pluginv1.3.2binaries.zip
- Create a directory named 'plugins' in your Unreal project folder, if it doens't already exist
- Unzip the file to the plugins directory

### UE4.26 install
- Download the 4.26 plugin here: http://loledvirtual.com/documentation/files/unreal/LONETClient1.4.zip
- Create a directory named 'plugins' in your Unreal project folder, if it doens't already exist
- Unzip the file to the plugins directory

### LiveLink
- When you launch Unreal, open your project and open Live Link
    - If Live Link plugin is not installed/enabled, be sure to enable it
- Add a source, select the LOLED as the source
- For the IP:port, you only need to specify the port, for example '0.0.0.0:3200'
- At the moment, the limitation will be only Focus, Iris and Zoom positions will be received
- The packet does support 6 data values to be streamed, so the other 3 values are Entrance Pupil, Near Focus Distace and Far Focus Distance.