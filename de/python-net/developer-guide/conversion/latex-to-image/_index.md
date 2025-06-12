---
translation: true
template: /templates/_template-python-net.md
title: LaTeX zum Bild | Aspose.TeX für Python
linktitle: LaTeX zum Bild
weight: 10
url: /python-net/latex-to-image/
keywords: Latex zu PNG, Latex PNG, Latex zu Bild, Latex Bild, Latex zu JPG, Latex JPG, Latex zu JPEG, Latex JPEG, Latex zu TIFF, Latex TIFF, Latex zu BMP, Latex BMP
description: Um TeX mit Aspose.TeX für Python in Bildformate zu konvertieren, lesen Sie die Artikel, in dem die Vorgehensweise und die Codebeispiele beschrieben werden.
lastmod: "2024-09-26"
---

{{<section overview>}}

**Aspose.TeX für Python** bietet uns die Möglichkeit, LaTeX-Dateien in verschiedene Rasterbildformate zu konvertieren.

## Konvertieren von LaTeX in PNG

Schauen wir uns nun den Python-Code an, der den einfachsten Ansatz zur Konvertierung von LaTeX in das PNG-Format bietet.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Zunächst müssen wir mit der Methode [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) erstellen. Machen Sie sich keine Sorgen um den Namen, es ist nur die statische Methode, die die Instanz erstellt. Diese Methode verwendet die Instanz [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) der Klasse [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), die sich perfekt zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) eignet. Diese Konfiguration richtet die Object TeX-Engine so ein, dass sie das Object LaTeX-Format lädt und für die Verarbeitung der LaTeX-Datei bereit ist. Das Object-LaTeX-Format ist im Wesentlichen dasselbe wie das [LaTeX-Format](/tex/{{lang.url-fragment}}net/what-is-latex/), verwendet jedoch [Object-TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente, um die Seitenmetriken zu definieren.

Die erste der notwendigen Optionen ist [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), die den Speicherort angibt, an dem die TeX-Ausgabe gespeichert wird. Bei Interesse können Sie weitere Informationen zum Konzept des [Ausgabeverzeichnisses in **Aspose.TeX für Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/) erfahren. In diesem speziellen Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), um die Ausgabe in ein bestimmtes Verzeichnis oder einen bestimmten Ordner zu schreiben.

