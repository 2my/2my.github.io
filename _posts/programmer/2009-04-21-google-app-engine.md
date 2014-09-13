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

## Java on App Engine
See <a href="http://code.google.com/appengine/docs/java/overview.html">App Engine Java Overview</a>.
SDK (<a href="http://code.google.com/appengine/docs/java/gettingstarted/installing.html">ref Google</a>):

I downloaded the SDK, unzipped it and added to my PATH.

I used Ant to build the app in demos\guestbook

I then ran the local test-server with command (path from demos dir):

*dev_appserver.cmd guestbook\war*

I must wait for activation before I can upload app

<a href="http://appengine.google.com/">Dashboard</a>.

### Groovy on App Engine

I impported the code for the <a href="http://blog.springsource.com/2009/04/07/write-your-google-app-engine-applications-in-groovy/">Groovy AppEngine HelloWorld</a>, but that does not run locally due to a bug in the SDK. I commented out the line that tries GroovyShell().evaluate("3*4"), and it ran, but it seems that Groovlets are based on being able to evaluate scripts.

Next up: get rss from Blogger and delicio.us.

