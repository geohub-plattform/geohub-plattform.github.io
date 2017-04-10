---
layout: post
title:  "Projektbeschreibung und Milestones"
---

Für die erste Runde des Prototype Funds habe ich mich mit folgender Idee beworben.

# Welches Problem willst Du mit Deinem Projekt lösen? Was ist Deine Motivation?
Open Street Map hat in den letzten Jahren gezeigt wie wichtig den Menschen Geodaten sind. In Open Street Map können jedoch nicht alle Daten gespeichert werden, wie zum Beispiel Daten über gebührenpflichtige Parkzonen und Wasserversorgungsgebiete.

Beim Trinkwassertool habe ich zum Beispiel gemerkt, dass es sehr schwierig ist, die Daten geobasiert zu erfassen. Wir können den Gemeinden oder anderen Freiwilligen nicht einfach einen Link schicken, über den sie die Versorgungsgebiete einzeichnen können. Zudem orientieren sich die Versorgungsgebiete an Straßen, Stadtteilen und Stadtgrenzen, so dass man derzeit diese Grenzen neu abzeichnen müsste.

Journalisten, die für einen Artikel nur bestimmte Gebiete oder Straßenzüge hervorheben wollen, müssen diese im Moment mühsam in Grafikeditoren nachzeichnen. Diese nachgezeichneten Karten sind nicht sehr präzise und nur sehr schlecht für die Wiederverwendung in neuen Daten geeignet, weil sie als Grafik vorliegen.

# Wie wird Dein Projekt dieses Problem lösen?
Mit dem Geodaten Editor soll ein Web-Tool geschaffen werden, welches es dem Nutzer erlaubt anhand vorhandener Geodaten, neue Geodaten, wie Flächen, Linien oder Punkte zu erstellen und diese mit Meta-Daten zu versehen.

Wichtig ist, dass das Tool es dem Nutzer erlaubt Linien entlang bereits vorhandener Linien zu zeichnen. Hat man beispielsweise bereits die Stadtgrenzen einer Stadt in den Editor geladen, so ist es nicht mehr nötig die äußeren Stadtteilgrenzen nochmals zu zeichnen. Nur die inneren Stadtteilgrenzen müssen gezeichnet werden und die äußeren Stadtteilgrenzen können aus den vorhandenen Stadtgrenzen übernommen werden.
Dasselbe gilt auch für Straßenzüge. Möchte man zum Beispiel Flächen oder Routen entlang bereits vorhandener Straßen zeichnen, so können diese in den Editor geladen werden und als Teil der der Fläche oder Route übernommen werden.

Alle in dem Editor erzeugten Daten können auf der Editor-Plattform gespeichert werden und anderen Nutzern zur Verfügung gestellt werden (ähnlich wie das Gist System von Github). Die User können somit andere Geodaten leicht für ihre eigenen Geodaten nutzen. Hat jemand beispielsweise schon die Stadtgrenzen einer Stadt auf der Plattform gespeichert, so können diese Daten leicht übernommen werden um beispielsweise Wasserversorgungsgebiete einzuzeichnen.

Alle gezeichneten Daten sollen mit Meta-Daten versehen werden können um zu beschreiben, was sie bedeuten oder enthalten. Der Export und Import der Daten in/aus bekannten Formaten wie GeoJSON, TopoJSON, GPX oder SVG soll in dem Editor möglich sein.

Die gezeichneten Daten sollen natürlich leicht als Karte für Print oder Web exportiert werden können.

# Wer ist die Zielgruppe? Wie profitiert sie vom Projekt?
Das Projekt richtet sich an alle, die mit Geodaten arbeiten.

Für Journalisten kann dieses Tool sehr wichtig sein um schnell und einfach eigene Visualisierungen zu erstellen. Durch die Verknüpfung von Meta-Daten können im Web leicht interaktive Karten erstellt werden, die für den Besucher im Detail sehr informativ sind.

Mitarbeiter in der Verwaltung können das Tool nutzen um für die Bürger genaue Karten mit bestimmten Versorgungsgebieten zu kennzeichnen. So werden im Moment häufig einfach nur Straßenzüge genannt, wenn Trinkwasserdaten veröffentlicht werden. Hier kann man sich nur sehr schlecht orientieren. Auch Müllabfuhr-Bezirke werden nur anhand von Straßen benannt und sind für die User nicht auf Anhieb eindeutig zu erkennen.
Darüber hinaus soll das Tool eine schnelle Möglichkeit bieten um Bauprojekte zu visualisieren und die damit verbundenen Behinderungen.

Geodaten Enthusiasten sollen das Tool nutzen können um beispielsweise Wanderrouten zu zeichnen und anderen zur Verfügung zu stellen. Durch die einfache Übernahme der Daten sollen andere die Möglichkeit haben, basierend auf diesen Daten neue Routen zu erstellen. Auch Blogger, die häufig in ihren Blogs Geodaten verwenden sollen mit dem Tool neue Möglichkeiten erhalten um ihre Besucher zu informieren und ihnen die Geodaten in offenen Formaten zum Download anbieten.

Als Open Source Projekt sollen von den geschaffenen Funktionalitäten auch Entwickler profitieren und in die Lage versetzt werden den Editor zu erweitern oder eigene Projekte auf Basis des Editors zu starten.

# Skizziere kurz die wichtigsten Meilensteine Deines Projekts.

1. Untersuchung und Analyse, wie der GeoJSON.IO Editor als Grundlage für dieses Projekt verwendet werden kann
2. Anpassung von GeoJSON.IO oder Entwicklung eines neuen JavaScript Editors, der es erlaubt Geodaten zu bearbeiten
3. Entwicklung von Import-Modulen, die Geodaten aus OpenStreetMap (via Overpass API) und aus anderen GeoJSON Datenquellen importieren können
4. Entwicklung eines Backends welches die Geodaten ähnlich wie Gist von Github speichert und anderen zur Verfügung stellt
5. Verknüpfung des JavaScript Editors mit dem Backend
6. Entwicklung von Export-Modulen für die Formate GeoJSON, TopoJSON, GPX und SVG
7. Entwicklung eines Export-Moduls für gerenderte Karten
8. Erstellung von Video-Tutorials um anhand von Beispielen den Nutzen des Projekts zu visualisieren

