---
layout: post
title:  "Milestone 2 erreicht"
categories: milestone2
author: Adrian
---

In den vergangenen Wochen habe ich den Editor in großen Teilen überarbeitet und viele Probleme in der Behandlung
der Geodaten behoben. Mit dem [heutigen Milestone 2](/milestone2) ist das Tool soweit, dass das Snapping
entlang von Geodaten hervorragend funktioniert und auch vom Benutzer gezeichnete Daten können als Grundlage für das
Snapping verwendet werden. Da im Moment nur Linien gezeichnet werden können, werde ich als Nächstes
auch Polygone zu dem Editor hinzufügen. Danach werden weitere Funktionen, wie Auswählen, Schneiden und Löschen von
Objekten dazu kommen.

Im Folgenden möchte ich eine paar Probleme dokumentieren, die mir auf dem Weg zum Milestone 2 begegnet sind.
Mit dem [Milestone 1](/milestone1) war es möglich Linien entlang von bereits vorhandenen Linien zu zeichnen. Dabei
wurden immer die bereits vorhanden Punkte als Eckpunkte verwendet. Als ich die Funktion hinzugefügt habe, mit der
der Benutzer auch ohne Snapping neue Punkte hinzufügen konnte gab es ein sehr seltsames Verhalten beim Bewegen
der Maus und man konnte erkennen, dass das Routing entlang der bereits vorhandenen Geodaten nicht funktioniert.

![Screenshot](/images/geohub-bug1.png)

Beispiel 1: Der Benutzer hat mit Punkt A angefangen zu zeichnen und bewegt die Maus auf die Diagonale
zwischen den Punkten D und B. Die kürzeste Strecke wäre in dem Fall A, B und E. Der Algorithmus wählt jedoch
einen "Umweg" und zeichnet die Route über die Punkte A, B, C, D und E.

![Screenshot](/images/geohub-bug2.png)

Beispiel 2: Der Benutzer hat erneut am Punkt A angefangen und bewegt die Maus entlang der Linie zwischen
den Punkten E und F. Der Algorithmus wählt hier die Route über die Ecke C, obwohl die
Verbindung B, D kürzer wäre.

In beiden Fällen ist der Punkt B das Problem. Obwohl dieser Punkt zuvor über den Editor hinzugefügt wurde und
der Snapping Algorithmus diesen Punkt als "auf der Linie" berechnet hat, ist dieser Punkt
nicht wirklich auf der Linie und wird somit nicht in der Route berücksichtigt.

Die Ursache dafür sind verschiedene Rundungsfehler, die bei geometrischen Berechnungen entstehen. Durch diese
Rundungsfehler können mehrere Fälle entstehen, bei denen der Punkt nicht auf der Linie liegt und
somit nicht in die Routenberechnung einbezogen wird.

Um dieses Problem zu beheben analysiert der GeoHub Editor jede Linie, die vom Benutzer gezeichnet wird
auf Schnittpunkte mit bereits vorhandenen Linien. Dabei werden zwei Sonderfälle untersucht und entsprechend behandelt.

*Sonderfall 1*: Zwei Linien schneiden sich, aber das eine Endstück ist so kurz, dass es kaum ins Gewicht fällt.
In diesem Fall wird der Endpunkt der einen Linie als Schnittpunkt der zweiten Linie genommen.

*Sonderfall 2*: Zwei Linien schneiden sich nicht, aber ein Endpunkt einer Linie liegt so nah an einer anderen Linie,
dass er als Schnittpunkt gelten könnte. In diesem Fall wird ebenfalls der Endpunkt der einen Linie
als Schnittpunkt der zweiten Linie genommen.

Mit der Umsetzung der beiden Sonderfälle funktioniert nun das Erstellen von neuen Linien
entlang von benutzergenerierten Linien. Am besten lässt es sich am aktuellen [Milestone 2](/milestone2)
testen. Auf dieser Seite werden bereits die Geodaten für die darunter liegende Karte geladen.
Man kann die Karte jedoch überall bewegen und mit dem "Wolke"-Button rechts oben auch
weitere Daten für einen anderen Ausschnitt downloaden.

![Screenshot](/images/geohub-milestone1.png)

### Weiteres Vorgehen ###

Wie bereits angedeutet soll als Nächstes die Möglichkeit zum Zeichnen von Polygonen geschaffen werden und dann auch
verschiedene Funktionen um Objekte auswählen und löschen zu können.








