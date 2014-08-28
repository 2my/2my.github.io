---
title: "MacOS 10.5 and Apache httpd 2.2"
layout: "post"
permalink: "/2008/02/mac-web-server.html"
uuid: "2013367502997820838"
guid: "tag:blogger.com,1999:blog-36955474.post-2013367502997820838"
date: "2008-02-10 18:25:00"
updated: "2008-02-21 21:05:45"
description: 
blogger:
    siteid: "36955474"
    postid: "2013367502997820838"
categories: 
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
Httpd 2.2 is included, but when I turned on web sharing, I got 403 for my personal page.
The solution is found in: http://www.gigoblog.com/2007/11/08/configure-apache-web-sharing-for-user-accounts-in-mac-os-x-105-leopard/
more stuff on: <a href="http://www.onlamp.com/pub/ct/49">Apache Web-Serving with Mac OS X</a>.

<span style="font-size:130%;">Tomcat connector (in progress...)
</span>I downloaded and installed Tomcat 6.0.16, and tried to connect it to Apache. References:
<a href="http://tomcat.apache.org/connectors-doc/webserver_howto/apache.html">tomcat connector</a>, <a href="http://www.malisphoto.com/tips/tomcatonosx.html"><span><span style="font-size:100%;">Installing Apache Tomcat 6 on <span class="mac">Mac OS X Leopard</span></span></span></a>
, but in the end I just did ProxyPass ajp://localhost:8009/
<span style="font-size:130%;">Some locations and commands:</span>
sudo apachectl restart
/usr/libexec/apache2/
/private/etc/apache2/httpd.conf

<span style="font-size:130%;">Domain...</span>
See: <a href="http://www.macinstruct.com/node/112">How to Turn Your Mac Into a Web Server</a>,<a href="http://www.apple.com/findouthow/web/" rel="nofollow"><span style="font-weight: bold;"> </span></a><a href="http://www.macdevcenter.com/pub/a/mac/2003/05/28/dns_primer.html" rel="nofollow"><span style="font-weight: bold;"></span>MacDevCenter.com -- A DNS Primer</a>,

<span style="font-size:130%;">More:
</span><a href="http://www.apple.com/findouthow/web/" rel="nofollow">Apple - Creating a Website</a> (iWeb guide),<a href="http://www.macdevcenter.com/pub/a/mac/2003/05/28/dns_primer.html" rel="nofollow"><span style="font-weight: bold;"></span></a>
</div>