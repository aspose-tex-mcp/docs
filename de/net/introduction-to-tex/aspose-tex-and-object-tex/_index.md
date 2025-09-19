---
translation: true
template: /templates/_template-net.md
linktitle: Objekt-TeX
title: Aspose.TeX und Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX ist ein Eingabe- und Ausgabeformat dieser API-Lösung. Daher erklären wir hier das Objekt TeX und wie es in ein Zielformat umgewandelt wird.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Objekt-TeX

Betrachten wir nun das Ausgabeformat.

Das ursprüngliche TeX konnte Dateien nur im *DVI*-Format (DeVice Independent) ausgeben. Es kam vor, dass das DVI-Format keine Metriken eines Mediums definiert, auf dem eine Datei gedruckt werden soll – die Seitengröße und die Position der oberen linken Ecke des gesamten Seiteninhalts. Sobald wir uns entscheiden, die TeX-Engine in die Lage zu versetzen, Dateien beispielsweise im PDF-Format auszugeben, müssen wir solche Metriken definieren. Daher müssen wir neue Grundelemente in den Satz der ursprünglichen TeX-Engine aufnehmen. Und dies wäre eine Erweiterung des Motors selbst.

Das ist *Object* TeX. Auch hier gilt: **Einerseits handelt es sich um eine Programmiersprache mit dem Satz von VirTeX-Grundelementen, die durch neue Grundelemente erweitert werden, die durch neue Ausgabeanforderungen auferlegt werden. Andererseits handelt es sich um eine erweiterte TeX-Engine, die auch neue Grundelemente versteht. Und drittens ist Object TeX ein insgesamt neues Satzsystem.**

Da ist die vierte Hand. Das Object TeX-Format ist ebenfalls ein auf Plain TeX basierendes Format, das Definitionen enthält, die neue Grundelemente beinhalten, z. B. die Zuweisung von Standardwerten zu Medienmetriken.

## Aspose.TeX

Und Aspose.TeX ist nur eine API zum Object TeX-System.

## Warum ist das neue TeX Object?

Warum haben wir also „Object“ im Namen des Systems verwendet? Der Grund dafür ist, dass die eigentliche Ausgabe der Object TeX-Engine keine Datei im Ausgabeformat ist, sondern ein Zwischenmodell *Objekt*, das dann in ein Zielformat umgewandelt wird.