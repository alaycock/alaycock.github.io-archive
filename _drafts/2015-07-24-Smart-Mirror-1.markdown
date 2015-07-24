---
layout: post
title:  "Smart Mirror - Intro"
date:   2015-07-24 14:00:00
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

## The Software ##
Since I'm a software guy, I'm going to start with the programming aspect of this
project. Michael already wrote
[an interface](https://github.com/MichMich/MagicMirror) which is functional
already, but I'm sort of particular about how I want my interface, so I decided
to do my own from scratch. It also has some custom gesture features that I'll
have to build in.

![](/img/20150724/code.jpg)

You can find my (currently incomplete) code on my
[Github](https://github.com/alaycock/SmartMirror), I'm also going to use a
browser for the interface, because of the low overhead. Basically it's a node
server that serves static files. The front end JavaScript does the heavy lifting
in terms of displaying and updating the time, time, weather and news. I'm
planning on adding a few more sections, including my calendar, email, etc.

Finally, I'll also need come code to tie into the Hover for gesture control. The
Hover has a [library](https://github.com/hoverlabs/hover_raspberrypi) for Python
already, so that will capture the input, then from there I can send keyboard
input to the browser. I haven't narrowed down the best way to do that yet
because I still have a number of steps to complete before that's necessary.

## The Hardware ##
I had to buy the following for this project:

 * Mirror
 * Raspberry Pi + power, HDMI, and GPIO jumper cables
 * Hover gesture control
 * Monitor
 * Frame
