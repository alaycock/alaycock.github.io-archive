---
layout: project
title:  "SmartMirror"
date:   2015-05-11 12:00:00
categories: projects
githuburl: https://github.com/alaycock/SmartMirror
---
This is the back-end for my smart mirror. It displays the current time, weather,
and some news stories. It also has integration for gesture controls, so you can
wave you hand near the mirror and have it do stuff.

[You can read my blog posts about building the Smart Mirror here.](/blog/2015/07/01/Smart-Mirror-Intro.html)

Web server
---
The web server runs on Node.js and uses some basic modules to serve static
files, but will also allow for custom pages, API, etc. in the future.

Front end
---
The different pieces of the page refresh at different intervals. The weather is
every few minutes, clock every second (it uses local time, not server
time), and news every few minutes as well. It also has integration with gesture
control, since the gestures will send keyboard inputs to the browser, the
JavaScript will have to detect that.

Gesture Control
---
This is still a WIP, but it will use Python to capture input from the Hover
device which is attached to the Raspberry Pi, and allow the user to interface
with Chrome.
