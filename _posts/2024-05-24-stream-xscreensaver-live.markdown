---
layout: post
title:  "Stream xscreensaver live"
date:   2024-05-24 15:10:30 +0100
categories: technology, programming, media
---

{% include analytics.html %}

I first saw xscreensaver on a researcher's laptop in 2003, when I was 14, and I loved it so much I installed linux. I've been running linux ever since, I got a few degrees in CS, and I'm still a huge fan.

How can people see it today, in a platform independent way? In an effort to make the screensaver easily available, I thought it would be neat to create a "livestream", and here are the steps:

On ubuntu 22, run
sudo vi /etc/gdm3/custom.conf
and disable Wayland by uncommenting the line
WaylandEnable=false

Install OBS studio and connect it to youtube.

Create a virtual screen with Xephyr:

Xephyr :2 -screen 1920x1080

and run xscreensaver in it:
DISPLAY=:2 xscreensaver
DISPLAY=:2 xscreensaver-command -activate

use Window Capture (XComposite) in OBS to capture the Xephyr screen without borders, and press "Start Streaming"

link to live stream: https://www.youtube.com/watch?v=J92IlAQKdCY

NB: it's actually pretty fiddly, so setting this up to run automatically on reboot is still a challenge.
