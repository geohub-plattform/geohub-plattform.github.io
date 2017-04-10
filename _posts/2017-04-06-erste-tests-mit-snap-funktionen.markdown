---
layout: post
title:  "Erste Tests mit Snap-Funktionen"
categories: milestone1
author: Adrian
---

Die Basisfunktion des Online-Editors ist die Snap-Funktion. Darunter
versteht man, dass der User beim Zeichnen von Objekten, diese anhand
bereits vorhandener Objekte ausrichten kann. Dies ist extrem wichtig
um Flächen und Routen zu erhalten, die genau an bereits vorhandenen
Orientierungspunkten, wie Straßen ausgerichtet sind.

In den bisherigen Editoren wie dem [geojson.io Editor](http://geojson.io) kann man Flächen
und Routen freihand zeichnen und erhält dann Daten, die mehr oder weniger
genau an den vorhandenen Straßen ausgerichtet sind.
Hier ein Beispiel:

![Beispiel Handgezeichnet](/images/handmade-track.png)

Für den Fall der Routenaufzeichnung kann man natürlich auch das GPS-Signal
nutzen und dann die gewünschte Route einfach ablaufen und sie aufzeichnen.
Je nach Signalqualität ist die aufgezeichnete Route dann ebenfalls mehr oder weniger
genau ausgerichtet.

![Beispiel GPS Aufreichnung](/images/gps-track.png)

Die perfekte Lösung ist natürlich, wenn der Editor den User dabei unterstützt die
Route an den vorhandenen Geo-Punkten auszurichten und ihm hilft Punkte zu setzen, die
genau mit den bereits vorhandenen Punkten übereinstimmen. So ergibt sich eine Route,
die genau mit den bereits vorhandenen Wegen übereinstimmt.

Ich habe ein Beispielvideo aufgezeichnet, welches die Snap-Funktion des GeoHub-Editors
verdeutlicht. In diesem Beispiel sieht man einen roten Punkt, der immer den nächsten
verfügbaren Punkt in den Geodaten in Bezug zum aktuellen Mauszeiger anzeigt. Der Punkt
wird nur angezeigt, wenn es bereits Geodaten in einem bestimmten Radius zur aktuellen
Mauszeigerposition gibt.
Ist der Punkt sichtbar, so wird bei einem Mausklick dieser Punkt zur aktuellen
Zeichnung hinzugefügt. So kann der User sowohl Flächen als auch Linien genau
an den bereits vorhanden Straßen ausrichten. Man kann in dem Video sehr schön sehen, wie
der Punkt jeweils die nächstgelegene Linie auswählt.

<iframe width="560" height="315" src="https://www.youtube.com/embed/J1B9b6iXuxc" frameborder="0" allowfullscreen></iframe>

Natürlich kann man dieselbe Snap-Funktion für Geodaten nutzen, die normalerweise nicht Teil
der sichtbaren Geodaten, wie Straßen sind. Dies können irgendwelche Grenzen sein oder sogar
eigene Geodaten, die man vorher erstellt hat.

Ich habe auch hierzu ein Beispiel erstellt indem ich beispielhaft ein Polygon in den GeoHub-Editor
geladen habe und dann weitere Flächen an diesem Polygon ausgerichtet habe. In diesem Beispiel
wurde der Editor so eingestellt, dass er nur das hinzugefügte Polygon als Referenz verwendet und
nicht die darunter liegenden Straßen. Der rote Punkt bewegt sich nur entlang der grauen Linie des
Polygons.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jDImurMok5U" frameborder="0" allowfullscreen></iframe>

### Weiteres Vorgehen

Die gezeigten Videos zeigen bereits schon ganz gut wohin die Reise gehen soll.
Es sind jedoch noch einige Herausforderungen zu meistern. Als nächste Funktion will ich den Editor so umbauen,
dass er die Eckpunkte der bereits vorhandenen Geodaten besser visualisiert und auch an diesen
Punkten eine stärkere Snap-Wirkung für den User bemerkbar ist. Dies ist wichtig, da im Moment
der Editor neue Punkte interpoliert, die zwischen zwei Punkten liegen. Dieses Verhalten ist gewünscht, weil
der User durchaus die Möglichkeit haben soll Linien und Flächen an Punkten anzuschließen, die
zwischen zwei Punkten liegen. Im Moment ist es für den User jedoch nicht erkennbar, ob er den
neuen Punkt genau auf einem bereits vorhandenen Punkt setzt oder
zwar auf der Linie, aber knapp daneben.
