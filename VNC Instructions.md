# VNC Server set up

I know you’ve all been annoyed when you are running something in a Jupyter notebook, and you lose your internet connection for long enough that it decides you’ve gone away, and then your session disappears, and you have to start it again from scratch. So what do you do? There is a very simple cool thing called VNC where you can install on your AWS instance or PaperSpace, or whatever:

* X Windows (xorg)
* Lightweight window manager (lxde-core)
* VNC server (tightvncserver)
* Firefox (firefox)
* Terminal (lxterminal)
* Some fonts (xfonts-100dpi)

Chuck the lines at the end of your ./vnc/xstartup configuration file, and then run this command (tightvncserver :13 -geometry 1200x900):

sudo apt-get install xorg lxde-core tightvncserver firefox lxterminal xfonts-100dpi
cat >> ~/.vnc/xstartup
  lxterminal &
  /usr/bin/lxsessions -s LXDE *
  <ctrl-d>
  tightvncserver :13 -geometry 120x900
  tightvncserver -kill :13
  
