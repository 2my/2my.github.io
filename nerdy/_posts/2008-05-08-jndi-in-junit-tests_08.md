---
title: "JNDI in JUnit tests"
layout: "post"
permalink: "/2008/05/jndi-in-junit-tests_08.html"
uuid: "1090094832776608512"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-1090094832776608512"
date: "2008-05-08 16:07:00"
updated: "2008-12-15 11:30:33"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "1090094832776608512"
    comments: "0"
categories: [tg, testing]
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
<div xmlns="http://www.w3.org/1999/xhtml">Sun har også en provider som kan brukes - se <a href="http://java.sun.com/products/jndi/tutorial/TOC.html">jndi-tutorial</a>.<br />I ended up using <a href="http://www.osjava.org/simple-jndi/index.html">Simple-JNDI - simple-jndi</a>, thanks to:<br /><a href="http://radio.weblogs.com/0112098/2005/07/26.html#a533">James Strachan's Weblog</a><br /><a href="http://www.unicon.net/node/601">Injecting Constants as Spring Bean Properties | Unicon</a><br /><h3></h3><h4>My setup for lookup-key "java:comp/env/jdbc/ds":</h4><b>jndi.properties</b>:<br />java.naming.factory.initial=org.osjava.sj.SimpleContextFactory<br />org.osjava.sj.root=${project.build.directory}\\test-classes\\jndi<br />org.osjava.sj.colon.replace=--<br />org.osjava.sj.delimiter=/<br /><br /><b>src/test/resources/jndi/java--comp/env/jdbc/ds.properties:<br /></b>type=javax.sql.DataSource<br />driver=oracle.jdbc.OracleDriver<br />url=${db.url}<br />user=${db.user}<br />password=${db.password}<br /><br /><br /><a href="http://commons.apache.org/configuration/"><br /></a></div>
</div>