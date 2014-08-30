---
title: "Scala - learning notes"
categories: 
layout: "post"
date: "2009-11-26 12:51:00"
updated: "2010-05-16 09:59:13"
blogger:
    siteid: "7706585097329252419"
    postid: "3231829722028836138"
---

### Plan

Do  it standing, about same mix of  slides and coding as before, handouts.

Slide:  Tom Waits + install

Slide/Code: fire up scala and show off syntax (REPL)

Slide:  motivation

Slide: My verdict + References

Slide/Code: Bonus section

### Presentation 
 “Your hands are like dogs, going to the same places they’ve        been. You have to be careful when playing is no longer in the        mind but in the fingers, going to happy places. You have to        break them of their habits or you don’t explore; you only play        what is confident and pleasing. I’m learning to break those        habits by playing instruments I know absolutely nothing about, like a bassoon or a waterphone.”—Tom Waits

<a onblur="try {parent.deselectBloggerImageGracefully();} catch(e) {}" href="http://farm4.static.flickr.com/3181/2711674628_028c1d02bb.jpg"><img style="display: block; margin: 0px auto 10px; text-align: center; cursor: pointer; width: 471px; height: 500px;" src="http://farm4.static.flickr.com/3181/2711674628_028c1d02bb.jpg" alt="" border="0" /></a>(Picture from <a href="http://www.flickr.com/photos/conchur/2711674628/sizes/m/">flickr</a> / Conor Lawless).

### Install
Download zip-file, unzip, set SCALA_HOME and add to PATH.

Then: <a href="http://www.scala-lang.org/node/91">install plugins</a> for  NetBeans (6.7+, prefer 6.8) and eclipse (3.5+).

I did best letting NetBeans handle project (not Maven).

### Syntax / REPL
scala.bat: Quick Read Evaluate Print  Loop

<table style="text-align: left; width: 634px; height: 449px;" border="1" cellpadding="2" cellspacing="2">

<tbody>

  <tr>

    <td style="font-weight: bold; text-align: center;">Code</td>

    <td style="font-weight: bold; text-align: center;">Points

to make</td>

  </tr>

  <tr>

    <td>

    <pre><span class="Keyword">class</span> <span class="ST1">PhoneNumber</span>( <span class="Keyword">val</span> <span class="ST2">kind</span>: <span class="ST3">String</span>, <span class="Keyword">var</span> <span class="ST4">no</span>: <span class="ST3">String</span> ) {

<span class="Keyword"> override</span> <span class="Keyword">def</span> <span class="ST5">toString</span>(): <span class="ST3">String</span> = {

<span class="ST4">   no</span> + <span class="StringLiteral">" ("</span> + <span class="ST2">kind</span> + <span class="StringLiteral">")"</span>

}

}</pre>

    </td>

    <td>switch to name: type

val / var / def

primary constructor

Concise</td>

  </tr>

  <tr>

    <td>

    <pre><span class="Keyword">object</span> <span class="ST0">PhoneNumber</span>{

<span class="Keyword"> def</span> <span class="ST5">apply</span>( <span class="ST6">kind</span>: <span class="ST3">String</span>, <span class="ST6">no</span>: <span class="ST3">String</span> ) : <span class="ST3">PhoneNumber</span> = {

<span class="Keyword">   new</span> <span class="ST3">PhoneNumber</span>( <span class="ST6">kind</span>, <span class="ST6">no</span> )

}

}</pre>

    </td>

    <td>object, no statics

apply is "default method"</td>

  </tr>

  <tr>

    <td>

    <pre><span class="Keyword">val</span> <span class="ST7">phonebook</span> = <span class="ST8">Map</span>(

<span class="StringLiteral"> "Tommy mobil"</span> -> <span class="ST8">PhoneNumber</span>( <span class="StringLiteral">"cell"</span>, <span class="StringLiteral">"92012201"</span> ),

<span class="StringLiteral"> "ICE Medisinsk"</span> -> <span class="ST8">PhoneNumber</span>( <span class="StringLiteral">"work"</span>, <span class="StringLiteral">"113"</span> )

)</pre>

    </td>

    <td>Expressive</td>

  </tr>

  <tr>

    <td>println( <span class="ST7">phonebook</span>(<span class="StringLiteral">"Tommy mobil"</span> ).<span class="ST4">no</span> )</td>

    <td>Concise</td>

  </tr>

  <tr>

    <td><span class="ST7">phonebook</span>.foreach(tuple => println( <span class="ST6">tuple</span>.<span class="ST2">_1</span> + <span class="StringLiteral">":"</span> + <span class="ST6">tuple</span>.<span class="ST2">_2</span> ))</td>

    <td>High-level

