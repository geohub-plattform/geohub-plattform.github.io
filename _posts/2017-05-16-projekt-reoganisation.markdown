---
layout: post
title:  "Projektreoganisation"
categories: milestone1
author: Adrian
---

Mit dem Datensummit und den Gesprächen mit dem Team von MapBox musste ich feststellen,
dass einige meiner Annahmen über MapBox GL nicht ganz zutreffen und deshalb eine
Neuausrichtung der Projekts notwendig ist. Die Daten, die ich bisher über die
mit Hilfe von MaxBox GL abgerufen habe können durch die Konvertierung in Vektor-Kacheln
verändert und teilweise auch optimiert werden, so dass die Punkte nicht mehr
dieselben sind oder nicht mehr verfügbar sind.

Aus diesem Grund muss der GeoHub Editor jetzt neu ausgerichtet werden. Der Editor wird
nicht mehr von MaxBox GL abhängig sein. Ich will weiterhin die Vektor-Kacheln verwenden,
weil sie einfach eine besser Darstellung im Browser bieten. Danach werde ich jedoch
den Editor weitestgehend mit Hilfe von Events auf die Benutzereingaben reagieren lassen
und der Editor wird auch seine eigenen Daten verwalten und sie nicht mehr aus dem
verwendeten Rendering holen.

Diese Unabhängigkeit gibt mir jetzt die Möglichkeit mit der Entwicklung schneller voranzukommen,
weil die Abstimmung mit anderen Frameworks wegfällt.
Die Nutzung von MapBox GL als Datenquelle war sehr verlockend, weil so viel fertig zu sein schien,
das Feedback der MapBox Entwickler hat mir jedoch klar gezeigt, dass MapBox GL auf die Darstellung
der Karte optimiert ist und dadurch manche Daten weggelassen werden.
Dies entspricht nicht dem Ansatz vom GeoHub Editor, der exaktes Bearbeiten von
Geodaten ermöglichen soll.

