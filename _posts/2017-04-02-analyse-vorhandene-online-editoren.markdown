---
layout: post
title:  "Analyse der vorhandenen Online Geo-Editoren"
categories: milestone1
author: Adrian
---

Als Vorbereitung auf die Entwicklung des Geo-Editors habe ich mir
einige Online Editoren und Erweiterungen angeschaut, die das Bearbeiten
von Geodaten im Browser erlauben und auch die wichtige Snap-Funktion anbieten.

Einer der Online Editoren ist der [geojson.io][geojson-io]. Ich habe diesen Editor bereits
öfters in der Vergangenheit verwendet. Er bietet gute Möglichkeiten um
Geodaten wie Linien und Polygone zu erstellen und diese auch mit
Zusatzattributen zu versehen. Der Editor kann die Geodaten aus verschiedenen
Quellen und in verschiedenen Formaten einlesen und dann auch in diese Formate exportieren.
Eigentlich die hervorragende Basis für die Entwicklung des GeoHub-Editors.
Was geojson.io fehlt ist die Snap-Funktion, die das Ausrichten von neuen Elementen an
bereits vorhandenen Geodaten erlaubt.

![Screenshot geojson.io](/images/geojson-io-editor.png)

Da der geojson.io Editor auf [Leaflet][leaflet] und
dem [Leaflet.Draw Plugin][leaflet-draw] basiert,
habe ich mir auch einige Plugins angeschaut, die
eine Snap-Funktion unterstützen würden. Dabei gibt es tatsächlich einige Plugins/Editoren, die
diese Funktion unterstützen und zwar das reine
[Leaflet Snap Plugin][leaflet-snap] oder das darauf
basierende [Leaflet Pin Plugin][leaflet-pin], welches das Zeichnen von verschiedenen
Geoobjekten erlaubt.
Beide Plugins sind jedoch seit einiger Zeit nicht mehr weiterentwickelt worden und basieren auf einer
0.7er Version von Leaflet. Mit dem Update auf Leaflet 1.0 wurden jedoch einige APIs verändert, so
dass diese Plugins nicht mehr mit der neusten Version kompatibel sind.
Ein weiteres Plugin, welches im Moment recht aktuell gehalten wird ist das [Leaflet PM][leaflet-pm].
Auf der Webseite wird sehr eindrucksvoll gezeigt, welche Möglichkeiten damit realisiert werden.

All diese Plugins und Editoren basieren auf Leaflet und somit auch auf der kachelbasierenden
Darstellung der Karte. Dies heißt, dass die Karte bereits vorgerendert ist und somit alle
Informationen über die Straßen und andere Geoinformationen fehlen. Ein neuer Ansatz, der
bereits in Google Maps zu sehen ist und auch von Mapbox genutzt wird, ist das Rendern der
Daten direkt im Webbrowser des Nutzers. Dank [WebGL][webgl] kann dies mittlerweile sehr
performant realisiert werden und erlaubt das stufenlose Zoomen der Karte.
Im Rahmen vom Prototype Fund wird auch das Projekt [Grandine][grandine]
von Thomas Skowron gefördert, welches zum Ziel die Erstellung von Vektor Kacheln hat.
Der Vorteil dieser Kacheln ist, dass die Informationen über Straßen
als Vektordaten und vorliegen und somit alle Punkte einer Straße auf dem Rechner
verarbeitet werden können. Genau diese Punkte benötigt auch der GeoHub-Editor
um neue Geodaten entlang bereits vorhandener Punkte und Linien zu erstellen.

Das open-source [Projekt Mapbox-Gl][mapbox-gl] nutzt bereits die Vektorkacheln und rendert
diese im Browser zu einer Karte. Dazu wurde auch ein [Tool zum Zeichnen von Linien und Polygonen][mapbox-gl-draw]
für Mapbox-Gl entwickelt. Seit Anfang des Jahres gibt es sogar einen [Pull Request, der die Snap-Funktionen][pr-snap]
in dem Draw Tool integriert. Diese Konstellation sieht für mich als die
beste Grundlage aus um den GeoHub Editor zu implementieren. Sowohl die ersten Ansätze
einer Snap-Funktion als auch die Verfügbarkeit der Geodaten in den Vektorkacheln sind
entscheidende Vorteile. Es ist auch davon auszugehen, dass die Weiterentwicklung der
Kartenwerkzeuge auf Basis von Vektorkacheln erfolgen wird.

### Weiteres Vorgehen

Der Vektorkacheln basierte Ansatz verspricht den besten Erfolg, so dass
ich in den nächsten Tagen den Pull Request mit der Snap-Funktion bei mir einrichten werde
und die vorhandenen Funktionen soweit ausbauen will, dass man neue Geodaten
entlang von bereits vorhandenen Daten zeichnen kann.
Darüber hinaus will ich mit den Entwicklern, die an dem Pull Request beteiligt sind,
klären wie meine Anforderungen in das Projekt einließen könnten.

[pr-snap]: https://github.com/mapbox/mapbox-gl-draw/pull/583
[mapbox-gl-draw]: https://github.com/mapbox/mapbox-gl-draw
[mapbox-gl]: https://github.com/mapbox/mapbox-gl-js
[grandine]: https://thomas.skowron.biz/blog/grandine-summary-march-2017/
[webgl]: https://de.wikipedia.org/wiki/WebGL
[leaflet-pm]: https://github.com/codeofsumit/leaflet.pm
[leaflet]: http://leafletjs.com/
[geojson-io]: http://geojson.io/
[leaflet-draw]: https://github.com/Leaflet/Leaflet.draw
[leaflet-pin]: https://github.com/kklimczak/Leaflet.Pin
[leaflet-snap]: https://github.com/makinacorpus/Leaflet.Snap