Die zweite Option ist eine Instanz der Klasse [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), die für die Verwaltung der Konvertierung vom [Objektmodell](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das gewünschte Format verantwortlich ist. Da wir in diesem Fall LaTeX in PNG konvertieren, verwenden wir die Klasseninstanz [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), mit der wir die Auflösung der Ausgabebilder angeben können.

Als nächstes erstellen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). Da wir in diesem Fall eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese Version des Konstruktors](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions). Wir müssen den vollständigen Pfad zur Datei angeben, andernfalls sucht die Engine im aktuellen Verzeichnis (dem Arbeitsverzeichnis des Skripts) danach und findet sie möglicherweise nicht. Die Erweiterung „.tex“ kann jedoch weggelassen werden, da die Engine sie automatisch anhängt. Das zweite Argument des Konstruktors ist eine Instanz der Klasse [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Da wir LaTeX in PNG konvertieren, handelt es sich um eine [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/)-Klasseninstanz, die allen unterstützten Bildformaten gemeinsam ist. Abschließend übergeben wir als letztes Argument die vorbereiteten Konvertierungsoptionen.

Jetzt müssen Sie nur noch den Job [ausführen](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#).

Nachdem der Job ausgeführt wurde, ist die erste Ausgabe, auf die wir stoßen, unabhängig von Erfolg oder Misserfolg, die Terminalausgabe. Bei erfolgreicher Ausführung sieht die Ausgabe etwa wie folgt aus:


```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Die Ergebnisse der Arbeit der Engine finden Sie im von uns angegebenen Ausgabeverzeichnis. Dazu gehören die Transkriptdatei und vor allem die PNG-Bilddatei(en) für die Hauptausgabe.

## Eine alternative Möglichkeit, die Hauptausgabe-PNG-Datei(en) zu schreiben.

Es gibt eine alternative Methode, um Bilddaten als Array von Byte-Arrays zu erhalten, wobei jedes Array in der zweiten Dimension die Bilddaten für eine separate Seite darstellt.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Die Datei(en) „page-n.png“ können in jeden angegebenen Pfad geschrieben werden. Im Gegensatz zu [PDF-Ausgabe](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) duplizieren diese PNG-Dateien die Ausgabe-PNG-Dateien, die in das Ausgabeverzeichnis geschrieben werden.

## Zu den Eingabemöglichkeiten

Wenn unsere Haupteingabedatei Abhängigkeiten erfordert, wie etwa Pakete, die nicht im grundlegenden LaTeX-System enthalten sind, oder unterstützte Pakete, müssen wir die Option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) auf ähnliche Weise festlegen, wie wir die Option *output_working_directory* festlegen Platzieren Sie die Abhängigkeiten in diesem Verzeichnis. Die Abhängigkeiten können je nach Bedarf in Unterverzeichnissen organisiert werden. Wenn wir unsere Dateien in den Satzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, müssen wir auch das [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) auf den Speicherort dieser Dateien festlegen. Wir können die Haupteingabedatei auch im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet. Es gibt auch weitere Details zum [Eingabeverzeichniskonzept](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) in **Aspose.TeX** und den bereitgestellten Implementierungen, die beschrieben werden.

Erfahren Sie auch die [anderen TeX-Joboptionen hier](/tex/{{lang.url-fragment}}python-net/other-options/).

**Sie können auch die kostenlose [Web-App](https://products.aspose.app/tex/conversion/latex-to-png) für die Konvertierung von LaTeX in PNG erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**

Im Folgenden erklären wir kurz die Konvertierung von LaTeX in andere unterstützte Rasterbildformate, ohne zu sehr ins Detail zu gehen, da es keine wesentlichen Unterschiede gibt. Die einzige Variation liegt im Typ der Eigenschaft [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) in den Konvertierungsoptionen.

## Konvertieren von LaTeX in JPG

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in JPG](https://products.aspose.app/tex/conversion/latex-to-jpg) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**

## Konvertieren von LaTeX in TIFF

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in TIFF](https://products.aspose.app/tex/conversion/latex-to-tiff) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**

## Konvertieren von LaTeX in BMP

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in BMP](https://products.aspose.app/tex/conversion/latex-to-bmp) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**


## Konvertieren von LaTeX in SVG

Ein weiteres unterstütztes Zielformat ist [**SVG**](https://en.wikipedia.org/wiki/SVG). **Skalierbare Vektorgrafiken (SVG)** ist ein XML-basiertes Vektorbildformat, das zur Definition zweidimensionaler Grafiken verwendet wird. Es unterstützt Interaktivität und Animation.

**SVG**-Bilder werden in XML-Textdateien gespeichert und in einem Vektorgrafikformat definiert. Dies bedeutet, dass **SVG**-Bilder ohne Qualitätsverlust in der Größe skaliert werden können und **SVG**-Dateien selbst durchsucht, indiziert, mit Skripts versehen und komprimiert werden können. Die XML-Textdateien können mit Texteditoren oder Vektorgrafik-Editoren erstellt und bearbeitet werden und können von den am häufigsten verwendeten Webbrowsern gerendert werden.

Die [**Aspose.SVG**](https://products.aspose.com/svg/) API bietet eine Reihe von Funktionen für die Arbeit mit **SVG**, wie zum Beispiel das Erstellen, Laden, Bearbeiten und Konvertieren von **SVG**-Dokumenten.

Das Konvertieren von LaTeX in SVG ist genauso einfach wie das [Konvertieren in Rasterbildformate](/tex/{{lang.url-fragment}}python-net/latex-to-image/), mit dem einzigen Unterschied, dass [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) auf eine Instanz der Klasse [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) gesetzt werden muss und die Das Gerät muss in eine Instanz der Klasse [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/) geändert werden.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in SVG](https://products.aspose.app/tex/conversion/latex-to-svg) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**