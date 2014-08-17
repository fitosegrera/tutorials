Installing OpenCV 2.4.8 on Mac OSX with Python Support
------------------------------------------------------

Tutorial created by jjyap at: [LINK](http://jjyap.wordpress.com/2014/02/21/installing-opencv-2-4-8-on-mac-osx-with-python-support/)

####Install openCV

1.First of all I’ll be using the package manager Homebrew to simplify things, you can get it here: [http://brew.sh/](http://brew.sh/)

2.Once you have brew installed you can go ahead and and add homebrew/science which is where OpenCV is located using:

	brew tap homebrew/science

3.The ‘formula’ for OpenCV should now be open in whatever you set the default editor to be, it’s vim by default but if you want to change it you can run the following replacing ‘emacs’ with whatever your favorite text editor is (I use "nano").

	echo 'export EDITOR=emacs' >> ~/.bash_profile
	source ~/.bash_profile

4.Type:

	brew edit opencv

5,Look for the following lines:

	require 'formula'
	 
	class Opencv < Formula
	  homepage 'http://opencv.org/'
	  url 'https://github.com/Itseez/opencv/archive/2.4.7.1.tar.gz'
	  sha1 'b6b0dd72356822a482ca3a27a7a88145aca6f34c'
	 
	  option '32-bit'

6.Go ahead and replace "url" and "sha1" lines with:

	url 'https://github.com/Itseez/opencv/archive/2.4.8.tar.gz'
	sha1 '61b95974bf9689b94b169c39aed6c85a2e124837'

7.Go ahead and install OpenCV now:

	brew install opencv

8.You’re done! You can find OpenCV at

	cd /usr/local/Cellar/opencv/2.4.8/


####Important NOTE:

If you get the error "Error: Cowardly refusing to `sudo brew link`" when typing:

	sudo brew install <packageName>

You need to make brew be owned by the root:

	ls -al `which brew`
	sudo chown root:wheel `which brew`
	sudo chown : `chown brew`

Now try to install the package again:

	sudo brew install <packageName>

####Setup Python

1.Navigate to your python path, if you don’t know where it is when you installed Python you can find it in your .bash_profile or using

	cat ~/.bash_profile | grep PYTHONPATH

in my case we’ll be using

	cd /Library/Python/2.7/site-packages/

2.Once there we need to link our compiled OpenCV files, create a symlink using

	sudo ln -s /usr/local/Cellar/opencv/2.4.8/lib/python2.7/site-packages/cv.py cv.py
	sudo ln -s /usr/local/Cellar/opencv/2.4.8/lib/python2.7/site-packages/cv2.so cv2.so

3.You’re done! You can make sure it works by running python and typing

	import cv

####Python Dependencies

1.Install PIL (you need to have PIP installed for this, it comes preinstalled with python)

	sudo pip install Pillow


