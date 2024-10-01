---
translation: true
template: /templates/_template-python-net.md
title: Alternative Methoden zur Bereitstellung der Haupt-TeX-Eingabedatei | Python
linktitle: Andere Möglichkeiten, die Haupt-TeX-Eingabedatei bereitzustellen
weight: 14
url: /python-net/other-ways-of-main-input/
description: Die Aspose.TeX-API-Lösung für Python enthält einen Konstruktor, der einen Stream als erstes Argument akzeptiert und so Konvertierungsfunktionen bereitstellt.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Bereitstellung der Haupteingabedatei für die TeX-Engine mithilfe eines Streams

Bisher haben wir nur gelernt, wie man der TeX-Engine die [Haupteingabedatei](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) als Dateinamen bereitstellt, sei es in vollständiger Form oder in verkürzter Form, mit oder ohne Erweiterung. Allerdings gibt es in der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) einen [anderen Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions), der einen Stream als erstes Argument akzeptiert. Dies ist nützlich, wenn die Haupteingabedatei aus irgendeinem Grund nicht in Form einer Datei im Dateisystem der Festplatte vorliegt. Hier ein Beispiel, wie es umgesetzt werden kann:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Beachten Sie, dass alle Ausgabedateien den Namen „texput“ erhalten. Dies liegt daran, dass die Engine keinen Zugriff auf einen anderen Namen hat. „texput“ ist der Standard-Jobname. Ausführlichere Informationen zu Jobnamen finden Sie in den Absätzen [TeX-Ausgabe](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) und [So legen Sie den Jobnamen fest](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Eingabe der Haupt-TeX-Eingabedatei über das Terminal

In der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) ist [ein weiterer Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) verfügbar, der es uns nicht erlaubt, die Eingabe überhaupt anzugeben. Sie fragen sich vielleicht, was ein solcher TeX-Job verarbeiten würde. In diesem Fall müssten wir ein Eingabeterminal verwenden. Die TeX-Engine fordert uns auf, den Dateinamen vom Terminal aus einzugeben.

Hier ist der Code:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Sobald es ausgeführt wird, hält die Engine an und wartet darauf, dass wir den Dateinamen eingeben (mit oder ohne Pfad und mit oder ohne Erweiterung):


![Terminalfenster](/tex/images/python-net/.png)

Und so würde es auf dem Ausgabeterminal (Konsole) aussehen:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```