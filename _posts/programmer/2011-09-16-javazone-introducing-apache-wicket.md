---
title: "JavaZone: introducing Apache Wicket"
layout: "posts"
permalink: "/2011/09/javazone-introducing-apache-wicket.html"
uuid: "896052624377724457"
guid: "tag:blogger.com,1999:blog-7706585097329252419.post-896052624377724457"
date: "2011-09-16 13:30:00"
updated: "2011-09-16 13:33:45"
description: 
blogger:
    siteid: "7706585097329252419"
    postid: "896052624377724457"
    comments: "0"
categories: 
author: 
    name: "Tommy"
    url: "http://www.blogger.com/profile/16604372255669213767?rel=author"
    image: "http://static.flickr.com/93/279356255_fb52db20a0_o.jpg"
---

Presentation from JavaZone 2011: http://javazone.no/incogito10/events/JavaZone%202011/sessions/Introducing%20Apache%20Wicket
Video posted to http://vimeo.com/28791557
Notes:

	* 7 years old framework, Wicket 1.5 just released
	* Component oriented, using just java+html
	* **Used by:** AdScale, WalMart, MeetMoi, fabulous40...
	* **Just html:** elements linked to wicket by attributes: <p wicket:id="foo">, no imperative markup in view.
	* **Just Java:** no logic in markup, Components are POJOs, No xml
	* **Components:** Manipulate markup, Render content, Receive events (onClick)
	* **Models:** data to / from Components, transform data
	* **Behaviors:** Decorator / Adapter for Component, manipulate markup of Component, can receive events (onClick), Add Ajax unctionality to Components
	* **Wicket projects:** Apache Wicket (core, integration to Spring...), Wicket stuff (components), Seam for Apache Wicket, WiQuery (jQuery), Leg before Wicket (archetypes), Apache Isis (DDD framework), Jolira Tools, Visural Wicket (components)...
	* **Quick start:** use Maven, http://wicket.apache.org/start/quickstart.html
	* **Some examples:** Hello World, click-counter, sign-up
	* **Navigation:** Overview and some detail on: External link, Bookmarkable link, Action
	* **Validators:** Overview, simple example and list of provided validators
	* **jQuery integration:** WiQuery overview and example
	* **JqZoom:** Example, zoom on image, how to integrate
	* **Development / Deployment mode:** List differences and show some features
	* **WicketTester:** Tests components, UI, Ajax, without starting server, runs in IDE, ant, maven
	* **New in 1.5:** Html5 input types, component event bus, some new components, improved internals, simpler request cycle, and more
	* **Component event bus:** pre/post example
	* **Wicket 6:** next version, preliminary list of features. Shorter release cycle.
	* **Q&amp;A:** How do components handle history button? Do you endorse Wicket WebBeans for rapid development?
