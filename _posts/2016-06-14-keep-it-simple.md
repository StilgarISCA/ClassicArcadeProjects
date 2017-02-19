---
layout: post
title: Keep it Simple Stupid
tags:
- raspberry pi
- power down
- ups
comments: true
---
One of the problems to conquer with using the Raspberry Pi as my Track & Field hardware is the shutdown step. While a lot of arcade machines do have a power switch, Track & Field (to my knowledge) does not. Powering down these old games in the arcade generally meant just turnning off a gang switch or breaker. In a one-off setting you'd likely just pull the plug. To appear outwardly authentic, I want to retain the ability to pull the plug for powering down.

Pulling the plug on a Raspberry Pi isn't a great idea. Because it's running a Unix-like OS, it has caches, temp files, logs and whatnot that it writes back to storage regularly. Without a proper shutdown you can corrupt your media and end up with a system that won't boot.

Powering down the Pi this way is a challenge I have to overcome. I did a lot of research and as it turns out this is a tough nut to crack. There are acutally two problems involved here: (1.) keeping power to the Pi so it can gracefully shutdown, and (2.) the software / hardware to trigger the shutdown event once the power drops off.

For the power issue, there are a lot of solutions in the works like [LiFePO3wered/Pi](https://hackaday.io/project/9461-lifepo4weredpi); a lot of unreleased solutions like [juice4halt](http://juice4halt.com); and some close-but-not-quite solutions like [PiUPS](https://www.pi-supply.com/product/pi-ups-uninterrupted-power-supply-raspberry-pi/).

I narrowed it down to these two solutions:

1. [UPS Pico Stack](http://www.pimodulescart.com/shop/item.aspx?itemid=24)
2. [Adafruit PowerBoost 1000](https://www.adafruit.com/products/2465)

I ended up buying the PowerBoost, because it didn't have any extra bells and whistles and I didn't have to deal with buying something overseas. Euros, VAT and shipping, yuck. Adafruit is also a company I trust.

The problem is that this was too elaborate for me. I hate soldering and I'm not very good at it. I printed off some diagrams and then I realized there was a bunch of other crap I needed to pull this off:

* new soldering iron -- my $5 Rat Shack job from 1989 wasn't going to cut it
* new soldering tips
* a soldering station, you know, the things with the aligator clips to hold your work
* a new spool of easy-to-work-with solder
* a breadboard 
* various resisters

After ordering more equipment, when I sat down to do the work, it was a bit too overwhelming for me. Immediately, I noticed that I was going to need even more gear. I'm sure I could pull it off, but I didn't want to go much further down this road because it'd take up too much of my precious, limited time and I wanted to spend more time building out the game then trying to solve this problem.

Looking over the parts and equipment on my workbench, I quickly recognized that I violated the [KISS principle](https://en.wikipedia.org/wiki/KISS_principle). Going back over my notes, I went to a simple, but elegant solution that I had dismissed earlier because for some reason it seemed wasteful to me.

Mathias Kunter uses a simple USB cellphone backup power brick combined with a cheap ethernet switch (I had some sort of mental problem using a switch this way). When the switch loses power, some custom software detects when the ethernet drops out (or comes on) and can execute batch scripts. You can read all about it at his project site: [http://raspi-ups.appspot.com/en/index.jsp](http://raspi-ups.appspot.com/en/index.jsp).

After ordering up a switch, power brick and 3" cat-5 patch cord, I felt a lot closer to having this working. Unfortunately, I ran into some issues with Mathias' daemon. I can get it to kill MAME when the power drops the first time, and when the power is restored it will load up MAME, but it won't kill it a second time. Mathias' code seems a bit too complicated for me and I've already learned my lesson with breaking KISS, so I'm taking a stab at writing a bit of Perl which mostly just makes system calls to Raspbian. It's not finished yet, but pretty close to done at time of this writing.

Here's the repository for my code: [https://github.com/StilgarISCA/PiMameManager](https://github.com/StilgarISCA/PiMameManager).