
# LivescoreRaspiPower
Use your raspberry pi to stream live video of a match and manage your score, time and players to the screen. Also pan your camera. Control everything via a simple website on your mobile phone!

In the ZIP you can find the mySQL database, php files you need to install on the raspberry. You also need to install pi-blaster in case you want to add a pan servo to GPIO17. For the stream you need UV4L driver and I managed to get a stream of 640x480 at 15 fps.
What you need:
apache
mysql
pi-blaster and servo (option)
raspberry pi cam



Follow this guide (not mine!)
from:
http://www.instructables.com/id/Raspberry-Pi- Video-Streaming/?ALLSTEPS


To install the uv4l driver, open the terminal and run the following commands:

wget http://www.linux-projects.org/listing/uv4l_repo/lrkey.asc &amp;&amp; sudo apt-key

add ./lrkey.asc

Add the following line to the file /etc/apt/sources.list :

sudo nano /etc/apt/sources.list

deb http://www.linux-projects.org/listing/uv4l_repo/raspbian/ wheezy main

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install uv4l uv4l-raspicam

sudo apt-get install uv4l-raspicam- extras

sudo apt-get install uv4l-server

sudo apt-get install uv4l-uvc

sudo apt-get install uv4l-xscreen

sudo apt-get install uv4l-mjpegstream

sudo reboot



sudo pkill uv4l (Optional)

sudo uv4l -nopreview -- auto-video_nr -- driver raspicam -- encoding mjpeg --

width 640 -- height 480 -- framerate 20 -- server-option &#39;-- port=9090&#39; -- server-

option &#39;-- max-queued- connections=30&#39; -- server-option &#39;-- max-streams=25&#39; --

server-option &#39;-- max-threads=29&#39;

Notes:

The -- port=9090 is the local IP port. You can use any port you like.

The -- max-streams=25 is the maximum simultaneous streams.
