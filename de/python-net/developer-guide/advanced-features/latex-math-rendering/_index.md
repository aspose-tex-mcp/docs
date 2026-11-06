---
translation: true
template: /templates/_template-python-net.md
title: Rendern von LaTeX-Matheformeln | Python
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /python-net/latex-math-formula-rendering/
description: Der Artikel bietet einen Überblick über die Aspose.TeX-API-Lösung für Python und ihre Funktionalität zum Rendern von LaTeX-Matheformeln.
lastmod: "2026-04-03"
---

{{<section overview>}}

## Rendern einer LaTeX-Matheformel in PNG

Werfen Sie bei Bedarf einen Blick auf den [API-Referenzabschnitt für dieses Thema](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Tatsächlich lässt sich die Renderfunktion für **LaTeX-Matheformeln** am besten demonstrieren, indem man mit einem Beispiel beginnt. Hier ist es:

Setzen Sie `ASPOSE_TEX_OUTPUT_DIR` auf Ihr Ausgabeverzeichnis oder verwenden Sie den Standardordner `output`. Der LaTeX-Code ist vollständig in den Beispielen enthalten; externe Eingabedateien sind nicht erforderlich. Wenden Sie zuerst eine Lizenz an. [Lizenzierung](/tex/de/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Kommen wir zu den Details. Zuerst initiieren wir ein [rendering options](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/)-Objekt, ähnlich dem TeX/LaTeX-Schriftsatz, das die Spezifikation für die gewünschte Ausgabebildauflösung enthält.

Als nächstes spezifizieren wir die Präambel. Die Standardpräambel lautet:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

das im Vergleich zum Standard-LaTeX eine verbesserte Unterstützung für mathematische Formeln bietet. Sie können beispielsweise das Paket „color“ einschließen, um die Hervorhebung in der Formel anzupassen, wie im bereitgestellten Codebeispiel gezeigt.

Mit `scale = 3000` wird die Ausgabe auf 300 % skaliert; `margin = 5` lässt Platz um das Fragment. Das PNG-Beispiel verwendet `resolution = 150` DPI.

Die nächsten beiden Optionen bestimmen die Vordergrund- und Hintergrundfarben. Alle Teile der Formel, die von der benutzerdefinierten Hervorhebung nicht betroffen sind, werden in der Farbe „text_color“ angezeigt.

Das Beispiel weist `log_stream` einen binären Dateistream zu und speichert das Protokoll als `math-formula.png.log` neben `math-formula.png`. Die `with`-Anweisung schließt beide Streams automatisch.

`show_terminal` steuert die Terminalausgabe in der Konsole. Die Beispiele setzen diese Option auf `False`; das Protokoll wird weiterhin in die Datei geschrieben.

Der eigentliche Rendervorgang wird von der Methode [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/) durchgeführt, die die Größe der Formel in Punkten zurückgibt.

Das zweite Argument ist der binäre Ausgabestream für das Bild. Das dritte Argument enthält die Rendering-Optionen.

Und schließlich wird die Methode „MathRenderer.render()“ aufgerufen, wobei die Optionen als drittes Argument übergeben werden. Als erstes Argument wird der LaTeX-Code der Formel bereitgestellt.

Die letzten Zeilen geben den Fehlerbericht oder bei leerem Bericht `No rendering errors.` aus, gefolgt von Breite und Höhe in Punkten.

Hier ist das Ergebnis des Renderings.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![LaTeX-Mathe-Formel-Rendering in PNG](/tex/images/python-net/math-formula.png)</a>

Dies stellt die häufigste und umfassendste Anwendung der **LaTeX-Funktion zum Rendern mathematischer Formeln** dar.

**Sie können auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/png) erkunden, die die implementierte Funktion der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) nutzt.**

## Rendern einer LaTeX-Matheformel in SVG

Ebenso können wir mit dem gleichen Ansatz eine LaTeX-Matheformel in das SVG-Format konvertieren.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Dieses Beispiel erstellt `math-formula.svg` und das Protokoll `math-formula.svg.log` im selben Ausgabeverzeichnis.

Die Unterschiede sind:

* Anstelle der Klasse [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/) verwenden wir die Klasse [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Wir geben keine Auflösung an.
* Anstelle der Klasse [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/) verwenden wir die Klasse [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Hier ist das Ergebnis:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![LaTeX-Mathe-Formel-Rendering in SVG](/tex/images/python-net/math-formula.svg)</a>

**Sie können auch die kostenlose [Web-App](https://products.aspose.app/tex/equation-editor/svg) erkunden, die die implementierte Funktion der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) nutzt.**