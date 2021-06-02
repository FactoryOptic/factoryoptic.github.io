---
title: "Display"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 30
---

### SYNCRO-LINK Display

The SYNCRO-LINK has an onboard OLED display that displays useful information.

#### Page 1

![page 1](/public/images/syncrolink_page1.png)

- On the top bar
    - UDP will indicate whenever UDP packets are streaming, usually takes 45-60 seconds afterbootup if the network settings are correct
    - Firmware version is shown on the right
- On the left
    - ip address of SYNCRO-LINK
    - ip address of destination server
    - port on destination server
        - DHCP will show next to port if network is configured as DHCP
    - mac address of SYNCRO-LINK
- On the right
    - LTC/Timecode
        - This should appear and change every frame when timecode is present
        - When timecode is no longer connected, the last timecode received will show
        - LTC is limited to 30 frames max, but when operating in double-rate video formats, such as 47.96, 48, 50, 59.94 or 60, SYNCRO-LINK will convert UDP packet timecode at the double rate, but the display will only show actual timecode. 
    - SYNC input format
        - Note, for UHD/4K, cameras will typically accept 1080 formats as Tri-Level sync for resolutions above 1080 do not exist.
        - When SYNC is not present or format is not supported, this line will go blank
    - Lens Name
        - This is the name provided by the lens data connection
        - This line will go blank when lens connection is removed
    - Lens Firmware Version
        - This will show the current firmware version as reported by the lens
- Notes
    - During boot-up, if no SD card is present, or SD card is missing config files or config files are not properly formatted, message will appear on device "SD Card not present"
        - insert card and reboot device

#### Page 2

![page 2](/public/images/syncrolink_page2.png)

- On the left
    - Focus distance
    - Lens t-stop
        - Readings are displayed in common aperture scale, with tenths resolution between marks. So 4-5 would be a T4 to T5.6 split
    - Zoom focal length
    - Entrance pupil
        -this is a signed number, showing the distance of the entrance pupil from the film plane, with negative numbers being behind the film plane. 
        
#### Page 3

![page 3](/public/images/syncrolink_page3.png)

- On the left
    - Lens manufacturer
    - Lens serial number
    - Lens Owner
    
#### Page 4

![page 4](/public/images/syncrolink_page4.png)

- On the left
    - PoE Voltage
    - DC Voltage
    - Streaming Format
    
- On the right
    - LTC
    - UTC date & time of day
    - SYNCRO-LINK Firmware version
    - SYNCRO-LINK firmware generation date and time