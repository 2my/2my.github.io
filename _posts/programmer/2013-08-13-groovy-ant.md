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

&nbsp;&nbsp;&nbsp; <taskdef classname="org.codehaus.groovy.ant.Groovy" name="groovy">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <classpath>

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <pathelement location="bin/groovy-ant-2.1.4.jar">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <pathelement location="bin/groovy-all-2.1.4.jar">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </pathelement></pathelement></classpath>

&nbsp;&nbsp;&nbsp; </taskdef>

&nbsp;&nbsp;&nbsp; <target name="test-groovy">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <groovy>

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; println "Hello World"

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; def ant = new AntBuilder( project ) 

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; ant.testmacro( dir: "qwerty" ) 

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </groovy>

&nbsp;&nbsp;&nbsp; </target>

&nbsp;&nbsp;&nbsp; <macrodef name="testmacro">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <attribute name="dir">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <sequential>

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; <echo message="parameter: @{dir}">

&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; </echo></sequential>

&nbsp;&nbsp;&nbsp; </attribute></macrodef>

</div>