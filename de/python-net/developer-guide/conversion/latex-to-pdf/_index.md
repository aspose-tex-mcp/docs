---
translation: true
template: /templates/_template-python-net.md
title: LaTeX zu PDF | Aspose.TeX für Python
linktitle: LaTeX in PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: Latex in PDF, Latex PDF, Latex in PDF konvertieren
description: Erfahren Sie, wie Sie TeX mit der Aspose.TeX-API-Lösung für Python in PDF konvertieren. Er enthält eine ausführliche Erklärung und Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Konvertieren von LaTeX in PDF

Schauen wir uns nun den Python-Code genauer an, der den einfachsten Ansatz zur Konvertierung von LaTeX in das PDF-Format bietet.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Zunächst müssen wir eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) erstellen. Die Methode [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) ist die einzige statische Methode, die dies erreicht, also machen Sie sich über ihren Namen keine Sorgen. Diese Methode benötigt eine [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/)-Instanz der Klasse [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), die sich perfekt zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) eignet. Diese Konfiguration weist die Object-TeX-Engine an, das Object-LaTeX-Format zu laden und sich auf die Verarbeitung der LaTeX-Datei vorzubereiten. Das Object LaTeX-Format ist im Wesentlichen dasselbe wie das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, verwendet jedoch [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente, um die Seitenmetriken zu definieren.

Die erste Option, die angegeben werden muss, ist [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), die den Speicherort bestimmt, an dem die TeX-Ausgabe gespeichert wird. Bei Bedarf finden Sie weitere Informationen zum [Konzept des Ausgabeverzeichnisses in **Aspose.TeX**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). In diesem speziellen Fall verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), die es uns ermöglicht, die Ausgabe in ein bestimmtes Verzeichnis oder einen bestimmten Ordner zu schreiben.

Die zweite Option erfordert eine Instanz der Klasse [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), die bestimmt, wie das [Objektmodell](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das gewünschte Format umgewandelt wird. In unserem Fall verweist es beim Konvertieren von LaTeX in PDF auf eine Instanz der Klasse [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Um eine im Dateisystem gespeicherte LaTeX-Datei zu konvertieren, müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) mit dem [Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions) erstellen, der den vollständigen Pfad der Datei als Parameter verwendet. Wenn wir nicht den vollständigen Pfad angeben, sucht die Engine im aktuellen Verzeichnis (dem Arbeitsverzeichnis des Skripts) nach der Datei und findet sie möglicherweise nicht. Wir können die Erweiterung jedoch weglassen, wenn unsere Datei die Erweiterung „.tex“ hat, da die Engine sie automatisch anhängt. Das zweite Argument des Konstruktors ist eine Instanz der Klasse [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Da wir in unserem Fall LaTeX in PDF konvertieren, handelt es sich um eine Instanz der Klasse [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Abschließend übergeben wir als letztes Argument die kürzlich vorbereiteten Konvertierungsoptionen.

Jetzt müssen Sie nur noch den Job [ausführen](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#).

Nach der Ausführung, unabhängig davon, ob sie erfolgreich war oder nicht, sehen wir als Erstes die Terminalausgabe. Bei erfolgreicher Ausführung sieht die Ausgabe etwa so aus:

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

In dem Ordner, den wir als Ausgabeverzeichnis angegeben haben, finden wir neben anderen Ergebnissen der Arbeit der Engine auch die Transkriptdatei und **hier ist sie!** die Hauptausgabe-PDF-Datei.

## Eine alternative Möglichkeit, die Hauptausgabe-PDF-Datei zu schreiben

Die Klasse *PdfDevice* verfügt über einen weiteren [Konstruktor](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase), der es uns ermöglicht, die resultierende PDF-Datei auf andere Weise zu erhalten.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

Die Hauptausgabe-PDF-Datei erhält den Namen „any-name.pdf“ und befindet sich im angegebenen Verzeichnis. Im Gegensatz zur [Bildausgabe](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files) befinden sich jedoch keine anderen PDF-Dateien im durch die Konvertierungsoptionen angegebenen Ausgabeverzeichnis. Die Ausnahme besteht, wenn sich „any-name.pdf“ im selben Dateisystemverzeichnis befindet, das der Option *output_working_directory* über *OutputFileSystemDirectory* zugewiesen wurde.

## Über Eingabemöglichkeiten

Wenn unsere Haupteingabedatei Abhängigkeiten erfordert, wie z. B. Pakete, die nicht im grundlegenden LaTeX-System enthalten sind, und unterstützte Pakete, ist es notwendig, die Option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) auf ähnliche Weise festzulegen, wie wir die Option *output_working_directory* festlegen Platzieren Sie die Abhängigkeiten in diesem Verzeichnis. Die Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Wenn wir darüber hinaus unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, müssen wir außerdem das [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) festlegen, indem wir den Pfad zum Speicherort dieser Dateien verwenden. Wir können die Haupteingabedatei auch im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet. Weitere Einzelheiten zum Eingabeverzeichniskonzept in **Aspose.TeX für Python** und den bereitgestellten Implementierungen finden Sie [hier](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Es werden auch [andere TeX-Joboptionen](/tex/{{lang.url-fragment}}python-net/other-options/) besprochen.

**Sie können auch die kostenlose [Web-App für die Konvertierung von LaTeX in PDF](https://products.aspose.app/tex/conversion/latex-to-pdf) erkunden, die mit der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) entwickelt wurde.**