---
translation: true
template: /templates/_template-java.md
linktitle: Schriftartenauswahlschema
title: Auswahlschema für LaTeX-Schriftarten
weight: 60
url: /java/latex-font-selection/
keywords: Latex, Latex-Schriftarten, Auswahl von Latex-Schriftarten, NFSS
description: Lernen Sie die Verwendung von LaTeX-Schriftarten bei der Verarbeitung von Dokumenten. Außerdem werden TeX-Schriftartmetriken und Zeichenformen erwähnt.
lastmod: "2024-09-26"
---

{{<section overview>}}


Während der Verarbeitung des Quelldokuments hat das LaTeX-Satzsystem keine großen Kenntnisse über die verwendete Schriftart. Es berechnet lediglich die Positionen der Zeichen, ohne dass Formen bekannt sein müssen. Die wichtigsten Informationen, die es benötigt, sind die *Blackboxes* der Zeichen, die durch ihre Breite, Höhe und Tiefe definiert werden. Diese Abmessungen werden für jede Schriftart in einer separaten externen Datei gespeichert, die als TeX-Font-Metrikdatei (`.tfm`) bezeichnet wird.

Die Charakter-Chaps kommen später ins Spiel. Wenn ein LaTeX-System eine `.dvi`-Datei erstellt, kombiniert ein *Treiber*-Programm Zeichenplatzierungsdaten aus der `.dvi`-Datei mit Informationen über Zeichenformen aus der `.pk`-Datei oder aus Gliederungsbeschreibungen (wie PostScript). Erzeugen Sie das Zeichenbild auf dem Ausgabemedium. Andere LaTeX-Systeme wie **PDF TeX** oder **VTEX** umgehen jedoch die Erstellung einer `.dvi`-Datei und generieren stattdessen direkt eine **PDF**- oder **PostScript**-Ausgabe. In diesem Fall werden die Zeichenformen eingebettet, wenn der entsprechende Formatierer die endgültige Ausgabe erzeugt.