---
layout: post
title:  "Stream xscreensaver live"
date:   2024-05-24 15:10:30 +0100
categories: technology, programming, media
---

{% include analytics.html %}

# XScreenSaver Livestream Setup

I first saw XScreenSaver on a researcher's laptop in 2003, when I was 14, and I loved it so much I installed Linux. I've been running Linux ever since, got a few degrees in Computer Science, and I'm still a huge fan.

## Viewing XScreenSaver Today

How can people see it today, in a platform-independent way? In an effort to make the screensaver easily available, I thought it would be neat to create a "livestream", and here are the steps:

### Step-by-Step Guide

1. **Disable Wayland on Ubuntu 22**

    Open the custom configuration file for GDM3:
    ```sh
    sudo vi /etc/gdm3/custom.conf
    ```
    Disable Wayland by uncommenting the following line:
    ```sh
    WaylandEnable=false
    ```

2. **Install OBS Studio**

    Install OBS Studio and connect it to your YouTube account.

3. **Create a Virtual Screen with Xephyr**

    Create a virtual screen using Xephyr:
    ```sh
    Xephyr :2 -screen 1920x1080
    ```

4. **Run XScreenSaver in the Virtual Screen**

    Start XScreenSaver in the virtual screen:
    ```sh
    DISPLAY=:2 xscreensaver
    DISPLAY=:2 xscreensaver-command -activate
    ```

5. **Capture the Xephyr Screen with OBS**

    Use Window Capture (XComposite) in OBS to capture the Xephyr screen without borders, and press "Start Streaming".

## Livestream Link

You can view the live stream here: [XScreenSaver Livestream](https://www.youtube.com/watch?v=J92IlAQKdCY)

> **NB:** It's actually pretty fiddly, so setting this up to run automatically on reboot is still a challenge.
