# TorPoint
Two scripts made to turn a raspberry pi into an access point that routes internet traffic through tor

A week or so ago I decided I wanted to create a tor access point with a raspberry pi I had hanging 
around...boy was it harder than I hoped it would be and here is why:  

-I wanted my access point to be configured with two wifi dongles, instead of the normal 1 dongle + 1 ethernet connection, which made it a little more tricky.
-I was using two random wifi dongles that I had lying around, and only one of them is capable of being access point 
-The dongle that can be an access point has the rtl871xdrv driver, which does not work with the default hostapd on raspbian
-There was probably more, but I can't remember off the top of my head

So what did I do?  Well...Google mostly, but I found some stuff that I think is helpful.

After trying a bunch of different configurations and different setups, I stumbled across Thomas' post https://hackaday.io/project/4223-raspberry-tor-router
Thomas was nice enough to write a few scripts that do all the heavy lifting for you, and come pretty close to what we want.  But it isn't exact...see Thomas' work sets you up to use a wifi dongle and an ethernet port, so this is where I come in :)

I took Thomas' script and made some changes so that you can turn your RaPi into a tor access point with 2 wifi dongles and (hpoefully) minimal effort!
