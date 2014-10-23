###5 Steps to install nodejs & npm from the terminal in a udoo quad core runing udoobuntu

	sudo apt-get install git-core python libssl-dev build-essential
	git clone git://github.com/joyent/node.git node && cd node
	git checkout v0.10.22
	./configure --without-snapshot
	make        (it will take some time - 40min)
	sudo make install