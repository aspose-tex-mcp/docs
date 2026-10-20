---
translation: true
template: /templates/_template-java.md
title: LaTeX-Figurenrendering | Aspose.TeX für Java
linktitle: Darstellung von LaTeX-Figuren
weight: 20
url: /java/latex-figure-rendering/
description: Hier wird Artikel die Aspose.TeX-Lösung für Java das Rendern von LaTeX-Fragmenten (Figuren) beschrieben. Erfahren Sie wie man Funktionalität nutzen kann.
lastmod: "2026-04-21"
---

{{<section overview>}}

Es kann vorkommen, dass Sie Inhalte (eine Zeichnung, eine Schrift, einen Plot usw.) aus einer LaTeX-Datei als separat gerendertes Stück oder als *„Figur“* extrahieren möchten, unabhängig von ihrer Position auf einer Ausgabedokumentseite . Eine Illustration für Ihre Veröffentlichung im Internet ist beispielsweise der Fall. Unsere API kann Ihnen bei dieser Aufgabe helfen. Es stehen zwei Zielformate zur Verfügung: PNG und SVG. Genau wie beim Rendern mathematischer Formeln in LaTeX. Wir müssen auch beachten, dass **LaTeX-Figuren-Rendering** eine Verallgemeinerung von [LaTeX-Mathe-Formel-Rendering](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) ist.

## So rendern Sie eine LaTeX-Figur in PNG

Und wie bei der Formeldarstellung beginnen wir mit einem Beispiel. Hier ist es:

Setzen Sie `outputFile` auf einen `java.nio.file.Path` in einem vorhandenen Ordner, beispielsweise `Paths.get(outputDirectory, "text-and-formula.png")` für PNG oder `Paths.get(outputDirectory, "text-and-formula.svg")` für SVG. Importieren Sie die verwendeten Aspose.TeX-Renderer-, Options- und `Size2D`-Klassen sowie `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie gemäß der [Lizenzierungsanleitung](/tex/{{lang.url-fragment}}java/licensing/) eine Lizenz an, um Evaluierungseinschränkungen zu vermeiden.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToPNG.java" >}}

Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/)-Instanz. Wir tun dies hier zusammen mit der Angabe der Ausgabebildauflösung.

Als nächstes spezifizieren wir die Präambel. Es gibt keine Standard-Präambel für die Darstellung von LaTeX-Figuren. Wenn Sie also beispielsweise einige Grafiken rendern möchten, die mit dem LaTeX-Paket „pict2e“ geplottet wurden, müssen Sie dies in der Präambel angeben:

```tex
\usepackage{pict2e}
```

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren. Die Beispiele setzen außerdem mit `setMargin(5)` einen Rand von 5 Punkten um die Figur. Das PNG-Beispiel verwendet 150 DPI.

Die nächste Option definiert die Hintergrundfarbe. Anders als beim Rendern mathematischer Formeln geben wir keine Vordergrundfarbe an, da wir davon ausgehen, dass die Farben vollständig vom LaTeX-Code gesteuert werden. Tatsächlich gilt dies auch für die Hintergrundfarbe, es handelt sich also lediglich um eine praktische Option.

Das Beispiel leitet Rendering-Protokolle mit `setLogStream()` an einen `ByteArrayOutputStream` weiter. Protokoll- und Bildausgabestream werden nach dem Rendern automatisch geschlossen.

`showTerminal()` steuert die Terminalausgabe in der Konsole. Die Beispiele verwenden `false`; setzen Sie `true`, um die Ausgabe anzuzeigen.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) wird auf einer `PngFigureRenderer`- oder `SvgFigureRenderer`-Instanz aufgerufen und gibt die Figurgröße in Punkten als `Size2D` zurück.

Die Methode akzeptiert den Bildausgabestream als zweites Argument. Das Beispiel öffnet ihn in einem try-with-resources-Block, der ihn nach dem Rendern schließt.

Schließlich rufen wir `render()` auf der Renderer-Instanz auf: Die LaTeX-Figur ist das erste Argument, der Bildausgabestream das zweite und die Rendering-Optionen das dritte.

Die letzten Zeilen des Beispiels geben zwei Artefakte der Figurendarstellung aus – die Größe der Figur und den kurzen Fehlerbericht (falls Fehler vorliegen).

Hier ist das Ergebnis des Renderns.

![LaTeX-Figuren-Rendering in PNG](/tex/images/java/text-and-formula.png)

Dies ist der allgemeinste Anwendungsfall für die Funktion **LaTeX-Figurenrendering**.

## So rendern Sie eine LaTeX-Figur in SVG

Auf die gleiche Weise können wir eine LaTeX-Figur in das SVG-Format rendern.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderFigureToSVG.java" >}}

Die Unterschiede sind:

 * Wir verwenden die Klasse [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) anstelle von [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
 * Wir geben keine Auflösung an.
 * Wir verwenden die Klasse [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) anstelle von [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).

 
Hier ist das Ergebnis:

<a href="/tex/images/java/text-and-formula.svg">![LaTeX-Figuren-Rendering in SVG](/tex/images/java/text-and-formula.svg)</a>