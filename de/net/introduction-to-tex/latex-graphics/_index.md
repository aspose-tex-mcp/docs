---
translation: true
template: /templates/_template-net.md
title: LaTeX-Grafiken | \includegraphics-Befehl
linktitle: LaTeX-Grafiken
weight: 18
url: /net/latex-graphics/
description: Erwähnenswert ist die Einbindung von Grafiken in TeX. Wenn man darüber spricht, fällt mir als Erstes der Befehl `\includegraphics` ein.
lastmod: "2026-04-22"
---

{{<section overview>}}

Tatsächlich gibt es zwei Aspekte der LaTeX-Grafik, die erwähnenswert sind:

 * Vektorgrafiken direkt mit LaTeX/TeX-Befehlen beschrieben und,
 * Einbindung externer Grafiken in externen Formaten wie EPS, PDF oder Raster-PNG und PDF.

Ersteres wird im ursprünglichen LaTeX und seinen Paketen nur begrenzt unterstützt. Es wird mit Hilfe der vertikalen und horizontalen TeX-Regeln implementiert. Das liegt daran, dass das ursprüngliche LaTeX auf der ursprünglichen TeX-Engine basiert, die die Hauptausgabe im *DVI*-Format erzeugt, das weder für die Beschreibung von Linien und Kurven noch für binäre Rasterbilddaten geeignet ist. Aber Engines, die in grafikunterstützenden Formaten (wie pdfTeX zu PDF) ausgeben können, können mithilfe formatabhängiger Pakete oder Paketfunktionen auch mit Grafiken umgehen. Aus dem gleichen Grund werden die letztgenannten Grafiken im Basis-LaTeX nicht unterstützt. Im Folgenden besprechen wir die Funktionen zur Grafikeinbindung.

## Das LaTeX-Paket „graphics“ und der Befehl `\includegraphics`.

Wenn man über die Einbindung von LaTeX-Grafiken spricht, fällt einem als Erstes der Befehl `\includegraphics` ein. Es ist im Paket „graphics“ definiert, das Sie in der Präambel erwähnen sollten, um seine Funktionen zu aktivieren.

```tex
\usepackage{graphics}
```

Wenn Ihr Satzsystem beispielsweise nicht standardmäßig für die Verwendung von pdfTeX konfiguriert ist, sollten Sie die entsprechende Option angeben, die das Paket dazu zwingt, die erforderliche „Treiber“-Datei zu verwenden:


```tex
\usepackage[pdftex]{graphics}
```

Eine „Treiber“-Datei ist Teil eines Pakets, das die Schnittstelle zwischen Paketbefehlen und formatabhängigen Low-Level-TeX-Erweiterungsprimitiven implementiert. Die LaTeX-Grafikunterstützung von Aspose.TeX ist für die Verwendung eines eigenen Treibers konfiguriert, sodass Sie die Treiberoption nicht angeben müssen.

Der einfachste Weg, beispielsweise ein PNG-Bild einzubinden, besteht darin, Folgendes einzugeben:


```tex
\includegraphics{sample-image.png}
```

Dabei ist „sample-image.png“ der Name der Datei, die Sie einschließen möchten. Sie können die Erweiterung sogar weglassen. Das Paket „graphics“ enthält die Liste der Definitionen unterstützter Formate. Bei der Suche nach einer Datei durchläuft es diese Liste und schließt die erste gefundene passende Datei ein.

Sie können den vollständigen Dateinamen auch mit einem absoluten oder relativen Pfad angeben:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Eine andere Möglichkeit, den/die Speicherort(e) der Grafikdateien anzugeben, besteht darin, eine Liste alternativer Pfade mit dem Befehl `\graphicspath` zu definieren, bevor `\includegraphics` aufgerufen wird:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Skalieren der Grafiken

Das LaTeX-Grafikpaket bietet Befehle zum Bearbeiten des Inhalts. Sie können also die enthaltenen Grafiken (eigentlich alles, was durch TeX/LaTeX-Code beschrieben wird) wie folgt skalieren:


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Größenänderung der Grafiken

Es ähnelt der Skalierung, aber Sie geben die erforderliche Größe anstelle eines oder mehrerer Skalierungsfaktoren an:


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Drehen der Grafiken

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## Das LaTeX-Paket „graphicx“.

Das LaTeX-Paket „graphicx“ stellt die Schnittstelle „key=value“ für Inhaltstransformationen bereit. Um seine Funktionen zu aktivieren, sollten Sie es in der Präambel erwähnen:


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Sie können jede der folgenden Optionen kombinieren, beachten Sie jedoch, dass die Reihenfolge wichtig ist.

### Grafikansichtsfenster
```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Grafiken skalieren

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Größenänderung von Grafiken

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Rotierende Grafiken

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Weitere Informationen zu den Funktionen des `Grafik`-Paketpakets finden Sie in der Dokumentation [hier](https://ctan.org/pkg/graphics) und
[hier](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Sie können sich auch die kostenlose Konvertierungs-[Web-App](https://products.aspose.app/tex/conversion/latex/) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**