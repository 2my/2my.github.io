---
title: "GeoCoding and maps in Swing"
categories: 
layout: "post"
date: "2008-10-17 10:33:00"
updated: "2008-10-17 10:33:00"
blogger:
    siteid: "7706585097329252419"
    postid: "3000837848680164914"
---

## Maps

Started with <a href='http://today.java.net/pub/a/today/2007/10/30/building-maps-into-swing-app-with-jxmapviewer.html'>article from java.net</a>., which details how to use the JxMapViewer from <a href='http://www.swinglabs.org/'>SwingLabs</a>.

<big>Web-based maps</big>

Use <a href='http://www.openlayers.org/'>OpenLayers</a> to wrap service provider.

For Ajax-maps, check <a href='http://24ways.org/2007/get-to-grips-with-slippy-maps'>this article</a>, or <a href='http://www.ibm.com/developerworks/web/library/x-geomap1/index.html?ca=drs-'>Tap into the Google Geocoder Web service</a>. or even <a href='http://www.ibm.com/developerworks/web/library/x-geomap2/index.html?ca=drs-'>Overlay data on maps using XSLT, KML, and the Google Maps API, Part 2</a>.

## GeoCoding
Første søk var oppløftende, sjekk <a href='http://irb.no/-/bulletin/show/65093_postnummer-geodata'>irb.no : Postnummer =&gt; geodata</a>.

<a href='http://www.statkart.no/'>Statkart</a> er grei å sjekke, men dataene nås først og fremst gjennom NorKart, Ugland IT...

Ugland IT, <a href='http://www.uglandit.com/produktdetaljer.php?visprodukt=6474'>FlexiMap Online</a>, <a href='http://www.uglandit.com/produktdetaljer.php?visprodukt=6472'>FlexiMap Locator</a>.

Foretrekker <a href='http://www.geodata.no'>GeoData</a>. (<a href='http://arcweb.esri.com/arcwebonline/index.htm'>ESRI</a>-baserte tjenester)

NorKart: **FixMe**.

geoNorge: **FixMe**.

## Coordinate conversion
This <a href='http://www.ibm.com/developerworks/java/library/j-coordconvert/index.html'>article </a>explains the works. Try libraries: <a href='http://geotools.codehaus.org/'>GeoTools</a>, <a href='http://www.jstott.me.uk/jcoord/'>JCoord</a> (cf. this <a href='http://forums.java.net/jive/thread.jspa?messageID=276692'>message</a>).

EPSG:32633 = WGS_1984_UTM_Zone_33N: 6648970N 255101E

EPSG:4326 = Lat/lon (GCS_WGS_1984): 59.90530N 10.61976E

900913 = Google special projection (is Mercator): 8378684N 1182185E

epsg:54004 = Mercator (World_Mercator)

A degree of longitude at the equator is 111.2 kilometers. A minute is 1853 meters. 

A second is 30.9 meters. For other latitudes multiply by cos(lat).

cos((2 * PI * 66) / 360) = 0.406736643

For reference systems / epsg codes, see: <a href='http://inovagis.terradue.com/giserver/epsg.asp'>GIServer</a> or <a href='http://www.spatialreference.org/'>spatialreference</a>.

http://www.radicalcartography.net

### Gratis-tjenester:
Norsk <a href='http://wiki.openstreetmap.org/index.php/WikiProject_Norway'>openstreetmap</a> prosjekt, men det ser ut til å være mangelfullt.

Posten sin <a href='http://epab.posten.no/Norsk/Nedlasting/NedlastingMeny.htm'>nedlastingsside</a> (gir kommunenr fra postnr, 1 skritt til for posisjon, men det blir veldig unøyaktig).

<a href='http://www.geonames.org/'>Geonames</a> funker sånn noenlunde med <a href='http://www.geonames.org/export/web-services.html#postalCodeLookupJSON'>postnummer</a>, de har <a href='http://www.geonames.org/export/ws-overview.html'>webservice</a> og egen <a href='http://www.geonames.org/postal-codes/postal-codes-norway.html'>norge-side</a>. Mulig vi må betale for tjenesten.

<a href='http://code.google.com/apis/maps/'>Google</a>: read <a href='http://my.safaribooksonline.com/0596101619/googlemapshks-CHP-2?cid=2008_developerlife_SOA_link'>this chapter</a> in the Google Maps Hack book. <a href='http://weblogs.java.net/blog/caroljmcdonald/archive/2007/10/adding_a_google.html'>Adding a Google Map to the Sample JSF Catalog Application</a> + <a href='https://blueprints.dev.java.net/complib/v2/map-viewer.html'>How to Use the Map Viewer and GeoCoder Components</a>. Best match: <a href='http://unserializableone.blogspot.com/2007/08/lightweight-google-geocoder-with-java.html'>Lightweight Google Geocoder with Java</a>?

Freebase har tripleter (subjekt+verb+objekt) som mapper postnumre til geolokasjoner, ikke mange norske. <a href='http://www.freebase.com/view/guid/9202a8c04000641f8000000003ea003a'>eksempel</a>.

Google laget en liste med <a href='http://groups.google.com/group/Google-Maps-API/web/resources-non-google-geocoders'>Geocoders</a>.

<a href='http://irb.no/-/bulletin/show/65093_postnummer-geodata'/></div>
