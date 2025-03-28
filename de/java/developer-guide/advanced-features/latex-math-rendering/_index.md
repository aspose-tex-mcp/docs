---
translation: true
template: /templates/_template-java.md
title: Rendern von LaTeX-Matheformeln | Java
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /java/latex-math-formula-rendering/
description: Das Rendern mathematischer LaTeX-Formeln innerhalb der Aspose.TeX für Java wird im Artikel beschrieben. Erfahren Sie wie man Funktionalität nutzen kann.
lastmod: "2024-09-26"
---

{{<section overview>}}

## So rendern Sie eine LaTeX-Matheformel in PNG

Tatsächlich lässt sich die Renderfunktion für **LaTeX-Matheformeln** am einfachsten demonstrieren, indem man mit dem Beispiel beginnt. Hier ist es:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Kommen wir zu den Details. Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions)-Instanz, ähnlich dem TeX/LaTeX-Schriftsatz. Wir tun dies hier und geben gleichzeitig die Ausgabebildauflösung an.

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

Die Methode, die das Rendern tatsächlich durchführt, ist [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Es gibt die Größe der Formel in Punkten zurück.

Der Stream, in den das Bild geschrieben werden soll, wird von der Methode als zweites Argument akzeptiert. Als nächstes erstellen wir den Stream.

Und schließlich rufen wir die Methode „MathRenderer.render()“ selbst auf und übergeben Optionen als drittes Argument. Als erstes Argument wird der LaTeX-Code der Formel übergeben.

Die letzten Zeilen des Beispiels geben zwei Artefakte der mathematischen Formeldarstellung aus – die Größe der Formel und den kurzen Fehlerbericht (für den Fall, dass Fehler aufgetreten sind).

Hier ist das Ergebnis des Renderns.

<a href="/tex/images/java/math-formula.png">![LaTeX-Figuren-Rendering in PNG](/tex/images/java/math-formula.png)</a>

Dies ist der allgemeinste Anwendungsfall für das Rendern von **LaTeX-Matheformeln**.

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/png) ansehen, die auf der in der [Aspose.TeX for .NET](https://products.aspose.com/tex/net/)-API implementierten Funktion basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**

## So rendern Sie eine LaTeX-Matheformel in SVG

Auf die gleiche Weise können wir eine LaTeX-Matheformel in das SVG-Format rendern.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Die Unterschiede sind:

 * Wir verwenden die Klasse [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) anstelle von [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
 * Wir geben keine Auflösung an.
 * Wir verwenden die Klasse [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) anstelle von [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Hier ist das Ergebnis:

<a href="/tex/images/java/math-formula.svg">![LaTeX-Mathe-Formel-Rendering in SVG](/tex/images/java/math-formula.svg)</a>

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/svg) ansehen, die auf der in [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) implementierten Funktion basiert.**