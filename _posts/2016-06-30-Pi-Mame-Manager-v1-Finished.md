---
layout: post
title: Pi Mame Manager is Finished
tags:
- Rasbian
- Raspberry Pi
- Mame
- Arcade
- Shutdown
- UPS
---
I'm happy to announce that my [Pi Mame Manager script](https://github.com/StilgarISCA/PiMameManager) is done. Done enough to tag it as version 1.0.0 that is.

You can find all the nitty-gritty details in [my last post on the subject](http://www.classicarcadeprojects.com/2016/06/14/keep-it-simple.html), and in [the repository's readme](https://github.com/StilgarISCA/PiMameManager). In a nutshell, it works something like this:

* Use a USB external battery brick -- like what you'd use to extend the battery life on your cell phone -- to pipe power to the Raspberry Pi.
* Plug a cheap ethernet switch into the Raspberry Pi's ethernet port.
* Run my PiMameManager script.

The script will launch Mame if the power is up. If the power drops off, the script will detect the loss of signal to the ethernet port. The Raspberry Pi will continue to run because of the external battery. When the script identifies a power outage it will kill the Mame process. If the power is restored, the script will relaunch Mame, simulating a reset. If the power crosses the battery threshold it will gracefully shutdown the Raspberry Pi.

Now, to capture a few of my thoughts that don't exist elsewhere:
 
* The script was designed with Raspbian Jessie in mind
* The script was tested with Advance Mame
* I tried to make the script easy to configure so you can use it with other OSes, Mame versions
* The script largely just wraps Bash functions
* I probably could have used Bash script instead of Perl, but I felt like my Bash was more rusty than my Perl
* Out of the box, the script can be run at start up, but it could easily be configured to run as a daemon or a cron job instead.

### Other Bullets

* [The PiMameManager Repository](https://github.com/StilgarISCA/PiMameManager)
* I stole this idea from [Mathias Kunter](http://raspi-ups.appspot.com/en/index.jsp)