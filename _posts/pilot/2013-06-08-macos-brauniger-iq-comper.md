---
title: "MacOS + Brauniger IQ Compeo"
categories: [software, checklist, paragliding]
layout: "posts"
date: "2013-06-08 20:25:00"
updated: "2013-08-13 07:47:59"
blogger:
    siteid: "36955474"
    postid: "834098218193162161"
---

To download track points, recipe:

I had an usb to serial converter cable, I don't know the make. System report said there was a Prolific device. I proceeded to download and install the driver from Plugable&nbsp;(md_PL2303_MacOSX10.6up_v1.5.0.zip), following <a href="http://plugable.com/2011/07/12/installing-a-usb-serial-adapter-on-mac-os-x">instructions</a>. The download comes with its own instructions as well.

I turned on my GPS, switched to Menu mode and entered the page that listed saved tracks before I connected the cable to it.

I then fired up GpsDump for Mac (from <a href="http://www.gethome.no/stein.sorensen/">Stein</a>).

From the&nbsp;GpsDump&nbsp;"Misc" menu I chose "set COM port", and in the window I selected "/dev/cu.usbserial", a name I recognized from verifying the driver installation.

Then I chose to get tracks from my Brauniger, and it all worked!
