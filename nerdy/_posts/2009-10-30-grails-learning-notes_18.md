---
title: "Grails - learning notes"
categories: 
layout: "post"
date: "2009-10-30 07:28:00"
updated: "2009-11-26 10:38:31"
blogger:
    siteid: "7706585097329252419"
    postid: "5326010484914720011"
---

## Hello <a href="http://grails.org/">Grails</a>!
<a href="http://www.youtube.com/watch?v=RDM75-oXGmQ">Trailer</a>.

Download and unpack Grails, set GRAILS_HOME environment variable and update PATH. It works

```

grails create-app mapp

cd mapp

grails create-domain-class mapp.site.Site

grails create-controller mapp.site.Site```

Import project into Eclipse or NetBeans (Grails creates Eclipse project)

Add fields and toString() to model

Add dynamic scaffold property to controller (def scaffold=Site)

```grails run-app```

Run and show off dynamicity by adding fields to model, and index-method.

```

grails generate-all mapp.site.Site

```

Step back and explain:

	* CoC: Show mapping url -> controller+view

	* MVC: Jump to "Domain Model", "Controller", "GSP"
	* Configuration: Set up database: store and update

Code a test

<span style="font-size:180%;">Why?</span>

No configuration, zero overhead, immediate turnaround.

High-productivity web MVC framework for the Java platform

	* CoC: easy to find your way to domain-objects, controllers, services, views
	* Ready-to-use development environment (+test and production)
	* Scaffolding (even dynamic): quick-start

	* Familiar: On the shoulders of Java eco-system, Hibernate, Spring, Groovy, SiteMesh

	* GORM: DAO-layer implemented by MOPing
	* Good Ajax-support
	* Small stuff: test support, generating (web-)services. flash-scope, Web-flow, filters

	* Easily extensible, 312 <a href="http://www.grails.org/plugin/category/all">Plugins</a> at last count. Grails main function is plugin management.

<span style="font-size:180%;">Domain Model</span>

You write POGOs, GORM provides DAO-functionality through mixins:

	* get, list, save, delete

	* findByName, findBy...And...
Validation provided.

Error container provided: siteInstance.errors

Command Object: domain object that is not persisted

<span style="font-size:180%;">Controllers

</span>Scaffolding: CRUD generated. Provides a nice starting point.

Comment on first Controller generated:

	* list(): where did Site.list() come from?
	* list(): return statement optional.

	* show(): what is flash-scope?
	* show(): Model passed to view: Controller properties or returned map [key:value].
	* edit(): same as show() but different view (by convention)
	* update(): siteInstance.properties = params

	* index(): will be default action if not overridden by eg. defaultAction = 'list';

<span style="font-size:180%;">View (GSP)

</span>JSP works, but GSP takes advantage of Groovy, and is remarkably similar

GSP taglib similar to Struts2 + jstl

<span style="font-size:180%;">Services

</span>Transactional boundaries, automagicaly injected.

<span style="font-size:180%;">Google app-engine</span>

Fra http://grails.org/plugin/app-engine og http://www.morkeleb.com/tag/grails/

sørge for at domeneklasser ligger under en pakke

```grails install-plugin app-engine```

(valgte jpa)

```grails install-plugin gorm-jpa```

La til annotasjoner (@Entity)

```

grails app-engine run

grails set-version 1

grails app-engine package```

(første gang $APPENGINE_HOME/bin/appcfg.sh update ./target/war)

```

grails app-engine deploy

```

Go 2 <a href="http://nerdetom.appspot.com/">http://nerdetom.appspot.com/</a>

<span style="font-size:180%;">IDE Support</span>

Approaching acceptable, maybe good if my PC was working fine.

NetBeans: syntax colored, some autocomplete, access to grails-commands, direct junit debug

Eclipse: some syntax colored, some autocomplete, debug of junit-tests.

IDEA: supposedly best-of-breed.

Debugging: remote (```grails-debug run-app```) on port 5005

<span style="font-size:180%;">Recommended reading</span>

<a href="http://grails.org/">http://grails.org</a>

<a href="http://www.morkeleb.com/tag/grails/">http://www.morkeleb.com/tag/grails/</a>

Book: "The Definitive Guide To Grails" 2nd edition by Graeme Rocher and Jeff Brown. Comprehensive and readable guide, details Enterprise integration issues.

<a href="http://www.ibm.com/developerworks/views/java/libraryview.jsp?search_by=mastering+grails">Mastering Grails</a> on DeveloperWorks.

<a href="http://tcs.java.no/tcs/?id=0DEDB0F8-E4E5-4969-A3C6-5AFFE36A6EB0">Agile Enterprise Development with Groovy and Grails</a>: From JavaZone 09

<a href="http://www.youtube.com/watch?v=-rutX0I6NxU">Outro</a>.

<div class="zemanta-pixie"><img src="http://img.zemanta.com/pixy.gif?x-id=55129da4-bcf9-820f-af73-4bf7d37a01e4" alt="" class="zemanta-pixie-img" /></div></div>

