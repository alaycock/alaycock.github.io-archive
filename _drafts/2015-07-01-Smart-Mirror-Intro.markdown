---
layout: post
title:  "Smart Mirror - Intro"
date:   2015-07-01 14:00:00
categories: blog
---
I've been working on making my own take on the
[Magic Mirror](http://michaelteeuw.nl/tagged/magicmirror), which was originally
done by Michael Teeuw. It's been done many times by other people, but mine is
going to be a little bit different and a little bit more complicated. Check out
Michael's site for a more complete understanding, but the basic idea is that
it's a 2-way mirror with a monitor behind it, so you can have visuals show up
while you're looking in the mirror. Use cases would include, displaying the
weather, the time, current events, your calendar, your email, etc.

What makes my mirror more interesting is this device.

![](/img/20150724/hover.jpg)

[The Hover](http://www.hoverlabs.co/) is a Raspberry Pi compatible gesture and
touch control. Meaning I will be able to wave my hand next to the mirror, and
show different views. Not revolutionary, but definitely interesting.

## The Hardware ##
I had to buy the following for this project:

 * Raspberry Pi 2 + power and HDMI cables
 * Hover gesture control + GPIO jumper cables
 * Monitor
 * 2-way Mirror
 * Frame
 
 ![](/img/20150724/hardware.jpg)

## The Steps ##

 1. Purchase parts  
 2. Write the software
   a. The browser interface
   b. The gesture controller
 3. Build the frame
 4. Assembly
 5. Mounting
 
I purchased the Raspberry Pi 2, since it's currently the newest version, as well
as the Hover gesture control, those were pretty easy purchases since there aren't
too many options for those.

[See the next section, picking and purchasing the monitor.]()
