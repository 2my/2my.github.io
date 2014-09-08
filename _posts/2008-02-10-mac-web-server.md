---
title: "MacOS 10.5 and Apache httpd 2.2"
categories: [mac]
layout: "post"
date: "2008-02-10 18:25:00"
updated: "2008-02-21 21:05:45"
blogger:
    siteid: "36955474"
    postid: "2013367502997820838"
---

Httpd 2.2 is included, but when I turned on web sharing, I got 403 for my personal page.
The solution is found in: http://www.gigoblog.com/2007/11/08/configure-apache-web-sharing-for-user-accounts-in-mac-os-x-105-leopard/
more stuff on: <a href="http://www.onlamp.com/pub/ct/49">Apache Web-Serving with Mac OS X</a>.

### Tomcat connector (in progress...)
I downloaded and installed Tomcat 6.0.16, and tried to connect it to Apache. References:
<a href="http://tomcat.apache.org/connectors-doc/webserver_howto/apache.html">tomcat connector</a>, <a href="http://www.malisphoto.com/tips/tomcatonosx.html">Installing Apache Tomcat 6 on Mac OS X Leopard</a>
, but in the end I just did ProxyPass ajp://localhost:8009/

### Some locations and commands:
sudo apachectl restart
/usr/libexec/apache2/
/private/etc/apache2/httpd.conf

### Domain...
See: <a href="http://www.macinstruct.com/node/112">How to Turn Your Mac Into a Web Server</a>,<a href="http://www.apple.com/findouthow/web/"></a><a href="http://www.macdevcenter.com/pub/a/mac/2003/05/28/dns_primer.html">MacDevCenter.com -- A DNS Primer</a>,

### More:
<a href="http://www.apple.com/findouthow/web/">Apple - Creating a Website</a> (iWeb guide),<a href="http://www.macdevcenter.com/pub/a/mac/2003/05/28/dns_primer.html">dns primer</a>
