---
title: Nord Pool Spot AS (Kunde)
categories: [cv customer]
layout: "posts"
---

Nord Pool Spot AS driver Europas første og fremste kraftbørs for områdene Norden, Baltikum og UK.
Tommy var leid inn i 3,5 år, prosjektene listes under.

2011.11 - 2015.05	80%
Nord Pool Spot
SW-arkeolog, utvikler og tester, utviklingsarkitekt, løsningsarkitekt.
	EMDS
Beskrivelse: EMDS er samlenavnet på systemene som utvikles og drives i avdelinga på Lysaker, bl.a:
	* NpSia: JMS tjenester på jBoss henter og mottar data fra alle parter i kraftproduksjon og ­distribusjon, inklusiv interne og eksterne handelssystem. Data lagres, behandles og videreformidles til børsmedlemmer, internett, handelssystem, partene i kraftdistribusjonen og myndigheter med EU.
	* Bænkers: Swing GUI app som overvåker og varsler når data ikke kommer innen frist, og lar brukeren legge inn manglende data manuelt.
	* Coma: Cocoon web applikasjon for konfigurasjonsstyring.
	* Feed Manager: Cocoon web applikasjon for konfigurasjon av datautsending.
	* FtpApp: java prosess som utveksler filer på ftp. Overvåkes og restartes automatisk.
	* VPP: Sving MVC applikasjon for nominering på videresalgs-kontrakter.
Tommy tok over og releasa Bænkers 1.0, og gjorde 3 utslipp til med utvidelser av overvåkingen.
I Feed Manager implementerte han UI og forretningslogikk for å koble produkter og publiseringskanaler.
VPP-utviklerne var ute, så han fant selv ut av applikasjon og datamodell, oppdaterte database og fiksa problem.
Var med å oppdatere all kode, data og oppsett så EMDS håndterte sommertidsoverganger med 23 og 25 timer.
I NpSia gjorde han mange prosjekt:
Designet og implementerte konfigurerbart mottak av Entso-E ESS meldinger, som med tiden er satt opp til å ta imot fysiske data fra LitGrid, Elering, AST og StatNett.
La ftp-funksjonene i en ekstern, overvåka prosess som restartes automatisk ved heng. Designet og implementerte overvåker og overvåket prosess.
Lagde installasjonsscript for hver tjeneste, og splitta ut konfigurasjonen for tjenestene, så de kunne installeres og oppdateres isolert fra hverandra.
Oppgraderte NpSia-base fra jBoss 4 til jBoss 7.
Lagde en wrapper som gjorde at vanlige database-tabeller kunne vises i tidsserie-modellen.
Spesifiserte, designa og implementerte rapportering av overføringskapasitet (ntc) til Entso-E (EU).
Var med å designe, implementere og teste rapportering av data fra kraftprodusenter, nettoperatører og kraftbørsen  til Entso-E i henhold til EUs «Transparency Regulation» for kraftmarkedene. Ansvarlig for generisk internt dokumentformat og transformasjon av dette til standardisert format. Samlet krav, designet og implementerte komponenter for å  rapportere day-ahead prices, reservoir filling, unavailability og net transfer capacity (intra-day, day-ahead og forecast).
Teknologi: Java, Scala, Groovy, JavaScript med json og jQuery UI, rest­klient, xml, xsd, xmlbeans, Velocity, Java trådhåndtering (concurrency), ftp, Swing, JavaFx, Spring, jBoss4, JMS, Cocoon, JDBC, Sybase, sql, Ant, Maven, UML, BPMN, Confluence med Gliffy, MarkDown og Entso­E bransjestandarder: ESS, ECAN og rammeverk for rapportering ihht EUs Transparency Regulation.