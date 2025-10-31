---
translation: true
template: /templates/_template-net.md
title: LaTeX-Figurenrendering | Aspose.TeX für .NET
linktitle: LaTeX enthält Abbildung
weight: 20
url: /net/latex-figure-rendering/
description: Hier wird Aspose.TeX für .NET das Rendern von LaTeX-Fragmenten (Figuren) beschrieben. Erfahr anhand der Codebeispiele, wie kann man Funktionalität nutzen.
keywords: Latexfigur, Latexfigurengröße, Latexbild, Latexbild, Latex-Einschlussfigur, Latexbild, Latexfigurenoptionen
lastmod: "2024-09-26"
---

{{<section overview>}}


Manchmal möchten Sie vielleicht einige Inhalte aus einer LaTeX-Datei als separat gerendertes Stück oder als *„Figur“* extrahieren, ohne irgendeine Verbindung zum Seitenlayout. Es kann beispielsweise eine Illustration für Ihre Veröffentlichung im Internet sein. Sie können dies mit unserer API tun. Was die Zielformate betrifft, gibt es zwei Optionen: PNG und SVG. Dies ist beispielsweise bei der LaTeX-Funktion zum Rendern mathematischer Formeln der Fall. Es ist auch erwähnenswert, dass **LaTeX-Figuren-Rendering** eine Verallgemeinerung von [LaTeX-Mathe-Formel-Rendering](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) ist.

## So rendern Sie eine LaTeX-Figur in PNG

Der API-Referenzabschnitt zu diesem Thema ist [hier](https://reference.aspose.com/tex/net/aspose.tex.features/). Und wie bei der Formeldarstellung beginnen wir mit einem Beispiel. Hier ist es:

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToPNG.cs" >}}

Zunächst erstellen wir eine [LaTeX-Figurenoptionen](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/)-Instanz. Wir tun dies hier und geben gleichzeitig die Ausgabebildauflösung an.

Als nächstes spezifizieren wir die Präambel. Es gibt keine Standard-Präambel für das Rendern von LaTeX-Figuren. Wenn Sie also beispielsweise einige Grafiken rendern möchten, die mit dem LaTeX-Paket „pict2e“ geplottet wurden, müssen Sie dies in der Präambel angeben:


```tex
\usepackage{pict2e}
```

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächste Option definiert die Hintergrundfarbe. Anders als beim Rendern mathematischer Formeln geben wir keine Vordergrundfarbe an, da wir davon ausgehen, dass die Farben vollständig vom LaTeX-Code gesteuert werden. Tatsächlich gilt dies auch für die Hintergrundfarbe, es handelt sich also lediglich um eine praktische Option.

Die nächste Zeile des Beispiels ergibt wenig Sinn. Es zeigt lediglich, dass Sie die Protokollausgabe an einen Stream weiterleiten können.

Und mit der letzten Option „ShowTerminal“ können Sie das Schreiben der Terminalausgabe in die Konsole umschalten.

Die Methode, die das Rendern tatsächlich durchführt, ist [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Es gibt die Größe der Figur in Punkten zurück.

Der Stream, in den das Bild geschrieben werden soll, wird von der Methode als zweites Argument akzeptiert. Als nächstes erstellen wir den Stream.

Und schließlich rufen wir die Methode „FigureRenderer.Render()“ selbst auf und übergeben Optionen als drittes Argument. Als erstes Argument wird der LaTeX-Code der Abbildung übergeben.

Die letzten Zeilen des Beispiels geben zwei Artefakte der Figurendarstellung aus – die Größe der Figur und den kurzen Fehlerbericht (falls Fehler vorliegen).

Hier ist das Ergebnis des Renderns.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![LaTeX-Figuren-Rendering in PNG](/tex/images/net/text-and-formula.png)</a>

Dies ist der allgemeinste Anwendungsfall für die Funktion **LaTeX-Figurenrendering**.

## So rendern Sie eine LaTeX-Figur in SVG

Auf die gleiche Weise können wir eine LaTeX-Figur im SVG-Format rendern.

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToSVG.cs" >}}

Die Unterschiede sind:

* Wir verwenden die Klasse [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) anstelle von [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Wir geben keine Auflösung an.
* Wir verwenden die Klasse [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) anstelle von [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).


Hier ist das Ergebnis:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![LaTeX-Figurenrendering in SVG](/tex/images/net/text-and-formula.svg)</a>
