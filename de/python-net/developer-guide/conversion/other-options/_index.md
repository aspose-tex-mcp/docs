---
translation: true
template: /templates/_template-python-net.md
title: Andere TeX-Verwaltungsoptionen | Python
linktitle: Andere Optionen
weight: 17
url: /python-net/other-options/
description: Aspose.TeX für Python umfasst eine Konvertierungsfunktion, mit der Sie den anfänglichen Interaktionsmodus festlegen können, in dem die Engine startet.
lastmod: "2026-04-20"
---

{{<section overview>}}

Die Beispiele erzeugen XPS-Dateien. Wenden Sie zuerst eine [Lizenz](/tex/{{lang.url-fragment}}python-net/licensing/) an und setzen Sie `ASPOSE_TEX_OUTPUT_DIR` auf den Ausgabeordner (Standard: `output`). Verwenden Sie für jedes Beispiel einen eigenen Ausgabeordner, um alle Ergebnisse aufzubewahren.

## Festlegen des Interaktionsmodus

Wie [im Abschnitt zur TeX-Interaktion](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) erwähnt, bietet **Aspose.TeX für Python** die Möglichkeit, den anfänglichen Interaktionsmodus festzulegen, in dem die Engine startet. Hier ist ein Beispiel, wie es gemacht werden kann:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Festlegen des Jobnamens

Wenn die Haupteingabedatei als Dateiname angegeben wird, haben die resultierenden Ausgabedateien denselben Namen, jedoch mit unterschiedlichen Erweiterungen. Die TeX-Engine bezeichnet den Namen der Eingabedatei als *Jobnamen* und verwendet ihn für die Ausgabedateien. Eine Ausnahme bilden Hilfsdateien mit explizit angegebenen Dateinamen. Wenn die Haupteingabedatei jedoch als [stream](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream) übergeben wird, verwendet die TeX-Engine den Standard-Jobnamen, der *texput* ist. In beiden Szenarien ist das Überschreiben des Jobnamens durch Zuweisen der entsprechenden Konvertierungsoption möglich.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## „Die Zeit anhalten“

Um aus bestimmten Definitionen in der Präambel automatisch einen Titel zu generieren, bietet LaTeX eine Funktion, die typischerweise das aktuelle Datum einbezieht. Es kann jedoch vorkommen, dass wir das Datum auf einen bestimmten Wert festlegen möchten. Hier ist eine Methode, um das zu erreichen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Fehlende Pakete werden ignoriert

Wenn wir über eine LaTeX-Datei verfügen, die Verweise auf Pakete enthält, die von der Bibliothek **Aspose.TeX für Python** nicht unterstützt werden, wird die TeX-Engine beim Versuch, diese Pakete zu laden, auf einen Fehler stoßen und anhalten. Um dies zu verhindern, können wir folgende Möglichkeit nutzen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## So vermeiden Sie die Bildung von Ligaturen

Standardmäßig erstellt die TeX-Engine Ligaturen für bestimmte Zeichenpaare, wenn die Schriftart die erforderlichen Daten enthält. Wir können die Engine jedoch mit dem folgenden Code anweisen, die Ligaturkonstruktion zu umgehen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## Den Auftrag wiederholen

Wie [im Absatz „LaTeX-Eingabedatei“](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file), Beschriftungen und Referenzen erwähnt, gibt es Situationen, in denen wir denselben Job möglicherweise zweimal ausführen müssen. Hier ist eine Methode, um das zu erreichen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Mathematische Formeln in Rasterbilder umwandeln

Wenn die Notwendigkeit besteht, mathematische Formeln in Rasterbilder umzuwandeln, anstatt sie mit Schriftarten darzustellen, kann zu diesem Zweck die folgende Option verwendet werden:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Grafiken in Rasterbilder umwandeln

Die ObjectTeX-Engine bietet die Möglichkeit, Grafikdateien in Rasterformaten wie PNG und JPG sowie den Formaten PS (EPS) und XPS (OXPS) einzubinden. Die beiden letztgenannten Formate enthalten typischerweise Vektorelemente und Text. Wenn wir sie rastern und als Vollbilder einbinden möchten, können wir die folgende Option nutzen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

Das Grafikbeispiel liest `Typesetting/triangle.eps` unter `ASPOSE_TEX_INPUT_DIR` (Standard: `input`). Behalten Sie dieses Unterverzeichnis bei der Vorbereitung der Ressourcen bei.

## Unterteilung von Schriftarten

Wenn wir die Größe der Ausgabedatei verringern möchten, können wir die Unterteilung von Schriftarten verwenden. Dies bedeutet, dass die Schriftarten im resultierenden Dokument keine Daten für die Glyphen enthalten, die im Dokument nicht vorhanden sind. Hier ist eine Lösung, um dies zu erreichen:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}