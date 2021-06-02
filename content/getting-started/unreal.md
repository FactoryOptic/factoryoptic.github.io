---
title: "Unreal Engine"
date: 2021-03-15 23:51:07
lastmod: 2021-03-15 23:37:48
publishdate: 2021-03-15 23:37:51
draft: false
weight: 30
---

The SYNCRO-LINK MARK-ZERO makes use of the LONET-Unreal-Plugin created by Andy Jaroz of LOLED VIRTUAL

### UE4.26 install
- Download the 1.50 plugin from LOLED VIRTUAL'S Github site: [https://loledvirtual.com/documentation/docs/unrealreleases/](https://loledvirtual.com/documentation/docs/unrealreleases/)
- Create a directory named 'plugins' in your Unreal project folder, if it doesn't already exist
- Unzip the file to the plugins directory

### Open project in Unreal Engine
- When you launch Unreal, open your project
- Unreal may warn that files are missing, you can select compile from source to generate if needed
- Unreal will let you know new plugins are available, make sure the LONET plugin is enabled

### LiveLink
- Open LiveLink
![LiveLink1](/public/images/livelink1.png)
- Select '+ Source', then LOLED LiveLink, set the port number to the UDP port you configured in dest.txt file 
   - be sure to click OK button to close
- If the SYNCRO-LINK is configured properly and streaming UDP packets, you will see 4 green dots as shown below
![LiveLink2](/public/images/livelink2.png)
- If you click on the ..._Lens@... subject, under view options, you can show live frame data
- As you rotate the lens, you should see these values changing, top field is focus distance in mm
- If data is updating, then everything should be good with LiveLink

### Configure XDClient
- XDClient should be present in your project, looking at the 'World Outliner', which shows all the actors in the current level
- Under 'Details' find the four components
   - Under XDDistortionLiveLink, set Subject Representation to ..._Distortion...
   - Under XDHeightLiveLink, set Subject Representation to ..._ImageHeight...
   - Under XDShadingLiveLink, set Subject Representation to ..._Shading...
   - Under XDLensLiveLink, set Subject Representation to ..._Lens...
![XDClient](/public/images/xdclient1.png)

### Configure Blueprint
- Under XDClient Details, select the blue 'Edit Blueprint' button
- The Blueprint should look like this
![blueprint](/public/images/blueprint.png)
- Find the Make Fx Fy section
   - Enter the 'Sensor Res X' as the video width being ingested into Unreal
      - Note, the sensor may have higher resolution than what is sent out the HDMI/HDSDI and it's important to provide the resolution of the video stream, which may be different than the sensor resolution.
   - Enter the 'Sensor Res Y' as the video height being ingested into Unreal
   - Enter the 'Sensor Size X' as the width in mm of the sensor's active area being used to capture the resolution.
     - It is important to take into account any scaling and cropping being done to determine the active area of the sensor for these values. Consult the camera manufacturer's information. 
![Pixel Resolution](/public/images/pixel1.png)

- Find the Distortion section and set the subject to ..._Distortion...
![Distortion](/public/images/distortion.png)

- Find the Image Height section and set the subject to ..._ImageHeight...
![Image Height](/public/images/imageheight.png)

- Find the Distortion section and set the subject to ..._Shading...
![Shading](/public/images/shading.png)

- Find the Distortion section and set the subject to ..._Lens...
![Lens](/public/images/lens.png)

- When you hit 'Play', you should see orange lines with data blobs flowing in & out of the 'Evaluate Live Link Frame' boxes. At this point, everything is connected and data is streaming.


### Confirm CineCameraActor is updating
- At this point, close the blueprint and back in your project click on CineCameraActor. The window showing the actual focal length of the lens. If it matches, everything is configured. 
![CineCameraActor](/public/images/cinecameraactor.png)
- If the film back settings don't match, you can update them

