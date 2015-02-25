# tightvnc
tightvnc for pi

VNC is a graphical desktop sharing system that allows you to remotely control the desktop interface of one computer from another. It transmits the keyboard and mouse events from the controller, and receives updates to the screen over the network from the remote host

You will see the desktop of the Raspberry Pi inside a window on your computer. You'll be able to control it as though you were working on the Raspberry Pi itself.

On your Pi (using a monitor or via SSH), install the TightVNC package:
sudo apt-get install tightvncserver

Next, run TightVNC Server which will prompt you to enter a password and an optional view-only password:
tightvncserver

Save this file as vncboot 
Make this file executable:
chmod 755 vncboot

Enable dependency-based boot sequencing:
update-rc.d /etc/init.d/vncboot defaults

If enabling dependency-based boot sequencing was successful, you will see this:
update-rc.d: using dependency based boot sequencing

But if you see this:
update-rc.d: error: unable to read /etc/init.d//etc/init.d/vncboot

then try the following command:
update-rc.d vncboot defaults

Reboot your Raspberry Pi and you should find a VNC server already started.
