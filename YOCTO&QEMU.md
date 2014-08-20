YOCTO-LINUX & QEMU
==================

Tutorial on how to run a YOCTO Linux pre-built image using QEMU as an emulator console.

1.open the directory called "yocto_qemu", you will see 2 files and one more folder:

	/toolchain
	core-image-minimal-qemuarm.ext3
	zImage-2.6.37-qemuarm-1.0.bin

2.Open a terminal and go to the toolchain directory

	cd /PATH/TO/TOOLCHAIN/DIRECTORY

In our case:

	cd /yocto/toolchain/

where the toolchain file is located...

3.To run the toolchain script type on your terminal:

	./poky-eglibc-x86_64-core-image-sato-armv5te-toolchain-1.6.1.sh

Make the install folder as default (/opt/poky/1.6.1....Wait untill the process finishes...

4.Establish the path of the runqemu executable:

	PATH=/opt/poky/1.6.1/sysroots/x86_64-pokysdk-linux/usr/bin:$PATH 

5.On the terminal write the following commands:
	
	type runqemu

You should see something like:

	runqemu is /opt/poky/1.6.1/sysroots/x86_64-pokysdk-linux/usr/bin/runqemu

6.Go from the toolchain folder to the yocto folder: 

	cd ..

7.Set the source file:

	source /opt/poky/1.6.1/environment-setup-armv5te-poky-linux-gnueabi

8.Run QEMU:

	runqemu qemuarm zImage-2.6.37-qemuarm-1.0.bin core-image-minimal-qemuarm.ext3

