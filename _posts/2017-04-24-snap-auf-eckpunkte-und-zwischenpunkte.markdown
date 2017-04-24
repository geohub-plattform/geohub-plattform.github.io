---
layout: post
title:  "Snap auf Eckpunkte und Zwischenpunkte"
categories: milestone1
author: Adrian
---

Nachdem das Setzen von Punkten entlang einer Linie bereits in dem letzten Update schon
ganz gut funktioniert hat, habe ich mit diesem Update eine stärkere Snap-Wirkung
an den Eckpunkten hinzugefügt. Dies ist wichtig, weil eigentlich sind das die Punkte,
die tatsächlich bereits Bestandteil der Karte sind und somit dem User besonders angezeigt
werden sollten.

Im folgendem Video kann man den Effekt ganz gut sehen. Der Benutzer setzt
hier Punkte, die perfekt mit dem Wegenetz entsprechen, obwohl er nie perfekt auf
die Eckpunkte klickt. Dies wird vom Editor automatisch erledigt.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Q5EcxM5dYFw" frameborder="0" allowfullscreen></iframe>

In der weiteren Umsetzung werden jetzt auch die notwendigen Zwischenpunkte
ermittelt. Wenn der Benutzer einen neuen Punkt setzt, so sollen dann auch
die Zwischenpunkte automatisch hinzugefügt werden, damit die gezeichnete
Linie auch 100%ig der darunterliegenden Karte entspricht.

Die roten Punkte in dem folgenden Video symbolisieren alle Punkte, die sich zwischen
der aktuellen Mausposition und dem letzten gesetzen Punkt befinden. Erstellt der
Benutzer einen neuen Punkt entlang dieser Linie, dann wird der Editor auch alle
roten Punkte zur aktuellen Zeichnung hinzufügen.

<iframe width="560" height="315" src="https://www.youtube.com/embed/LCnwUKqFjj0" frameborder="0" allowfullscreen></iframe>

### Weiteres Vorgehen

An dieser Stelle sind weitere Analysen notwendig. Je nachdem, wie weit der User
von dem letzten Punkt entfernt klickt, können mehrere Pfade zwischen dem Punkt und der
aktuellen Mausposition liegen. Hier müssen dann verschiedene Routen berechnet werden
und der kürzeste Pfad angezeigt werden. Da dies bereits stark in Richtung Navigation führt,
wird man diese Funktion entsprechend eingrenzen müssen, da sonst die Berechnungen
zu lange dauern würden.

Darüber hinaus ist eine stärkere Integration in den Draw-Editor an sich notwendig.
Im Moment ist die Snap-Funktion einfach eine Art Plugin, die intern die Mausposition
für den Editor verändert. Da die Snap-Funktion aber jetzt auch Zwischenpunkte
hinzufügt, muss dies beim Rückgängigmachen auch berücksichtigt werden. D.h. der
Editor muss wissen, welche Punkte vom Benutzer und welche Punkte automatisch
hinzugefügt wurden.