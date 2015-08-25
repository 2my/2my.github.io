---
title: "Breaking the Monolith from JavaZone 2013"
categories: [work]
layout: "posts"
date: "2013-10-10 23:24:25"
---

Check also Antares insight [post][post].


# Breaking the Monolith ([video][break])
Stefan Tilkov beskrev en arkitektur for smidighet (manøvrerbarhet) og hvordan man kan løse opp i en monolitt. Basert på hans og Innoq sin erfaring. Med monolitt mener han systemer med millioner kodelinjer - de svære systema som er så nedsylta i teknisk gjeld at de ikke lar seg endre eller utvide. "Nobody designs a monolith on purpose", men det blir slik fordi man tenker at 1 prosjekt = 1 system.


I steden for å bygge ett stort system, så bygger man flere undersystem. Undersystema er isolerte fra hverandre, med:
	* egen persistens
	* intern, separat logikk
	* egen domenemodell
	* egen implementasjonsstrategi
	* eget UI
	* egen utvikling
	* begrenset interaksjon med andre system.
	* autonom produksjonssetting og drift

Nevnte [12 factor app][12fact], Dropwizard og reactive. Fra 12 factor:
	* separat, kjørbar prosess
	* tilgang via standard porter og protokoller
	* shared-nothing model
	* horisontal skalerbart
	* rask start og recovery

Arkitektur gjøres på 3 nivåer:
	* Domene-arkitekturen deler systemet i undersystemer, og sier hva som skal gjøres i hvert undersystem.
	* Makro-arkitekturen spesifiserer grensesnitt mellom undersystemene og omgivelsene.
	* Mikro-arkitektur internt for hvert undersystem er mest mulig fri.

![Necessary rules and guidelines](../_images/referat/breaking_the_monolith/necessary_rules_and_guidelines.png)  
![Main objectives over time](../_images/referat/breaking_the_monolith/main_objectives_over_time.png)

## Migration
![prerequisites](../_images/referat/breaking_the_monolith/prerequisites_for_breaking_out.png)
![procedure](../_images/referat/breaking_the_monolith/breaking_out_of_monolith.png)
	1. Close for change
	2. Enable integrateability (authentication and navigation)
	3. Create new system for new feature
	4. Copy and isolate


  [break]: http://jz13.java.no/presentation.html?id=5b3d6ab9  "Video from JavaZone"
  [12fact]: http://12factor.net  "The 12 factor App"
  [post]: http://insight.antares.no/frelst-igjen-2013/  "Bloggpost on Antares insight"
