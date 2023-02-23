# config_Jetson_NX
This is the repository for configuring the Jetson Xavier NX by SDK manager.

This configuration do not require SD card.

If you have a SD card that has 16GB minimum, see Configure F1TENTH System at https://f1tenth.org/build.html.

## install SDK manager
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

Now, you have to flash your Xavier. 

<img src = "https://user-images.githubusercontent.com/17681187/216935503-9fc8cc92-3b7f-41fb-9de8-e6671971ba34.png" width = "400" height = "400">

