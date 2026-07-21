---
translation: true
template: /templates/_template-python-net.md
title: LaTeX-Figurenrendering | Aspose.TeX für Python
linktitle: LaTeX enthält Abbildung
weight: 20
url: /python-net/latex-figure-rendering/
description: Der Artikel gibt einen Überblick über die Aspose.TeX-API-Lösung für Python und ihre Funktionalität zum Rendern von LaTeX-Fragmenten (Abbildungen).
keywords: Latexfigur, Latexfigurengröße, Latexbild, Latexbild, Latex-Einschlussfigur, Latexbild, Latexfigurenoptionen
lastmod: "2026-04-03"
---

{{<section overview>}}

In bestimmten Situationen müssen Sie möglicherweise bestimmte Inhalte aus einer LaTeX-Datei als eigenständiges gerendertes Stück extrahieren, das üblicherweise als *Abbildung* bezeichnet wird, ohne Verbindung zum Seitenlayout. Dies könnte beispielsweise beim Erstellen von Illustrationen für eine Online-Publikation nützlich sein. Unsere API ermöglicht Ihnen dies. Die Zielformate für die Darstellung von Zahlen sind PNG und SVG, genau wie bei der LaTeX-Funktion zur Darstellung mathematischer Formeln. Es ist erwähnenswert, dass **LaTeX-Figurenrendering** eine allgemeinere Funktion im Vergleich zu [LaTeX-Rendering von mathematischen Formeln](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/) ist.

## Rendern einer LaTeX-Figur in PNG

Werfen Sie bei Bedarf zunächst einen Blick auf den [API-Referenzabschnitt für dieses Thema](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Ähnlich wie bei der Formeldarstellung beginnen wir mit einem Beispiel. Hier ist es:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Zunächst erstellen wir eine Instanz der Klasse [LaTeX Figure Renderer Options](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), in der wir gleichzeitig die Ausgabebildauflösung angeben.

Als nächstes müssen wir die Präambel angeben. Im Gegensatz zum Rendern mathematischer Formeln in LaTeX gibt es für das Rendern von Zahlen in LaTeX keine Standardpräambel. Wenn Sie also planen, Grafiken zu rendern, die beispielsweise mit dem LaTeX-Paket „pict2e“ erstellt wurden, müssen Sie dies in der Präambel angeben:

```tex
\usepackage{pict2e}
```

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächste Option bestimmt die Hintergrundfarbe. Anders als beim Rendern mathematischer Formeln müssen wir keine Vordergrundfarbe angeben, da wir davon ausgehen, dass die Farben vollständig vom LaTeX-Code gesteuert werden. Ebenso wird die Hintergrundfarbe ebenfalls durch den LaTeX-Code gesteuert, sodass diese Option lediglich der Einfachheit halber bereitgestellt wird.

Die folgende Zeile im Beispiel ist möglicherweise nicht besonders aussagekräftig. Es soll lediglich zeigen, dass Sie die Möglichkeit haben, die Protokollausgabe an einen bestimmten Stream weiterzuleiten.

Mit der letzten Option „ShowTerminal“ können Sie steuern, ob die Terminalausgabe in der Konsole angezeigt werden soll.

Die für das Rendern der Figur verantwortliche Methode ist [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions) . Es gibt die Größe der Figur in Punkten zurück.

Die Methode akzeptiert einen Stream als zweites Argument. Dabei handelt es sich um den Stream, in den das Bild geschrieben wird. Den Stream erstellen wir in der nächsten Zeile.

Schließlich rufen wir die Methode „FigureRenderer.render()“ selbst auf und übergeben die Optionen als drittes Argument. Als erstes Argument wird der LaTeX-Code der Abbildung bereitgestellt.

In den letzten Zeilen des Beispiels werden zwei Informationen zur Abbildungsdarstellung angezeigt: die Größe der Abbildung und ein kurzer Fehlerbericht (falls Fehler vorliegen).

Hier ist das Ergebnis des Renderns.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![LaTeX-Figuren-Rendering in PNG](/tex/images/python-net/text-and-formula.png)</a>

Dies stellt den allgemeinsten Anwendungsfall für die Funktion **LaTeX-Figurenrendering** dar.

## Rendern einer LaTeX-Figur in SVG

Ebenso können wir eine LaTeX-Figur im SVG-Format rendern.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Die Unterschiede sind:

* Anstelle der Klasse [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/) verwenden wir die Klasse [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Wir müssen die Auflösung nicht angeben.
* Anstelle der Klasse [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/) verwenden wir die Klasse [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).
 
Hier ist das Ergebnis:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![LaTeX-Figurenrendering in SVG](/tex/images/python-net/text-and-formula.svg)</a>