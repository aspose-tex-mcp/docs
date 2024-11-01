---
translation: true
template: /templates/_template-java.md
title: LaTeX zu PDF | Aspose.TeX für Java
linktitle: LaTeX in PDF
weight: 11
url: /java/latex-to-pdf/
keywords: Latex in PDF, Latex PDF, Latex in PDF konvertieren
description: Um TeX mit der Aspose.TeX für Java in PDF zu konvertieren, lesen Sie diesen Artikel, in dem die Vorgehensweise und die Codebeispiele beschrieben werden.
lastmod: "2024-09-26"
---

{{<section overview>}}


## So konvertieren Sie LaTeX in PDF

Werfen wir einen genaueren Blick auf den Java-Code, der die einfachste Möglichkeit zur Konvertierung von LaTeX in das PDF-Format bietet.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

Das erste, was wir also tun müssen (manchmal nicht das allererste, wie wir später herausfinden werden), ist, eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions) zu erstellen. Die einzige statische Methode, die dies tut, ist [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), also kümmern wir uns nicht um die Bedeutung ihres Namens. Die Methode benötigt eine [Instanz](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) der Klasse [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), die genau zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) geeignet ist. Diese Konfiguration weist die Object-TeX-Engine an, das Object-LaTeX-Format zu laden und bereit zu sein, die LaTeX-Datei zu akzeptieren. Das Objekt-LaTeX-Format ist genau das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, mit der Ausnahme, dass es [Objekt-TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente verwendet, um die Seitenmetriken einzurichten.

Die erste der erforderlichen Optionen ist [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--), die den Raum oder Bereich definiert, in den die TeX-Ausgabe geschrieben wird. [Hier](/tex/{{lang.url-fragment}}java/aspose-tex-output/) finden Sie die Details zum Ausgabeverzeichniskonzept in **Aspose.TeX für Java**. In diesem Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), die es uns ermöglicht, die Ausgabe in das angegebene Verzeichnis oder den angegebenen Ordner zu schreiben.

Die zweite Option ist eine Klasseninstanz [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions), die die Transformation des [Objektmodells](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das Zielformat steuert. Da wir LaTeX in PDF konvertieren, handelt es sich um die Klasseninstanz [PdfSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Dann müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob) erstellen. Wenn wir eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) Version des Konstruktors. Wir sollten den vollständigen Pfad zur Datei angeben. Andernfalls sucht die Engine im aktuellen Verzeichnis (das [hier](https://docs.oracle.com/javase/7/docs/api/java/io/File.html) definiert ist) danach und wird es höchstwahrscheinlich nicht finden. Dennoch können wir die Erweiterung weglassen, wenn unsere Datei die Erweiterung *.tex* hat. Die Engine wird es automatisch anhängen. Das zweite Argument des Konstruktors ist eine Klasseninstanz [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Da wir LaTeX in PDF konvertieren, handelt es sich um eine [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice)-Klasseninstanz. Als letztes Argument übergeben wir die kürzlich vorbereiteten Konvertierungsoptionen.

Jetzt müssen wir nur noch den Job [ausführen](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--).

Unabhängig davon, ob die Ausführung erfolgreich war oder nicht, ist das erste Ergebnis, das wir sehen, die Terminalausgabe. Im Erfolgsfall sieht es etwa so aus:

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

Weitere Produkte des Motorlaufs finden wir in dem Ordner, den wir als Ausgabeverzeichnis angegeben haben. Dabei handelt es sich um die Transkriptdatei (.log) und, **Voila!**, die Hauptausgabe-PDF-Datei.

## Eine alternative Möglichkeit, die Hauptausgabe-PDF-Datei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), mit dem wir die resultierende PDF-Datei auf alternative Weise erhalten können.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

Die Datei *any-name.pdf* im angegebenen Verzeichnis ist unsere Hauptausgabe-PDF-Datei. Gleichzeitig finden wir im Gegensatz zu [Bildausgabe](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files) keine PDF-Dateien in dem durch die Konvertierungsoptionen definierten Ausgabeverzeichnis. Ausnahme: *any-name.pdf* befindet sich (durch seinen Pfad) im selben Dateisystemverzeichnis, das der Option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) mit [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory) zugewiesen ist.

## Über Eingabemöglichkeiten

Falls unsere Haupteingabedatei Abhängigkeiten erfordert, beispielsweise Pakete, die nicht im grundlegenden LaTeX-System und den unterstützten Paketen enthalten sind, MÜSSEN wir die Option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) auf die gleiche Weise festlegen, wie wir die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) festlegen. Option und legen Sie die Abhängigkeiten in diesem Verzeichnis ab. Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Falls wir unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, MÜSSEN wir auch das [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) festlegen, indem wir den Pfad zum Speicherort verwenden, an dem diese Dateien gesammelt werden. Wir können die Haupteingabedatei auch irgendwo im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben (oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet). [Hier](/tex/{{lang.url-fragment}}java/aspose-tex-input/) finden Sie die Details zum Eingabeverzeichniskonzept in **Aspose.TeX für Java** und den bereitgestellten Implementierungen.

Weitere TeX-Joboptionen werden [hier](/tex/{{lang.url-fragment}}java/other-options/) besprochen.

**Sie können sich auch die kostenlose LaTeX-zu-PDF-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-pdf) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**