---
translation: true
template: /templates/_template-java.md
linktitle: Grafiken einschließen
title: LaTeX includegraphics
weight: 10
url: /java/latex-includegraphics/
keywords: includegraphics Latex, Latex includegraphic, Bilder einfügen Latex, Latex-Grafik
description: Erfahren Sie mehr über das LaTeX-Grafikmakro, Bildtransformationen, Ansichtsfenster, Beschneidung und den Unterschied zwischen Grafik- und Grafikpaketen.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Einführung

Während Sie an Ihren akademischen und wissenschaftlichen Dokumenten wie Forschungsarbeiten, Konferenzberichten und wissenschaftlichen Präsentationen arbeiten, möchten Sie möglicherweise gelegentlich grafische Abbildungen einbinden.

Das können zum einen Zeichnungen, Plots, Histogramme oder etwas anderes sein, was allgemein als Vektorgrafiken bezeichnet wird. Moderne LaTeX-Systeme (wie `pdfTeX`) bieten zahlreiche Werkzeuge zum Erstellen solcher Grafiken in einem Dokument. Zum Beispiel die Pakete `pict2e`, `PGF(TikZ)` und `PGFplots`. In den meisten Fällen werden die Figuren selbst von einer TeX-Engine generiert und als Sequenzen von Vektorgrafikanweisungen, die für ein bestimmtes Ausgabeformat geeignet sind, in die Ausgabedatei eingefügt.

Andererseits verfügen Sie möglicherweise über Rasterbilder, die Sie ebenfalls in Ihre Publikation einbinden möchten. LaTeX-Systeme sind derzeit auch dazu in der Lage, Sie müssen jedoch den Pfad zu Ihrer Bilddatei in Ihrer LaTeX-Datei als Parameter für ein LaTeX-Makro angeben.

In diesem Artikel geht es um das Einfügen von Rasterbildern in LaTeX-Dateien mithilfe des Makros `\includegraphics` aus dem Paket `graphics` (und dem dazugehörigen Paket `graphicx`).

## Welches Paket soll ich wählen, `graphics` oder `graphicx`?

Beide Pakete, `graphics` und `graphicx`, sind sich sehr ähnlich. Der Hauptunterschied liegt in der Syntax. Während das Paket `graphics` eine Reihe separater Makros verwendet, um Transformationen auf ein Bild anzuwenden, verwendet das Paket `graphicx` die Notation `key=value` für die Parameter des Makros `\includegraphics`, um diese Transformationen anzugeben. Wir geben Beispiele für jeden Anwendungsfall für beide Pakete gleichzeitig, um den Unterschied deutlicher zu machen.

## Inklusive des gewählten Pakets

Dies geschieht mit dem Befehl `\usepackage` auf die gleiche Weise wie bei jedem anderen LaTeX-Paket:


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Angeben eines Treibers

Wenn Ihr Satzsystem beispielsweise nicht standardmäßig für die Verwendung von „pdfTeX“ konfiguriert ist, sollten Sie die entsprechende Option angeben, die das Paket dazu zwingt, den erforderlichen „Treiber“ zu verwenden:


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

Ein „Treiber“ ist ein Teil eines Pakets, der die Schnittstelle zwischen Paketbefehlen und formatabhängigen Low-Level-TeX-Erweiterungsprimitiven implementiert. Die LaTeX-Grafikunterstützung von **Aspose.TeX** ist für die Verwendung eines eigenen Treibers konfiguriert, sodass Sie die Treiberoption nicht angeben müssen.

## LaTeX-Makro `\includegraphics`.

Fahren wir nun mit dem einfachsten Beispiel fort. Hierbei handelt es sich natürlich um das Einbinden eines Bildes ohne jegliche Transformation. Erwartungsgemäß ist der LaTeX-Code, der beide Pakete verwendet, derselbe:


```tex
\includegraphics{sample-image.png}
```

In diesem Beispiel wird davon ausgegangen, dass sich Ihre Bilddatei im selben Verzeichnis wie die LaTeX-Datei befindet. Es gibt jedoch mehrere Möglichkeiten, einen anderen Standort anzugeben. Der LaTeX-Code wird für beide Pakete wieder derselbe sein:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Eine andere Möglichkeit, den/die Speicherort(e) der Grafikdateien anzugeben, besteht darin, eine Liste alternativer Pfade mit dem Befehl `\graphicspath` zu definieren, bevor `\includegraphics` aufgerufen wird:


```tex
`\graphicspath`{{d:/img}{c:/img}{d:/work/img}}
```

## LaTeX-Grafiktransformationen

Die LaTeX-Pakete „graphics“ und „graphicx“ bieten eine Reihe von Möglichkeiten zur Bearbeitung des Inhalts.

### Maßstabsgetreue LaTeX-Figur

Sie können also die enthaltenen Grafiken (eigentlich alles, was durch TeX/LaTeX-Code beschrieben wird) wie folgt skalieren:


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Größe der Figur LaTeX ändern

Es ähnelt der Skalierung, aber Sie geben die erforderliche Größe anstelle eines oder mehrerer Skalierungsfaktoren an:


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Figur LaTeX drehen

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Festlegen eines Ansichtsfensters und Zuschneidens

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Was das Paket „graphicx“ betrifft, können Transformationen kombiniert werden, aber die Reihenfolge ist wichtig.
Weitere Informationen zu den Funktionen des `Grafik`-Paketpakets finden Sie auf der [Paketseite auf CTAN](https://ctan.org/pkg/graphics) und
die [Paketdokumentation](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### LaTeX Include Graphics kostenlose Web-App

Wenn Sie nicht programmgesteuert mit dem Latexpaket includegraphics arbeiten möchten, können Sie sich auch die kostenlose Web-App [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/) ansehen, die auf der Grundlage von [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) erstellt wurde. 

Mit der App können Sie mehrere Bilder auswählen und deren Transformationen visuell anpassen. Es generiert außerdem LaTeX-Quellcode mit dem Paket „graphicx“ und rendert ihn, wobei das Ergebnis auf der Seite angezeigt wird.

### LaTeX Figure Rendering-Funktion in der Aspose.TeX-Bibliothek

Die **Aspose.TeX**-Bibliothek bietet eine Möglichkeit, Raster- und SVG-Figuren zu erstellen, die Sie in Ihren Veröffentlichungen außerhalb des TeX/LaTeX-Kontexts verwenden können. Zum Beispiel auf einer Webseite. Dies wird als **LaTeX Figure Rendering** bezeichnet. Kurz gesagt, dieser Teil der API ermöglicht es Ihnen, ein Fragment des LaTeX-Quellcodes unabhängig vom Seitenlayout zu rendern. Weitere Einzelheiten finden Sie in diesem [Artikel](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

Der Artikel über [einschließlich externer LaTeX-Pakete](/tex/{{lang.url-fragment}}java/external-latex-packages/) kann Ihnen auch einen Hinweis geben, wie Sie Figuren aus LaTeX-Plots erstellen.