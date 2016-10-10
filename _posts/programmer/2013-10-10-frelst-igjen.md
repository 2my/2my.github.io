---
title: Frelst, igjen…
categories: [work]
layout: "posts"
---

# Frelst, igjen…
Hvert år, omtrent på denne tia, skjer det. JavaZone er over og jeg står igjen, litt klokere, med fornya tro og mer vann på mølla.  
Pussig nok ble jeg mest inspirert av ting jeg egentlig visste fra før. Resonans? Det er godt å være enig, men dum som jeg er, har jeg prøvd å se litt mer kritisk på det som ble sagt.

## Drep produkteier-rollen ([video][kill])
Tim Berglund vil brenne alt som minner om tvang eller ufrihet, som:

* sjefs-rollen
* feriedager
* fast arbeidstid
* fast arbeidssted

Også produkteier-rollen vil han brenne, så vi skal få jobbe direkte med kunder.

Det han vil bygge opp er selvbestemmelse, mestring og mening. Faktorer som gir tilfredse ansatte som yter maksimalt. Han vil at utviklere skal kjenne forretninga, lære domenet, ha kontakt med kunder og like dem.  

Vellykkede selskaper som GitHub, SparkFun og Valve gjør dette. Det er nok enklere for disse å gjøre slike grep enn for oss som jobber i mindre sexy bransjer, men Berglund utfordra oss til å prøve å få det til.  

### Flere veier til lykken
Jeg har i noen perioder jobbet med slike betingelser, og kan skrive under på at det var givende:

* Jeg jobba i en forskningsgruppe ved universitetssykehuset i Linkøping en vinter. Jeg jobba nesten alle mine våkne timer og stortrivdes hele tiden.
* Jeg har lagd et par utilities som Open Source prosjekter. Det var vanskelig å legge fra seg disse klokka 2 om natta selv om jeg visste at ungene ville vekke meg mange ganger før 7.
* som fagansvarlig hos Antares fant jeg selv på hva jeg ville gjøre, hvor og når jeg ville. Det ble lite søvn, men mye tilfredshet.  

(Det er altså mulig å finne friheten i forskning, åpen kildekode prosjekt, stillinger med ansvar, eller egen forretning)

Kundekontakt kan være bra det, men det er ikke noe trylleslag. Det første prosjektet mitt gjorde jeg sammen med kunde. Jeg håndtere ikke prosjektet og kundedialogen bra nok, og vi utvikla et produkt bare vi to kunne bruke. Jeg ante hvor det gikk i løpet av det andre året, de siste månedene grudde jeg meg for å gå på jobb.  
Kundekontakt er enklest hvis man er sin egen kunde. Jeg har truffet svært få kunder som vil bruke (mye) tid i et prosjekt. De fleste har annet arbeid å gjøre. De som engasjerer seg kommer ofte inn med spesifikke ting de vil ha gjort, og viser lite engasjement ut over det.  
Jeg tror ["Contextual Design"][cd] er beste måten å komme i kundedialog og drive den videre: dra ut til kunden, observér og ta dialogen der, men selv det har vært vanskelig å få til av forskjellige grunner.  

Berglund's revolusjon går tilsynelatende lengre enn det vi her på berget har gjort, så hvorfor opplever jeg mye av frihetene han agiterer for? Kanskje fordi partene i arbeidslivet har jobba seg den veien, demokratisert, endra rollene, myka opp, innført fleksitid og hjemmekontor. Titler er devaluert, ledelse er blitt en rolle som skal fylles, og organisasjonene kan (om-) organisere seg i hytt og vær, uten at noen rasler med fyrstikkene.  
Mitt bidrag har vært å dra arkitektur mot lettvekts-løsninger, med den viktige egenskapen at man ikke må være inne på kontoret for å gjøre jobben. Det har gjort underverker.  

Stor frihet og ansvar er vidunderlig, men også krevende. Det krevs erfaring eller god hjelp om en utvikler som skal fungere godt i organisasjonen som Berglund beskriver. Struktur gir trygghet, og kan brukes til å bygge ansatte opp, så de senere kan vokse og mestre mer frihet.  

## Breaking the Monolith ([video][break])
Jeg er kanskje en destruktiv type, men skammer meg ikke over å ville knuse monolittene - de svære systema som er så nedsylta i teknisk gjeld at de ikke lar seg endre eller utvide. Stefan Tilkov beskrev en arkitektur for smidighet (manøvrerbarhet) og hvordan man kan løse opp i en monolitt. Basert på hans og Innoq sin erfaring.  

I steden for å bygge ett stort system, så bygger man flere undersystem. Undersystema er isolerte fra hverandre, med blandt annet egen persistens, UI, utvikling og produksjonssetting samt begrenset interaksjon med andre system.

Arkitektur gjøres på 3 nivåer:
* Domene-arkitekturen deler systemet i undersystemer, og sier hva som skal gjøres i hvert undersystem.
* Makro-arkitekturen spesifiserer grensesnitt mellom undersystemene og omgivelsene.
* Mikro-arkitektur for hvert undersystem er mest mulig fri.

Slik får man mye frihet i undersystema, som blir små og får en fokusert arkitektur. Man unngår containere som løser alle de andre verdensproblema også.  

### Smågodt
Lite, enkelt og fritt - jeg liker det. Spesielt fordi mange små system er lettere å håndtere enn et stort hvis man kommer i uføret med høy teknisk gjeld.

Jeg ville sammenstille dette med Berglunds herjinger, for:
* Størst mulig frihet for undersystema => autonomi.
* Mindre og mer fokuserte system gir lettere mestring.
* Meningsløst dill fjernes - som bygging av irrelevant kode eller deployment til J2EE container under utvikling.
* Den enkeltes bidrag er mer og raskere synlig.
* Flere forskjellige system = mer valgfrihet.
* Det er lettere å utvikle utenfor kontoret.


Hype-varsel: Den siste tia har Micro-Services og fokuserte rammeverk kommet mer frem i rampelyset. Hvis det passer med det som skal bygges, så mener jeg man bør strebe etter en slik arkitektur.  


Going Reactive: Event-Driven, Scalable & Resilient Systems
Principles of Reactive Programming
  [break]: http://jz13.java.no/presentation.html?id=5b3d6ab9  "Video from JavaZone"
  [kill]: http://jz13.java.no/presentation.html?id=159f8623  "Video from JavaZone"
  [cd]: http://en.wikipedia.org/wiki/Contextual_design  "Wikipedia article"
