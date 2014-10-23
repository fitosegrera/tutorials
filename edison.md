Edison Cheat-sheet
==================

###Connecting to the Edison via linux:

1. Plug both micro USB cables to both the edison and the source computer where you are working on.
2. Once the edison appears in your file explorer as an external USB device go to your "edit connections", select the wired connection created by the Edison and click on Edit. Then go to the IPV4 tag and click on "add", and add the following: 

2.1. Adress --> 

	192.168.2.1

2.2. Netmask -->

	255.255.255.255

2.3. Gateway -->

	0.0.0.0

Click save. Got to your terminal and type:

	ssh root@192.168.2.15

And login!!

###Commands

####Launch Edison's Server
To start the edison's pre-configured server:

	configure_edison --server

Then go to browser and type: 

	192.168.2.15

To unblock any interface (wlan0, eth0, etc.): 	

	rfkill list all

	rfkill unblock all

Other stuff

	ip link show up

####Using connman:

Enable connman (wifi config):

	systemctl enable connman  
	
	systemctl start connman

Scan wifi:

	connmanctl scan wifi

List Scanned Networks:

	connmanctl services

Connect to open network:

	connmanctl connect wifi_dc85de828967_4d6568657272696e_managed_none

__CONECTING TO SECURE WIFI WITH CONNMAN:__

Connecting to a protected access point. For protected access points you will need to provide some information to the ConnMan daemon, at the very least a password or a passphrase. The commands in this section show how to run connmanctl in interactive mode, it is required for running the agent command. To start interactive mode simply type:

	$ connmanctl

You then proceed almost as above, first scan for any Wi-Fi technologies:

	connmanctl> scan wifi

To list services:

	connmanctl> services

Now you need to register the agent to handle user requests. The command is:

	connmanctl> agent on

You now need to connect to one of the protected services. To do this it is very handy to have a terminal that allows cut and paste. If you were connecting to OtherNET in the example above you would type:

	connmanctl> connect wifi_dc85de828967_38303944616e69656c73_managed_psk

The agent will then ask you to provide any information the daemon needs to complete the connection. The information requested will vary depending on the type of network you are connecting to. The agent will also print additional data about the information it needs as shown in the example below.

	Agent RequestInput wifi_dc85de828967_38303944616e69656c73_managed_psk
		Passphrase = [ Type=psk, Requirement=mandatory ]
		Passphrase?  

Provide the information requested, in this example the passphrase, and then type:

	connmanctl> quit

####Install nano text editor:

This command downloads and builds the nano text editor on the Edison:

	wget http://www.nano-editor.org/dist/v2.2/nano-2.2.6.tar.gz && tar xvf nano-2.2.6.tar.gz && cd nano-2.2.6 && ./configure && make && make install