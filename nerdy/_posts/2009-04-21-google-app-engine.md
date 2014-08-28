---
title: "Google App Engine"
layout: "post"
permalink: "/2009/04/google-app-engine.html"
uuid: "5868789460989407160"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-5868789460989407160"
date: "2009-04-21 18:19:00"
updated: "2009-04-22 20:16:07"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "5868789460989407160"
    comments: "0"
categories: [DotMe]
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
<span style="font-weight: bold;font-size:130%;" >Java on App Engine<br /></span><span style="font-size:130%;">See <a href="http://code.google.com/appengine/docs/java/overview.html">App Engine Java Overview</a>.<br /><br /></span><span style="font-weight: bold;font-size:130%;" >SDK (<a href="http://code.google.com/appengine/docs/java/gettingstarted/installing.html">ref Google</a>):<br /></span>I downloaded the SDK, unzipped it and added to my PATH.<br />I used Ant to build the app in demos\guestbook<br />I then ran the local test-server with command (path from demos dir):<br /><span style="font-style: italic;">dev_appserver.cmd guestbook\war</span><span><br /><br />I must wait for activation before I can upload app<br /><br /><a href="http://appengine.google.com/">Dashboard</a>.<br /><br /><span style="font-size:130%;"><span style="font-weight: bold;">Groovy on App Engine</span></span><br />I impported the code for the <a href="http://blog.springsource.com/2009/04/07/write-your-google-app-engine-applications-in-groovy/">Groovy AppEngine HelloWorld</a>, but that does not run locally due to a bug in the SDK. I commented out the line that tries GroovyShell().evaluate("3*4"), and it ran, but it seems that Groovlets are based on being able to evaluate scripts.<br /><br />Next up: get rss from Blogger and delicio.us.<br /><br /><br /></span>
</div>