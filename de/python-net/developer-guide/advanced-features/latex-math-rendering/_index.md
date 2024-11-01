---
translation: true
template: /templates/_template-python-net.md
title: Rendern von LaTeX-Matheformeln | Python
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /python-net/latex-math-formula-rendering/
description: Der Artikel bietet einen Überblick über die Aspose.TeX-API-Lösung für Python und ihre Funktionalität zum Rendern von LaTeX-Matheformeln.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Rendern einer LaTeX-Matheformel in PNG

Werfen Sie bei Bedarf einen Blick auf den [API-Referenzabschnitt für dieses Thema](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Tatsächlich lässt sich die Renderfunktion für **LaTeX-Matheformeln** am besten demonstrieren, indem man mit einem Beispiel beginnt. Hier ist es:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Kommen wir zu den Details. Zuerst initiieren wir ein [rendering options](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/)-Objekt, ähnlich dem TeX/LaTeX-Schriftsatz, das die Spezifikation für die gewünschte Ausgabebildauflösung enthält.

Als nächstes spezifizieren wir die Präambel. Die Standardpräambel lautet:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

das im Vergleich zum Standard-LaTeX eine verbesserte Unterstützung für mathematische Formeln bietet. Sie können beispielsweise das Paket „color“ einschließen, um die Hervorhebung in der Formel anzupassen, wie im bereitgestellten Codebeispiel gezeigt.

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächsten beiden Optionen bestimmen die Vordergrund- und Hintergrundfarben. Alle Teile der Formel, die von der benutzerdefinierten Hervorhebung nicht betroffen sind, werden in der Farbe „TextColor“ angezeigt.

Die folgende Zeile im Beispiel dient zur Veranschaulichung, dass Sie die Möglichkeit haben, die Protokollausgabe auf einen bestimmten Stream umzuleiten.

Und schließlich können Sie mit der Option „ShowTerminal“ steuern, ob die Terminalausgabe in der Konsole angezeigt werden soll.

Der eigentliche Rendervorgang wird von der Methode [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) durchgeführt, die die Größe der Formel in Punkten zurückgibt.

Die Methode akzeptiert den Stream, in den das Bild geschrieben wird, als zweites Argument. Anschließend erstellen wir den Stream.

Und schließlich wird die Methode „MathRenderer.render()“ aufgerufen, wobei die Optionen als drittes Argument übergeben werden. Als erstes Argument wird der LaTeX-Code der Formel bereitgestellt.

Die letzten Zeilen des Beispiels zeigen zwei Ausgaben des Rendering-Prozesses der mathematischen Formel – die Größe der Formel und einen kurzen Fehlerbericht, falls Fehler auftreten.

Hier ist das Ergebnis des Renderings.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX-Mathe-Formel-Rendering in PNG](/tex/images/python-net/math-formula.png)</a>

Dies stellt die häufigste und umfassendste Anwendung der **LaTeX-Funktion zum Rendern mathematischer Formeln** dar.

**Sie können auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/png) erkunden, die die implementierte Funktion der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) nutzt.**

## Rendern einer LaTeX-Matheformel in SVG

Ebenso können wir mit dem gleichen Ansatz eine LaTeX-Matheformel in das SVG-Format konvertieren.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Die Unterschiede sind:

* Anstelle der Klasse [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) verwenden wir die Klasse [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Wir geben keine Auflösung an.
* Anstelle der Klasse [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) verwenden wir die Klasse [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Hier ist das Ergebnis:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX-Mathe-Formel-Rendering in SVG](/tex/images/python-net/math-formula.svg)</a>

**Sie können auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/svg) erkunden, die die implementierte Funktion der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) nutzt.**