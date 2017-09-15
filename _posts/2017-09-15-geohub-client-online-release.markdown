---
layout: post
title: "GeoHub Editor Online Release"
categories: release
author: Adrian
---

In den vergangenen Monaten konnte ich sukzessive die Probleme beim
Schneiden von Linien weiter lösen und zwar bis zu einem Punkt, wo
alles sehr gut funktioniert. Danach habe ich den Fokus auf die Funktionen
rund um den Editor gesetzt und weniger auf das Blogging hier. Aus dem Grund
gibt es hier jetzt einen Blog, der alle Funktionen zusammenfasst und erklärt.

Der Online-Editor ist ab sofort unter der folgenden URL verfügbar:
<a href="https://geohub-client.firebaseapp.com">https://geohub-client.firebaseapp.com</a>

[![Screenshot](/images/geohub-screen.png)](https://geohub-client.firebaseapp.com)

Nach dem Öffnen des Editors sieht der Nutzer eine Karte und auf der rechten Seite
eine Reihe an Funktions-Icons, die im folgendem näher erklärt werden.
Der Editor kann grundsätzlich Punkte zeichnen, die zu Linien verknüpft werden können.
Um das Zeichnen zu beenden muss der letzte Punkt erneut angeklickt werden.
Wird nur ein Punkt gesetzt und dann erneut angeklickt, dann hat man nur einen einzelnen Punkt erstellt.
Wenn eine Linien geschlossen wird, d.h. der letzte Punkt entspricht dem ersten Punkt,
dann erstellt der Editor daraus automatisch eine Fläche (Polygon).

Werden in den Editor so genannte Stützdaten geladen, so kann man seine Punkte auf bereits
vorhandene Punkte platzieren oder sie entlang von bereits vorhandener Linien setzen.
Findet der Editor zwischen dem letzten Punkt und der aktueller Mausposition einen Weg
entlang der Stützdaten, so wird der Weg eingeblendet und kann mit einem Mausklick zu der
aktuellen Zeichnung hinzugefügt werden.

### Funktionen

<p><img src="/images/action_download_ways.png"/>
Lädt die Straßen-Geodaten für den aktuellen Bereich um sie als Stützdaten anzuzeigen. Mit Hilfe
der Stützdaten können andere Geo-Objekte ausgerichtet werden, z.B. entlang von Straßen oder
Gebäuden.</p>

<p><img src="/images/action_download_all.png"/>
Lädt die Straßen und Gebäude-Geodaten für den aktuellen Bereich um sie als Stützdaten anzuzeigen.</p>

<p><img src="/images/action_editor.png"/>
Öffnet den Editor um die Eigenschaften der ausgewählten Geodaten zu bearbeiten. Die Eigenschaften
sind einfache Schlüssel-Wert Paare, die jedem Objekt oder einer Gruppe von Objekten zugeordnet
werden können. Sind die Werte für manche Schlüssel unterschiedlich, so werden sie als Platzhalter
angezeigt.
</p>

<p><img src="/images/action_load.png"/>
Lädt Geodaten von der Festplatte runter. Die Geodaten können im GEOJSON oder KML Format sein.
Es ist auch möglich die GEOJSON oder KML Datei einfach in den Browser zu ziehen um sie zu laden.
Mit dem GitHub Icon können die Daten auch von einem < href="https://gist.github.com/">GIST</a> geladen werden.
Dabei muss die URL von dem GIST bekannt sein und kann in einem Dialogfeld eingegeben werden.
</p>

<p><img src="/images/action_save.png"/>
Speichert die aktuellen Geodaten als GEOJSON oder KML Datei auf der Festplatte. Alternativ können die
Daten auch als GIST gespeichert werden. Wenn nur bestimmte Objekte ausgewählt sind, so werden nur
sie gespeichert.</p>

<p><img src="/images/action_select.png"/>
Auswahlwerkzeug um bestimmte Objekte auszuwählen. Bei gedrückter SHIFT-Taste können mehrere Objekte
selektiert werden.
</p>

<p><img src="/images/action_draw.png"/>
Zeichenwerkzeug zum Zeichnen von neuen Geodaten. Bei aktiviertem Snapping werden die Daten
automatisch entlang bereits vorhandener Geodaten gezeichnet. Beim Drücken der SHIFT-Taste wird das
Snapping deaktiviert. Beim Drücken der ALT-Taste wird das Routing deaktiviert. Zum Löschen
der letzten Punkte kann die ENFT-Taste gedrückt werden.
Beim erneutem Klick auf den letzten Punkt wird das Zeichnen beendet und das Objekt abgeschlossen.
</p>

<p><img src="/images/action_cut.png"/>
Schneidewerkzeug trennt die aktuelle Linie in zwei Teile. Beim Trennen von Polygonen wird das Polygon
aufgelöst und eventuelle innere Polygone als einzelne Polygone ausgelöst.
</p>

<p><img src="/images/action_snapping.png"/>
Snapping Funktion aktivieren oder deaktivieren. Mit der Snapping Funktion wird versucht immer
den nächstgelegenen Punkt als Stützpunkt zu verwenden.
</p>

<p><img src="/images/action_routing.png"/>
Routing Funktion aktivieren oder deaktivieren. Mit der Routing Funktion wird die gezeichnete Linie entlang bereits vorhandener Linien gezogen.
Dadurch stimmendie Daten exakt mit den bereits vorhandenen Geodaten überein.
</p>

<p><img src="/images/action_combine.png"/>
Kombiniert die ausgewählten Objekte zu einem Objekt. Mehrere Linien werden dabei zu einer Linie
zusammengeführt. Die erste Linie legt dabei die Richtung für die Gesamtlinie fest.
Bei mehreren Polygonen ist das erste Polygon das äußere und die anderen sind die inneren Polygone.
</p>

<p><img src="/images/action_group.png"/>
Objekte gruppieren. Es können nur Linien mit Linien (MultiLineString) und Polygone mit
Polygonen (MultiPolygon) gruppiert werden.
</p>

<p><img src="/images/action_ungroup.png"/>
Gruppierung rückgängig machen. Die gruppierten Objekte werden dabei in ihre Ursprungsformen
aufgeteilt.
</p>

<p><img src="/images/action_polygon.png"/>
Eine Linie zum Poylgon machen. Sind der Anfang- und Endpunkt nicht gleich, dann wird das
Polygon automatisch geschlossen.
</p>

<p><img src="/images/action_delete.png"/>
Gezeichnete Daten löschen. Löscht alle Benutzerdaten. Kann nicht rückgängig gemacht werden.
</p>

<p><img src="/images/action_delete_snap.png"/>
Löscht die Sützdaten im Hintergrund.
</p>

<p><img src="/images/action_zoom.png"/>
Bewegt die Karte so, dass alle Benutzerobjekte sichtbar sind.
</p>

<p><img src="/images/action_hide_selected.png"/>
Versteckt die gerade ausgewählten Objekt. Diese Funktion kann nützlich sein, wenn viele Objekte
übereinander liegen und man das gewünschte Objekte nicht direkt auswählen kann.
</p>

<p><img src="/images/action_add_snap.png"/>
Fügt die aktuell ausgewählten Daten zur den Stützdaten hinzu.
</p>

Ich freue mich über Feedback zu dem Editor per E-Mail. Da der Editor Open-Source ist, können gerne auch Änderungen
an dem Editor vorgenommen und als Pull-Requests eingereicht werden.

Auf Wunsch erstelle ich auch gerne einen Blog-Post, der beschreibt wie man das Build-System von dem Projekt
aufsetzt und neue Funktionen hinzufügt.
