RFduino - Ubuntu
================

Due to the lack of support and docummentation from the RFduino developers about linux compatibility, I decided to make a step by step guide of my own process while making the board work on ubuntu 13.10.

####Steps
1.Install Wine

	sudo apt-get install wine

2.Configure Wine in ubuntu: Hit the super key to run the search tool; or launch it from your side bar. Then type "wine" and select "Configure Wine". This will crete a ".wine" hidden folder in your home directory. We will need to deal with it later on.

3.Assuming that your RFduino will show up under "/dev/ttyUSB0" (that's how mine shows and many other people I've read about on web forums)... :

	ln -s /dev/ttyUSB0 ~/.wine/dosdevices/com1

__Note:__ To make sure how your RFduino shows in your serial port, go to a terminal and type:

	dmesg | grep tty

4.Download and uncompress arduino 1.5.7 BETA for your Linux architechture x32 or x64 [DOWNLOAD](http://arduino.cc/en/pmwiki.php?n=main/software)

5.Download and unzip RFduino.zip [DOWNLOAD](http://www.rfduino.com/download-rfduino-library/)

6.In the RFDuino folder, open platform.txt and select replace all '\' with '/' and save file.

7."cd" into the RFduino folder and change the privileges of the RFDLoader file:

	chmod +x RFDloader

8.Move RFduino to the Arduino folder:

	mv /path/to/RFduino /path/to/arduino-1.5.5/hardware/arduino/

__Note:__ If you already have another version of arduino installed and a fodler for it in your /home directory, repeate step 8 but this time copy the RFduino folder to your other arduino folder in the same path:

	mv /path/to/RFduino /path/to/yourOtherArduinoFolder/hardware/arduino/

This worked for me, though I'm not sure why it is necessary!! ;)

10.Finally we need to tell wine the path of the RFDLoader file. So go to your RFduino folder (if you have two arduino versions or more, remember to do this step to all of them), open your RFDLoader file with a text editor (NOT the RFDLoader.exe), select all the code there and delete it. Now copy and paste the following code to it:

	/usr/bin/wine /home/USERNAME/arduino-1.5.7/hardware/arduino/RFduino/RFDLoader.exe $1 com1 $3

This is assuming you have your recently downloaded "arduino-1.5.7" folder in your "/home/username" directory. Remember to replace "USERNAME" with your own.

I know it is a crazy thing that an opensource openhardware project like RFduino doesn't support Linux in a clear way. This steps worked for me...

Hope this help!!!
