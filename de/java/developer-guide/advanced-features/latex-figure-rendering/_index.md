---
translation: true
template: /templates/_template-java.md
title: LaTeX-Figurenrendering | Aspose.TeX für Java
linktitle: Darstellung von LaTeX-Figuren
weight: 20
url: /java/latex-figure-rendering/
description: Hier wird Artikel die Aspose.TeX-Lösung für Java das Rendern von LaTeX-Fragmenten (Figuren) beschrieben. Erfahren Sie wie man Funktionalität nutzen kann.
lastmod: "2024-09-26"
---

{{<section overview>}}

Es kann vorkommen, dass Sie Inhalte (eine Zeichnung, eine Schrift, einen Plot usw.) aus einer LaTeX-Datei als separat gerendertes Stück oder als *„Figur“* extrahieren möchten, unabhängig von ihrer Position auf einer Ausgabedokumentseite . Eine Illustration für Ihre Veröffentlichung im Internet ist beispielsweise der Fall. Unsere API kann Ihnen bei dieser Aufgabe helfen. Es stehen zwei Zielformate zur Verfügung: PNG und SVG. Genau wie beim Rendern mathematischer Formeln in LaTeX. Wir müssen auch beachten, dass **LaTeX-Figuren-Rendering** eine Verallgemeinerung von [LaTeX-Mathe-Formel-Rendering](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) ist.

## So rendern Sie eine LaTeX-Figur in PNG

Und wie bei der Formeldarstellung beginnen wir mit einem Beispiel. Hier ist es:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions)-Instanz. Wir tun dies hier zusammen mit der Angabe der Ausgabebildauflösung.

Als nächstes spezifizieren wir die Präambel. Es gibt keine Standard-Präambel für die Darstellung von LaTeX-Figuren. Wenn Sie also beispielsweise einige Grafiken rendern möchten, die mit dem LaTeX-Paket „pict2e“ geplottet wurden, müssen Sie dies in der Präambel angeben:

```tex
\usepackage{pict2e}
```

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächste Option definiert die Hintergrundfarbe. Anders als beim Rendern mathematischer Formeln geben wir keine Vordergrundfarbe an, da wir davon ausgehen, dass die Farben vollständig vom LaTeX-Code gesteuert werden. Tatsächlich gilt dies auch für die Hintergrundfarbe, es handelt sich also lediglich um eine praktische Option.

Die nächste Zeile des Beispiels ergibt wenig Sinn. Es zeigt lediglich, dass Sie die Protokollausgabe an einen Stream weiterleiten können.

Und mit der letzten Option „ShowTerminal“ können Sie das Schreiben der Terminalausgabe in die Konsole umschalten.

Die Methode, die das Rendern tatsächlich durchführt, ist [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Es gibt die Größe der Figur in Punkten zurück.

Der Stream, in den das Bild geschrieben werden soll, wird von der Methode als zweites Argument akzeptiert. Als nächstes erstellen wir den Stream.

Und schließlich rufen wir die Methode „FigureRenderer.render()“ selbst auf und übergeben Optionen als drittes Argument. Als erstes Argument wird der LaTeX-Code der Abbildung übergeben.

Die letzten Zeilen des Beispiels geben zwei Artefakte der Figurendarstellung aus – die Größe der Figur und den kurzen Fehlerbericht (falls Fehler vorliegen).

Hier ist das Ergebnis des Renderns.

![LaTeX-Figuren-Rendering in PNG](/tex/images/java/text-and-formula.png)

Dies ist der allgemeinste Anwendungsfall für die Funktion **LaTeX-Figurenrendering**.

## So rendern Sie eine LaTeX-Figur in SVG

Auf die gleiche Weise können wir eine LaTeX-Figur in das SVG-Format rendern.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Die Unterschiede sind:

 * Wir verwenden die Klasse [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) anstelle von [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
 * Wir geben keine Auflösung an.
 * Wir verwenden die Klasse [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) anstelle von [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).

 
Hier ist das Ergebnis:

<a href="/tex/images/java/text-and-formula.svg">![LaTeX-Figuren-Rendering in SVG](/tex/images/java/text-and-formula.svg)</a>