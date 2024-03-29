# config_Jetson_NX (without SD Card image)
This is the repository for configuring the Jetson Xavier NX by SDK manager and SSD card.

This configuration do not require micro SD card.

If you can use a micro SD card that has 16GB minimum, see Configure F1TENTH System at https://f1tenth.org/build.html.

## Required Equipments
-Jetson Xarvier NX  

-SSD card

-Ubuntu 20.04 host PC  

-Jumper(for convert to recovery mode)  

-5 pin cable  

-HDMI cable

-External monitor/display  

-Keyboard  

-Mouse  

-Wireless router  

-Ethernet cable (needed if Pit/Host laptop does not have WiFi capability)

## Install SDK manager
You can install SDK manager of recent version from https://developer.nvidia.com/drive/sdk-manager.

When you install and run SDK manager, you have to sign in Nvidia account.

## Flash Jetson NX
By executing this process, we can boot Jetson NX to Ubuntu 20.04

After sign in SDK manager, connect Xavier to host PC using 5 pin cable.

<img src = "https://user-images.githubusercontent.com/17681187/216936127-747e84aa-37ac-4db7-ab99-19d6b632491b.jpg" width = "250" height = "350">

Then SDK manager will automatically detect your Xavier.

<img src = "https://user-images.githubusercontent.com/17681187/215978979-bc5e0c19-fe1e-4c2e-95ee-7a01fc32ad4a.png" width = "700" height = "400">
And pick the JetPack version. We picked JetPack5.1.

Click accept button and continue installation.
<img src = "https://user-images.githubusercontent.com/17681187/216929955-a5bb22a0-fe1f-48f8-ba37-addbb6f5b990.png" width = "700" height = "400">

Then you can install necessary packages on host PC.

Now, you should flash your Xavier with the option that manual setup.
When you execute this step, you have to place a jumper across the Force Recovery Mode pins.
These are pins 9 [GND] and 10 [FC REC] of the Button Header [J14].

<img src = "https://user-images.githubusercontent.com/17681187/220860509-854e8040-8366-4940-9f70-b04d668aa3c2.png" width = "300" height = "200">      <img src = "https://user-images.githubusercontent.com/17681187/220863260-bf85ad86-0960-46f2-a2bb-86a01335dc04.jpg" width = "300" height = "200">

Select EMMC as storage device.

<img src = "https://user-images.githubusercontent.com/17681187/216935503-9fc8cc92-3b7f-41fb-9de8-e6671971ba34.png" width = "400" height = "400">  
Connect monitor, keyboard, mouse to Xavier.  

You can check the succeeding of booting of Xavier.    

By this step, ubuntu 20.04 will be installed at SD card built in your Xavier.  
This is the step only for flashing Xavier. Even if you did flash your Xavier, JetPack is not installed in Xavier.  
Because EMMC inside Jetson Xavier NX has 16GB of storage space that is not enough to install all pakages, you should configure root disk to external SSD.  

<img src = "https://user-images.githubusercontent.com/17681187/220870706-96d9f9cb-3b0a-4c6a-af20-284503053f21.png" width = "700" height = "400">  


## Change root disk    
From now, host PC will not be used.   
You can reference https://github.com/jetsonhacks/rootOnNVMe.  

 
Using keyboard and mouse connected to Xavier, enter the setting "disks".  
If your SSD has several partitions, merge to one those and format disk.     
<img src = "https://user-images.githubusercontent.com/17681187/221497402-a9cc2235-8408-4c7a-a5dd-75fea97c1060.png" width = "400" height = "300">  
Then, create partition clicking "+" button as Ext4 type.   

Open the terminal and use following commands.

```bash
git clone https://github.com/jetsonhacks/rootOnNVMe.
cd rootOnNVMe
./copy-rootfs-ssd.sh
./setup-service.sh
sudo reboot now
```

## Install JetPack on Xavier  
For install JetPack, using this command.
```bash
sudo apt update
sudo apt install nvidia-jetpack
```
