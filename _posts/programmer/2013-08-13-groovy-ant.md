---
title: "Groovy Ant"
layout: "posts"
date: "2013-08-13 07:56:00"
updated: "2013-08-13 07:56:28"
blogger:
    siteid: "7706585097329252419"
    postid: "2033203167136617158"
categories: 
---

In case you cannot use <a href="http://www.gradle.org/">Gradle</a>, here is how to get <a href="http://groovy.codehaus.org/The+groovy+Ant+Task">Groovy task in Ant</a>, and how to call a macro from <a href="http://groovy.codehaus.org/">Groovy</a>.

```xml
 <taskdef classname="org.codehaus.groovy.ant.Groovy" name="groovy">

  <classpath>

    <pathelement location="bin/groovy-ant-2.1.4.jar">

    <pathelement location="bin/groovy-all-2.1.4.jar">

  </pathelement></pathelement></classpath>

 </taskdef>

 <target name="test-groovy">

  <groovy>

   println "Hello World"

   def ant = new AntBuilder( project ) 

   ant.testmacro( dir: "qwerty" ) 

  </groovy>

 </target>

 <macrodef name="testmacro">

  <attribute name="dir">

  <sequential>

   <echo message="parameter: @{dir}">

  </echo></sequential>

 </attribute></macrodef>
```