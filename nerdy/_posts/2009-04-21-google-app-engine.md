---
title: "Google App Engine"
categories: [DotMe]
layout: "post"
date: "2009-04-21 18:19:00"
updated: "2009-04-22 20:16:07"
blogger:
    siteid: "7706585097329252419"
    postid: "5868789460989407160"
---

<span style="font-weight: bold;font-size:130%;" >Java on App Engine

</span><span style="font-size:130%;">See <a href="http://code.google.com/appengine/docs/java/overview.html">App Engine Java Overview</a>.

</span><span style="font-weight: bold;font-size:130%;" >SDK (<a href="http://code.google.com/appengine/docs/java/gettingstarted/installing.html">ref Google</a>):

</span>I downloaded the SDK, unzipped it and added to my PATH.

I used Ant to build the app in demos\guestbook

I then ran the local test-server with command (path from demos dir):

<span style="font-style: italic;">dev_appserver.cmd guestbook\war</span><span>

I must wait for activation before I can upload app

<a href="http://appengine.google.com/">Dashboard</a>.

<span style="font-size:130%;"><span style="font-weight: bold;">Groovy on App Engine</span></span>

I impported the code for the <a href="http://blog.springsource.com/2009/04/07/write-your-google-app-engine-applications-in-groovy/">Groovy AppEngine HelloWorld</a>, but that does not run locally due to a bug in the SDK. I commented out the line that tries GroovyShell().evaluate("3*4"), and it ran, but it seems that Groovlets are based on being able to evaluate scripts.

Next up: get rss from Blogger and delicio.us.

</span>
