---
translation: true
template: /templates/_template-python-net.md
title: Bereitstellung der Haupt-TeX-Eingabedatei | Python
linktitle: Andere Möglichkeiten, die Haupt-TeX-Eingabedatei bereitzustellen
weight: 14
url: /python-net/other-ways-of-main-input/
description: Aspose.TeX-API-Lösung für Python enthält einen Konstruktor, der einen Stream als erstes Argument akzeptiert und so Konvertierungsfunktionen bereitstellt.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Bereitstellung der Haupteingabedatei für die TeX-Engine mithilfe eines Streams

Bisher haben wir nur gelernt, wie man der TeX-Engine die [Haupteingabedatei](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) als Dateinamen bereitstellt, sei es in vollständiger Form oder in verkürzter Form, mit oder ohne Erweiterung. Allerdings gibt es in der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) einen [anderen Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions), der einen Stream als erstes Argument akzeptiert. Dies ist nützlich, wenn die Haupteingabedatei aus irgendeinem Grund nicht in Form einer Datei im Dateisystem der Festplatte vorliegt. Hier ein Beispiel, wie es umgesetzt werden kann:

Setzen Sie `ASPOSE_TEX_OUTPUT_DIR` auf das Ausgabeverzeichnis (Standard: `output`). Wenden Sie zuerst eine Lizenz an. [Licensing](/tex/de/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Kodieren Sie ein vollständiges LaTeX-Dokument in einen binären `BytesIO`-Stream und übergeben Sie ihn an `TeXJob` mit `TeXConfig.object_latex`. Halten Sie den Stream während des Auftrags offen. Ergebnis: `texput.xps` und `texput.log`.

Beachten Sie, dass alle Ausgabedateien den Namen „texput“ erhalten. Dies liegt daran, dass die Engine keinen Zugriff auf einen anderen Namen hat. „texput“ ist der Standard-Jobname. Ausführlichere Informationen zu Jobnamen finden Sie in den Absätzen [TeX-Ausgabe](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) und [So legen Sie den Jobnamen fest](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Eingabe der Haupt-TeX-Eingabedatei über das Terminal

In der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) ist [ein weiterer Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) verfügbar, der es uns nicht erlaubt, die Eingabe überhaupt anzugeben. Sie fragen sich vielleicht, was ein solcher TeX-Job verarbeiten würde. In diesem Fall müssten wir ein Eingabeterminal verwenden. Die TeX-Engine fordert uns auf, den Dateinamen vom Terminal aus einzugeben.

Hier ist der Code:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Speichern Sie folgenden plain-TeX-Text als `hello-world.tex` im Ordner `ASPOSE_TEX_INPUT_DIR` (Standard: `input`). Das Beispiel verwendet `TeXConfig.object_tex()`. Geben Sie bei der Aufforderung `hello-world.tex` ein und drücken Sie Enter, oder übergeben Sie den Namen über die Standardeingabe. Ergebnis: `hello-world.xps` und `hello-world.log`.

```tex
Hello, World!
\end
```
