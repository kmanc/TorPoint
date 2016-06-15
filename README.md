# TorPoint  
Two scripts made to turn a raspberry pi into an access point that routes internet traffic through tor  

A week or so ago I decided I wanted to create a tor access point with a raspberry pi I had hanging around...boy was it harder than I hoped it would be and here is why:    
  
-I wanted my access point to be configured with two wifi dongles, instead of the normal 1 dongle + 1 ethernet connection, which made it a little more tricky.  
-I was using two random wifi dongles that I had lying around, and only one of them is capable of being access point   
-The dongle that can be an access point has the rtl871xdrv driver, which does not work with the default hostapd on raspbian  
-There was probably more, but I can't remember off the top of my head  
  
So what did I do?  Well...Google mostly, but I found some stuff that I think is helpful.

After trying a bunch of different configurations and different setups, I stumbled across Thomas' post https://hackaday.io/project/4223-raspberry-tor-router  
Thomas was nice enough to write a few scripts that do all the heavy lifting for you, and come pretty close to what we want. But it isn't exact...see Thomas' work sets you up to use a wifi dongle and an ethernet port, so this is where I come in :)

I took Thomas' script and made some changes so that you can turn your RaPi into a tor access point with 2 wifi dongles and (hpoefully) minimal effort!  
  
How to run the scripts:  

In order to ensure that everything runs properly, I would suggest *NOT* having any wifi dongles plugged in during the setup.  However, you do need an internet connection, so I suggest plugging in an ethernet cable while the scripts are being run.  

First thing's first, you need to get them onto your pi.  You can either do that with a flash drive or by running "wget LINK_GOES_HERE" 
Open up a terminal and move to the directory where the scripts are stored  
Now you need to give the scripts permission to run by running "chmod +x access_point.sh" followed by "chmod +x tor_config.sh" Now you'll run access_point by running the command "sudo ./access_point.sh". Follow the instructions, and your Pi will reboot when it is done. 
Your Pi will reboot once again when that script is done. Now, you should plug in a working wifi dongle (does not need to be anything specific), and after that, plug in a wifi dongle with the rtl871xdrv driver. If the second wifi dongle plugged in does not have the correct driver, your access point probably will not work.  
You've got one more step before you're done!! Once it has rebooted, you'll open up a terminal again, move to the correct directory (again) and type "sudo ./tor_config.sh". The script will run, reboot when it is finished, and you should have a working tor access point!  Congrats :)


