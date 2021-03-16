---
title: "Display"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 30
---

### SYNCRO-LINK Display

![Display](/images/display.png)

The display has a single page for showing the following information

- On the top bar
    - UDP will indicate whenever UDP packets are streaming
    - Firmware version is shown on the right
- On the left
    - ip address of SYNCRO-LINK
    - ip address of destination server
    - port on destination server
        - DHCP will show next to port if DHCP has been configured
    - mac address of SYNCRO-LINK
- On the right
    - SYNC input format
        - Note, for UHD/4K, cameras will typically accept 1080 formats as Tri-Level sync for resolutions above 1080 do not exist.
        - When SYNC is not present, this line will go blank
        - For any formats not supported, the format will be surrounded by \*, for example \*1080P/60\*
    - LTC/Timecode
        - This should appear and change every frame when timecode is present
        - When timecode is no longer connected, the last timecode received will show
    - Lens Name
        - This is the name provided by the lens data connection
        - This line will go blank when lens connection is removed
    - Focal length
        - This will show lens focal length in mm
- Notes
    - During bookup, if no SD card is present, or SD card is missing config files or config files are not properly formatted, message will appear on device "SD Card not present"
        - insert card and reboot device
