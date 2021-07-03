# Face-Mask-Detection-Raspberry-Pi
Uilizing Tensorflow and openCV frameworks, we have created a Face Mask Detection Software Script. It takes 10 Minutes to setup and run on a Raspberry Pi.

# The Need For it

Skip Over to 'Installing Prerequisites' if you already have your mind made up.

This is a repository that is to run a Mask Detection System on your RASPBERRY PI 2 / 3B / 3B+ / 4.
This has been tested on a Raspberry Pi 3B. It runs super smooth at 10fps.
Upon little overclocking, the fps is 23 fps

It is very fast(<1 second for full detection), accurate( 3000+ images and 90% accuracy rate) and can be deployed in areas with heavy traffic (can recognise ten people at once).
# Install prerequisites on your Raspberry Pi 
The Raspberry Pi requires that you install a few system packages before you get started:
RUN THESE COMMANDS.

    $ sudo apt-get install libhdf5-dev libhdf5-serial-dev libhdf5-103
    $ sudo apt-get install libqtgui4 libqtwebkit4 libqt4-test python3-pyqt5
    $ sudo apt-get install libatlas-base-dev
    $ sudo apt-get install libjasper-dev

# Install pip on your Raspberry Pi

The Python package manager, “pip”, can be obtained via wget:
Run These Commands

    $ wget https://bootstrap.pypa.io/get-pip.py
    $ sudo python3 get-pip.py

# Setup Virtual Environments on your Raspberry Pi
Virtual environments are definitely the way to go if your Raspberry Pi has multiple purposes. They won't interfere with your system libraries.

    $ pip install virtualenv virtualenvwrapper

Then you need to add the following lines to your ~/.bashrc by

    sudo nano ~/.bashrc

and append these lines to the end:

    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
    export WORKON_HOME=$HOME/.virtualenvs
    export VIRTUALENVWRAPPER_VIRTUALENV=/home/YOUR_USERNAME/.local/bin/virtualenv
    source /usr/local/bin/virtualenvwrapper.sh

remember to put your username in the YOUR_USERNAME field

Then:

Save the file. Then “source it” in your terminal:

    $ source ~/.bashrc

Terminal output will be printed indicating that virtualenvwrapper is ready. Be sure to inspect it for errors.

You now have access to new terminal commands:

1. Create an environment with mkvirtualenv
2. Activate an environment (or switch to a different one) with workon
3. Deactivate an environment with deactivate
4. Remove an environment with rmvirtualenv

    
# Installation

Clone The Repo:

        $ git clone https://github.com/inmicro/Face-Mask-Detection-Raspberry-Pi
        
Change your directory to the cloned repo and create a Python virtual environment named 'test'
        
        $ cd Face-Mask-Detection-Raspberry-Pi
        $ mkvirtualenv test

Now, run the following command in your Terminal/Command Prompt to install the libraries required

        $ pip3 install -r requirements.txt

# Running The Scripts

For Still Images use:
    
    $ python3 detect_mask_image.py --image images/pic1.jpeg
    
Replace the images/pic1.jpeg with your image source.

For Realtime Virtual Streams, use:

        $ python3 detect_mask_video.py 
       

 # PiCamera Users
 
 If you plan on using the pi camera, use this: 

        $ pip install "picamera[array]"
 
 
And Use the script demarcated for the pi camera:

        $ python3 detect_mask_video_picamera.py 
