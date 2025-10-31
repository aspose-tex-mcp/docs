---
translation: true
template: /templates/_template-net.md
title: Rendern von LaTeX-Matheformeln | Aspose.TeX für .NET
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /net/latex-math-formula-rendering/
description: Hier wird Aspose.TeX für .NET die Darstellung math Formeln in LaTeX beschrieben. Erfahr anhand der Codebeispiele, wie kann man Funktionalität nutzen.
lastmod: "2024-09-26"
---

{{<section overview>}}


## So rendern Sie eine LaTeX-Matheformel in PNG

Der API-Referenzabschnitt zu diesem Thema ist [hier](https://reference.aspose.com/tex/net/aspose.tex.features/). Tatsächlich ist es am einfachsten, die **LaTeX-Funktion zum Rendern mathematischer Formeln** zu demonstrieren, indem man mit dem Beispiel beginnt. Hier ist es:

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToPNG.cs" >}}

Kommen wir zu den Details. Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/)-Instanz, ähnlich dem TeX/LaTeX-Schriftsatz. Wir tun dies hier und geben gleichzeitig die Ausgabebildauflösung an.

Als nächstes spezifizieren wir die Präambel. Die Standardpräambel lautet:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

Dies bietet etwas erweiterte Unterstützung für mathematische Formeln als einfaches LaTeX. Sie können beispielsweise das Paket „color“ hinzufügen, wenn Sie Ihre eigene Hervorhebung in der Formel verwenden möchten, wie wir im Codebeispiel gezeigt haben.

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächsten beiden Optionen definieren die Vordergrund- und Hintergrundfarben. Die Teile der Formel, die nicht durch die benutzerdefinierte Hervorhebung abgedeckt („eingefärbt“) werden, werden in der Farbe „TextColor“ angezeigt.

Die nächste Zeile des Beispiels ergibt wenig Sinn. Es zeigt lediglich, dass Sie die Protokollausgabe an einen Stream weiterleiten können.

Und mit der letzten Option „ShowTerminal“ können Sie das Schreiben der Terminalausgabe in die Konsole umschalten.

Die Methode, die das Rendern tatsächlich durchführt, ist [MathRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/). Es gibt die Größe der Formel in Punkten zurück.

Der Stream, in den das Bild geschrieben werden soll, wird von der Methode als zweites Argument akzeptiert. Als nächstes erstellen wir den Stream.

Und schließlich rufen wir die Methode „MathRenderer.Render()“ selbst auf und übergeben Optionen als drittes Argument. Als erstes Argument wird der LaTeX-Code der Formel übergeben.

Die letzten Zeilen des Beispiels geben zwei Artefakte der mathematischen Formeldarstellung aus – die Größe der Formel und den kurzen Fehlerbericht (falls Fehler vorliegen).

Hier ist das Ergebnis des Renderns.

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![LaTeX-Mathe-Formel-Rendering in PNG](/tex/images/net/math-formula.png)</a>

Dies ist der allgemeinste Anwendungsfall für die Funktion **LaTeX-Rendering mathematischer Formeln**.

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/png) ansehen, die auf der in [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) implementierten Funktion basiert.**

## So rendern Sie eine LaTeX-Matheformel in SVG

Auf die gleiche Weise können wir eine LaTeX-Matheformel in das SVG-Format rendern.

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToSVG.cs" >}}

Die Unterschiede sind:

* Wir verwenden die Klasse [SvgMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) anstelle von [PngMathRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/).
* Wir geben keine Auflösung an.
* Wir verwenden die Klasse [SvgMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) anstelle von [PngMathRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/).

 
Hier ist das Ergebnis:

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![LaTeX-Mathe-Formel-Rendering in SVG](/tex/images/net/math-formula.svg)</a>

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/svg) ansehen, die auf der in [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) implementierten Funktion basiert.**
