---
translation: true
template: /templates/_template-java.md
title: Rendern von LaTeX-Matheformeln | Aspose.TeX für Java
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /java/latex-math-formula-rendering/
description: Das Rendern mathematischer LaTeX-Formeln innerhalb der Aspose.TeX für Java wird im Artikel beschrieben. Erfahren Sie wie man Funktionalität nutzen kann.
lastmod: "2026-04-21"
---

{{<section overview>}}

## So rendern Sie eine LaTeX-Matheformel in PNG

Tatsächlich lässt sich die Renderfunktion für **LaTeX-Matheformeln** am einfachsten demonstrieren, indem man mit dem Beispiel beginnt. Hier ist es:

Setzen Sie `outputFile` auf einen `java.nio.file.Path` in einem vorhandenen Ordner, beispielsweise `Paths.get(outputDirectory, "math-formula.png")` für PNG oder `Paths.get(outputDirectory, "math-formula.svg")` für SVG. Importieren Sie die verwendeten Aspose.TeX-Renderer-, Options- und `Size2D`-Klassen sowie `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie gemäß der [Lizenzierungsanleitung](/tex/{{lang.url-fragment}}java/licensing/) eine Lizenz an, um Evaluierungseinschränkungen zu vermeiden.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Kommen wir zu den Details. Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/)-Instanz, ähnlich dem TeX/LaTeX-Schriftsatz. Wir tun dies hier und geben gleichzeitig die Ausgabebildauflösung an.

Als nächstes spezifizieren wir die Präambel. Die Standardpräambel lautet:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

Dies bietet etwas erweiterte Unterstützung für mathematische Formeln als einfaches LaTeX. Sie können beispielsweise das Paket `color` hinzufügen, wenn Sie Ihre eigene Hervorhebung in der Formel verwenden möchten, wie wir im Codebeispiel gezeigt haben.

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die beiden Optionen definieren Vordergrund- und Hintergrundfarben. Ohne benutzerdefinierte Hervorhebung verwendet die Formel die mit `setTextColor()` festgelegte Farbe.

Das Beispiel leitet Rendering-Protokolle mit `setLogStream()` an einen `ByteArrayOutputStream` weiter. Protokoll- und Bildausgabestream werden nach dem Rendern automatisch geschlossen.

`showTerminal()` steuert die Terminalausgabe in der Konsole. Die Beispiele verwenden `false`; setzen Sie `true`, um die Ausgabe anzuzeigen.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) wird auf einer `PngMathRenderer`- oder `SvgMathRenderer`-Instanz aufgerufen und gibt die Formelgröße in Punkten als `Size2D` zurück.

Die Methode akzeptiert den Bildausgabestream als zweites Argument. Das Beispiel öffnet ihn in einem try-with-resources-Block, der ihn nach dem Rendern schließt.

Schließlich rufen wir `render()` auf der Renderer-Instanz auf: Die LaTeX-Formel ist das erste Argument, der Bildausgabestream das zweite und die Rendering-Optionen das dritte.

Die letzten Zeilen des Beispiels geben zwei Artefakte der mathematischen Formeldarstellung aus – die Größe der Formel und den kurzen Fehlerbericht (für den Fall, dass Fehler aufgetreten sind).

Hier ist das Ergebnis des Renderns.

<a href="/tex/images/java/math-formula.png">![LaTeX-Figuren-Rendering in PNG](/tex/images/java/math-formula.png)</a>

Dies ist der allgemeinste Anwendungsfall für das Rendern von **LaTeX-Matheformeln**.

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/png) ansehen, die auf der in der [Aspose.TeX for .NET](https://products.aspose.com/tex/net/)-API implementierten Funktion basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**

## So rendern Sie eine LaTeX-Matheformel in SVG

Auf die gleiche Weise können wir eine LaTeX-Matheformel in das SVG-Format rendern.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Die Unterschiede sind:

* Wir verwenden die Klasse [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) anstelle von [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Wir geben keine Auflösung an.
* Wir verwenden die Klasse [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) anstelle von [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Hier ist das Ergebnis:

<a href="/tex/images/java/math-formula.svg">![LaTeX-Mathe-Formel-Rendering in SVG](/tex/images/java/math-formula.svg)</a>

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/svg) ansehen, die auf der in [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) implementierten Funktion basiert.**