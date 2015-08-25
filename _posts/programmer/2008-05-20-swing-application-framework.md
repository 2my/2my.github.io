---
title: "Architecture: Swing, Maven2, NetBeans etc."
categories: [guicode, tg, architecture]
layout: "posts"
date: "2008-05-20 04:03:00"
updated: "2008-10-03 14:47:38"
blogger:
    siteid: "7706585097329252419"
    postid: "2385788718381454948"
---

### Development setup

	* Maven
	* NetBeans, plugins

Modules: swing-gui (client), service (ejb, ws, xml-dummies), model, parent

	* Unit tests, test-data
	* Code harness
	* Libraries / Frameworks: SWAF, Hibernate

### Maven in NetBeans
I use NetBeans (6.1 ) with maven plugin, as described <a href='http://wiki.netbeans.org/MavenBestPractices'>here</a>. should maybe read <a href='http://blogs.sun.com/geertjan/entry/hello_world_maven_based_netbeans'>10 Steps to Happiness with Maven and the NetBeans Platform</a>.

Maven is found on <a href='http://maven.apache.org/'>Apache site</a>.

### Swing
I found a host of useful examples on <a href='http://www.java2s.com/Code/Java/Swing-Components/Grid-Table.htm'>java2s</a>, (with Outline=TreeTable <a href='http://www.java2s.com/Open-Source/Java-Document/IDE-Netbeans/web.core/org.netbeans.swing.outline.htm'>examples</a>) and in "<a href='http://www.amazon.com/Swing-Hacks-Tips-Tools-Killer/dp/0596009070/ref=pd_bbs_sr_1?ie=UTF8&amp;s=books&amp;qid=1216647942&amp;sr=8-1'>Swing Hacks</a>". I use some stuff from <a href='http://swinglabs.java.sun.com/'>SwingLabs</a>, check <a href='http://swinglabs.org/docs.jsp'>documentation</a>.

### MVC + Swing
I use <a href='https://appframework.dev.java.net/'>Swing Application Framework</a>, note that this Framework is "bleeding edge" according to self, but seeing it was used by Matisse NetBeans plugin, I concluded I might as well try it. (Alternatives: Eclipse RCP, NetBeans Platform, and Spring RCP (cf <a href='http://java.dzone.com/news/practical-introductions-spring'>intro</a>) and <a href='http://www.jgoodies.com/'>JGoodies</a>).

I was pointed to <a href='https://fuse.dev.java.net/'>Swing Fuse</a> by this article on <a href='http://www.javalobby.org/articles/swing-fuse/'>DI with Swing Fuse</a>. Worth also to look up <a href='http://code.google.com/p/google-guice/'>Google guice</a>.

SDN has a nice article on <a href='http://java.sun.com/developer/technicalArticles/javase/mvc/index.html'>Java SE Application Design With MVC</a>.  
On undo/redo from <a href='http://www.javaworld.com/javaworld/jw-06-1998/jw-06-undoredo.html'>JavaWorld</a>,  or <a href='http://www.softwareresearch.net/site/teaching/WS0708/se1/material/undo_redo_mvc.pdf'>MVC-alternative</a>.  
Check Holub's <a href='http://www.javaworld.com/javaworld/jw-01-2004/jw-0102-toolbox.html'>More on getters and setters</a>.

### Unit testing
Unit testing the Swing GUI may not be worthwile, cf. **<a href='http://www.devx.com/Java/Article/9614/0/page/2'>jfcUnit Tests Swing GUIs</a>** (sidebar).  
Injection of test data can be done with <a href='http://www.castor.org/'>Castor</a>.

### More
Check the <a href='http://weblogs.java.net/blog/timboudreau/archive/2008/08/the_capability.html'>Capability Pattern</a>.

