RPi Fury-Miner
==============

---------------------------------------------------------------------------------------

Setup guide for installing zencontroller in a raspberry pi with a Gawminer Fury 1.3mhz
tutorial by: fito_segrera
07-25-2014

---------------------------------------------------------------------------------------

1. Download the following raspberryPi Image:

	https://docs.google.com/document/d/1UilAJ3wMOgoHFqz9e1zhOvz79KQDascYaC6Aq3sbmqg

2. You need to format a SD card with the downloaded img file. If you are in MAC you can download Raspberry Pi SD installer from:

	https://github.com/RayViljoen/Raspberry-PI-SD-Installer-OS-X

You can also use other terminal commands in either Linux or OSX to do this. Also some SD formating softwares are available for all platforms. Check the following link for more information:

	http://elinux.org/RPi_Easy_SD_Card_Setup

3. Unzip Raspberry-PI-SD-Installer-OS-X-master.zip and copy the downloaded image on step 1 (rpi_genA.img) into the Raspberry-PI-SD-Installer-OS-X-master folder.

4. Insert Open a terminal window and cd into the Raspberry-PI-SD-Installer-OS-X-master folder. Once inside the folder execute te following command in the terminal:

	sudo ./install rpi_genA.img

5. You will see a terminal interface with a list of your storage devices. Select the one that corresponds to the SD by pressing the number related to it.

	WARNING: Be sure that you are selecting the correct option, otherwise you can erase your hardrive or any partition within it.

6. Wait until the process is over. DON'T CLOSE THE TERMINAL until the process stops. I might take around 5 to 10 mins.

7. Once the image is formated into the SD card and the process is finished, take the SD card, put it into the raspberry Pi, connect your raspberry Pi to your router with an ethernet cable and power it.

8. Power and Connect your Gawminer Fury to your raspberry Pi with the USB cable. Go to https://www.zenminer.com and create a new account; username and password. Log in... Click the add miner button and it should show up, it may take a while for it first to show up but it will (also try refreshing)

9. 	Go to "Pools" and configure your pool address, username and password.

10. Go to "Miner" and select "change hardware"; select FURY. Save and restart the process. 

---------------------------------------------------------------------------------------

More info on this topic: [https://bitcointalk.org/index.php?topic=644921.0]([https://bitcointalk.org/index.php?topic=644921.0)