functional iteration</td>

  </tr>

  <tr>

    <td><span class="number">1.1</span>.+(<span class="number">2.2</span>)

    <span class="number">1</span> until <span class="number">10</span></td>

    <td>Pure OO

operator mode for methods</td>

  </tr>

  <tr>

    <td>

    <pre><span class="Keyword">val</span> <span class="ST0">xmlE</span> = <span class="xml"><</span><span class="xml">a</span> <span class="xml">href</span>=<span class="StringLiteral">"index.html"</span><span class="xml">></span> {<span class="number">3</span> + <span class="number">4</span>} <<span class="xml">/</span><span class="xml">a></span><span class="xml"></span>

(<span class="ST0">xmlE</span> \ <span class="StringLiteral">"@href"</span>).text

</pre>

    </td>

    <td>Pragmatic</td>

  </tr>

</tbody>

</table>

.

### Motivation

<span style="font-weight: bold;">Evolution, not revolution</span>: Java-like,   interoperates with java  (seamlessly). 
	* can extend java  classes
	* can   implement  java interfaces
	* understands java  generics
	* uses   java  primitives

Leads you into **functional  programming.

Easy  to do easy  stuff, AND facilitates the hard stuff.

**More up2date** language - builds on java lessons, adds:

	* Facilitates   DSL  with several short-hand notations
	* Traits (~multiple  inheritance)
	* ++

One vision (Martin Odersky), not designed by   comitee

Pragmatic

"I can honestly say if someone had shown  me  the Programming Scala  book by by Martin Odersky, Lex Spoon &amp;  Bill  Venners back in 2003 I’d  probably have never created Groovy." —  James  Strachan

"If I were  to pick a language to use today other  than  java, it would be Scala" —  James Gosling (from before he left  Oracle)

### My verdict: lead me into...

Wonderful way of coming from Java to Functional programming. I started out writing java-like OO, but wolfed out by the end of my second 3-hour session.

The book fuelled this transformation.

Scala feels very good so far, I now like Java less...

### References

<a href="http://www.scala-lang.org/">Scala site</a>.

Book "Programming in Scala" (Odersky++) is very good for learning, not so for  reference.

<a href="http://www.ibm.com/developerworks/views/java/libraryview.jsp?search_by=scala+neward">The busy Java developer's guide to Scala</a>: articles on DeveloperWorks

From JavaZone 09:

	* <a class="library_activeTitle" onclick="this.blur();return false;" href="http://tcs.java.no/tcs/?id=AF4C824A-D6A8-417E-A68A-FFC35B71DE8E">Pragmatic  Real-World Scala</a>:
	* <a href="http://tcs.java.no/tcs/?id=61D7856D-637F-42E0-9E5E-3DA2D977B372">Scala + Wicket</a>...
	* <a href="http://tcs.java.no/tcs/?id=57E1B7DF-0500-4670-BB2A-8AB000BEA6DD">State, You're doing it Wrong</a>...

### Bonus section
Start with Java Discovery and refactor a suitable class:

	* common.ServiceDescription (for properties and basics) NB! keep scala-code for equals / canEqual

Show off in code

<table style="text-align: left; width: 699px; height: 276px;" border="1" cellpadding="2" cellspacing="2"> <tbody> <tr> <td style="font-weight: bold; text-align: center;">Code</td> <td style="font-weight: bold; text-align: center;">Points to make</td> </tr> <tr> <td>TestServer</td> <td>object and main</td> </tr> <tr> <td>client.v2.Notifier</td> <td>operators</td> </tr> <tr> <td>client.ServiceBrowser:

	* class extends with
	* tryto
	* getReplyDescriptor
 </td> <td>traits

Function is first-class object

Option + match</td> </tr> <tr> <td>sclanb.Main.recurse2</td> <td>Closures, and how crazy I got </td> </tr> <tr> <td>sclanb.Main</td> <td>

</td> </tr> <tr> <td>client.ServiceBrowserListener</td> <td>abstract, no interface</td> </tr>  <tr> <td><a href="http://www.cs.helsinki.fi/u/wikla/OTS/Sisalto/examples/swing/FirstSwingApp.scala">FirstSwingApp</a>.</td> <td>DSL, Swing</td> </tr>   <tr> <td>Code from <a href="http://www.cs.helsinki.fi/u/wikla/OTS/Sisalto/examples/html/ch30.html">ch30</a></td> <td>Actors</td> </tr> </tbody> </table>
