---
title: "Groovy Ant"
layout: "post"
permalink: "/2013/08/groovy-ant.html"
uuid: "2033203167136617158"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-2033203167136617158"
date: "2013-08-13 07:56:00"
updated: "2013-08-13 07:56:28"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "2033203167136617158"
    comments: "0"
categories: 
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

<div class="css-full-post-content js-full-post-content">
In case you cannot use <a href="http://www.gradle.org/">Gradle</a>, here is how to get <a href="http://groovy.codehaus.org/The+groovy+Ant+Task">Groovy task in Ant</a>, and how to call a macro from <a href="http://groovy.codehaus.org/">Groovy</a>.<br /><br />&nbsp;&nbsp;&nbsp; <taskdef classname="org.codehaus.groovy.ant.Groovy" name="groovy"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <classpath><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <pathelement location="bin/groovy-ant-2.1.4.jar"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <pathelement location="bin/groovy-all-2.1.4.jar"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </pathelement></pathelement></classpath><br />&nbsp;&nbsp;&nbsp; </taskdef><br /><br />&nbsp;&nbsp;&nbsp; <target name="test-groovy"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <groovy><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; println "Hello World"<br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; def ant = new AntBuilder( project ) <br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; ant.testmacro( dir: "qwerty" ) <br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </groovy><br />&nbsp;&nbsp;&nbsp; </target><br /><br />&nbsp;&nbsp;&nbsp; <macrodef name="testmacro"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <attribute name="dir"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <sequential><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <echo message="parameter: @{dir}"><br />&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </echo></sequential><br />&nbsp;&nbsp;&nbsp; </attribute></macrodef><br /><br /><br />
</div>