Kivy: Python for Android and iOS
================================
This tutorial goes over the basics of KIVY, installation, usage and how to write an Android or iOS APP.
This process has been tested in Ubuntu 13.10

###Dependencies
-python
-pygame

###Installation
Once you have all the dependencies installed, go to a terminal and add the repository for kivy. Any of the following two should work (more information at [LINK](http://kivy.org/docs/installation/installation-linux.html#ubuntu-11-10-or-newer):

	sudo add-apt-repository ppa:kivy-team/kivy

	sudo add-apt-repository ppa:kivy-team/kivy-daily

To install kivy on python 2.*:

	sudo apt-get install python-kivy

To install kivy on python 3.*:

	sudo apt-get install python3-kivy

To get the examples:

	sudo apt-get install kivy-examples

###Writing an APP for Android
1.Create a new python script and name it 

	main.py

To create a buildozer.spec file:

	buildozer init

To build the Android app go to terminal and write:

	buildozer android debug

If you want to push the compiled app to your phone add "deploy" to the previous line:

	buildozer android debug deploy

###LINKS

+ [KIVY](http://kivy.org/#home)
+ [Quick Start Guide](http://kivy.org/docs/guide/quickstart.html)
+ [Crash Course](http://inclem.net/pages/kivy-crash-course/)
+ [CRASH VIDEO](https://www.youtube.com/watch?v=t8N_8WkALdE)