---
title: "JNDI in JUnit tests"
categories: [tg, testing]
layout: "post"
date: "2008-05-08 16:07:00"
updated: "2008-12-15 11:30:33"
blogger:
    siteid: "7706585097329252419"
    postid: "1090094832776608512"
---

Sun har også en provider som kan brukes - se <a href="http://java.sun.com/products/jndi/tutorial/TOC.html">jndi-tutorial</a>.

I ended up using <a href="http://www.osjava.org/simple-jndi/index.html">Simple-JNDI - simple-jndi</a>, thanks to:

<a href="http://radio.weblogs.com/0112098/2005/07/26.html#a533">James Strachan's Weblog</a>

<a href="http://www.unicon.net/node/601">Injecting Constants as Spring Bean Properties | Unicon</a>

### My setup for lookup-key "java:comp/env/jdbc/ds":
**jndi.properties**:
```
java.naming.factory.initial=org.osjava.sj.SimpleContextFactory
org.osjava.sj.root=${project.build.directory}\\test-classes\\jndi
org.osjava.sj.colon.replace=--
org.osjava.sj.delimiter=/
```
**src/test/resources/jndi/java--comp/env/jdbc/ds.properties:** 
```
type=javax.sql.DataSource
driver=oracle.jdbc.OracleDriver
url=${db.url}
user=${db.user}
password=${db.password}
```

<a href="http://commons.apache.org/configuration/">commons-configuration</a>
