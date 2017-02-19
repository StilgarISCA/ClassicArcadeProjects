---
layout: post
title: Wiring is Tedious
tags:
- Track and Field
- wiring
- molex
- crimp
- terminal
feature-img: "img/tnf-control-panel-lose-wiring.jpg"
comments: true
excerpt: After many, many hours of running wires and crimping pins and terminals, I wasn't very thrilled to revisit all this work in the form of a blog post. Much like the wiring job itself, I pushed through and here we are.
---
I've spent hours and hours running wires, crimping pins and connectors and heat shrinking to get my Track and Field cocktail in a playable state.

I bought a bunch of 18 gauge equivalent wire from Amazon.com. I needed more colors, but didn't want to buy more wire so I had to reuse. It would have been convenient to have enough colors for each button, but doubling up wasn't too bad because I could later trace the wires back to the correct button with the continuity test on my multimeter.

For each button I crimped on a spade terminal and put some heat shrink on for good measure. I realize the heat shrink wasn't necessary, but I like the clean, sealed look that it gives. I essentially did the same things for the speakers, but I used "real" speaker wire to wire the speakers up to the amplifier.

![alt text](/img/tnf-crimped-spade-terminal.jpg "Crimped spade terminal with two wires")

{% include image.html
            img="img/tnf-zip-tie-wires.jpg"
            title="Control Panel wires zip tied together"
            caption="Zip ties and wire harnesses made it all nice and neat once the wiring was finished" %}


After I started running all these wires, I realized that if I ever wanted to take my cabinet apart again &ndash; to lighten it up for moving, or for easier service &ndash; I'd have another nightmare on my hands, because each of these wires would have to be disconnected.

The solution was to go with the industry standard Molex connectors. You pick an accessible spot, cut all the wires, strip, crimp pins and receivers on, plug them into the plastic male or female housing. It takes forever, but it does look nice when it's done.

![alt text](/img/tnf-molex-connectors.jpg "12-pin Molex connector")

I'm using an iPac board to convert the button presses into keystrokes that MAME will understand. I wanted that to look nice too, so unlike all the other boards, I mounted this one on the side of the cabinet instead of on the flat slide-out piece. This also allowed me to neatly arrange the wires from the control panels.

I had preprogramed all the button locations on the iPac a head of time, and that ended up being a wasted effort. During preprograming I hadn't considered the physical orientation of the wires in relation to the iPac terminals. It was easier just to put the wires in where they made sense and then just reprogram MAME to match up with the wires after the fact.

{% include image.html
            img="img/tnf-ipac-neat-wires.jpg"
            title="The wired up iPac board"
            caption="The iPac all wired up" %}

My next post will talk more about wiring up the boards and power supply.