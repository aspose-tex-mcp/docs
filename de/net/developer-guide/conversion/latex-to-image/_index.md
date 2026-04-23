---
translation: true
template: /templates/_template-net.md
title: LaTeX zum Bild | .NET
linktitle: LaTeX zum Bild
weight: 10
url: /net/latex-to-image/
keywords: Latex zu PNG, Latex PNG, Latex zu Bild, Latex Bild, Latex zu JPG, Latex JPG, Latex zu JPEG, Latex JPEG, Latex zu TIFF, Latex TIFF, Latex zu BMP, Latex BMP
description: Um TeX mit der Aspose.TeX für .NET in Bildformate zu konvertieren, lesen Sie diesen Artikel, in dem die Vorgehensweise beschrieben werden.
lastmod: "2026-04-22"
---

{{<section overview>}}

**Aspose.TeX für .NET** ermöglicht uns die Konvertierung von LaTeX-Dateien in eine Reihe von Rasterbildformaten.

## So konvertieren Sie LaTeX in PNG

Werfen wir einen detaillierten Blick auf den Code in C#, der die einfachste Möglichkeit zum Konvertieren von LaTeX in das PNG-Format bietet.

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Das erste, was wir also tun müssen (na ja, manchmal nicht das allererste), ist, eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) zu erstellen. Die einzige statische Methode, die dies tut, ist [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/). Lassen Sie uns also nicht über die Bedeutung ihres Namens rätseln. Die Methode verwendet die [ObjectLaTeX-Instanz](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) der Klasse [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), die genau zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) geeignet ist. Diese Konfiguration weist die Object TeX-Engine an, das Object LaTeX-Format zu laden und bereit zu sein, die LaTeX-Datei zu akzeptieren. Das Object LaTeX-Format ist eigentlich nur das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, außer dass es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente verwendet, um die Seitenmetriken einzurichten.

Die erste der erforderlichen Optionen ist [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/), die den Raum oder Bereich definiert, in den die TeX-Ausgabe geschrieben wird. [Hier](/tex/{{lang.url-fragment}}net/aspose-tex-output/) finden Sie die Details zum Ausgabeverzeichniskonzept in **Aspose.TeX für .NET**. In diesem Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), mit der wir die Ausgabe in das angegebene Verzeichnis oder den angegebenen Ordner schreiben können.

Die zweite Option ist eine Klasseninstanz [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), die die Transformation des [Objektmodells](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das Zielformat steuert. Da wir LaTeX in PNG konvertieren, ist es die Klasseninstanz [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), mit der wir die Auflösung der Ausgabebilder festlegen können.

Dann müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/) erstellen. Wenn wir eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) Version des Konstruktors. Wir müssen den vollständigen Pfad zur Datei angeben. Andernfalls sucht die Engine im aktuellen Verzeichnis ([CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) danach und wird es höchstwahrscheinlich nicht finden. Dennoch kann die Erweiterung *.tex* weggelassen werden. Die Engine wird es automatisch anhängen. Das zweite Argument des Konstruktors ist eine Klasseninstanz [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Da wir LaTeX in PNG konvertieren, handelt es sich um eine Instanz der Klasse [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), und dies gilt für alle unterstützten Bildformate. Als letztes Argument übergeben wir die kürzlich vorbereiteten Konvertierungsoptionen.

Jetzt müssen Sie nur noch den Job [ausführen](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/).

Unabhängig davon, ob die Ausführung erfolgreich war oder nicht, ist das erste Ergebnis, das wir sehen, die Terminalausgabe. Wenn der Lauf erfolgreich war, sieht es in etwa so aus:


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

Weitere „Früchte“ der Engine-Arbeit finden wir in dem Ordner, den wir als Ausgabeverzeichnis angegeben haben. Dabei handelt es sich um die Transkriptdatei und, **hier ist sie!**, die Hauptausgabe-PNG-Bilddatei(en).

## Eine alternative Möglichkeit, die Hauptausgabe-PNG-Datei(en) zu schreiben.

Es gibt eine andere Möglichkeit, Bilddaten als Array von Byte-Arrays abzurufen. Jedes Array in der zweiten Dimension repräsentiert Bilddaten für eine separate Seite.

**Alternatives Konvertierungsbeispiel**

Der folgende C#-Ausschnitt zeigt eine weitere Möglichkeit, die PNG-Ausgabe zu erhalten, indem die Bilddaten in einen Speicherstream statt direkt in das Dateisystem geschrieben werden. Dieser Ansatz ist nützlich, wenn Sie die generierten PNG-Bytes im Speicher für die weitere Verarbeitung benötigen, z. B. zum Senden über ein Netzwerk, zum Speichern in einer Datenbank oder für zusätzliche Transformationen vor dem Speichern.

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

Die *"page-n.png"*-Datei(en) werden in jeden von uns angegebenen Pfad geschrieben. Im Gegensatz zu [PDF-Ausgabe](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) duplizieren sie die ausgegebenen PNG-Dateien, die in das Ausgabeverzeichnis geschrieben werden.

## Über Eingabemöglichkeiten

Falls unsere Haupteingabedatei Abhängigkeiten erfordert, beispielsweise Pakete, die nicht im grundlegenden LaTeX-System und den unterstützten Paketen enthalten sind, MÜSSEN wir die Option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) auf die gleiche Weise festlegen, wie wir die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) festlegen. Option und legen Sie die Abhängigkeiten in diesem Verzeichnis ab. Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Falls wir unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, MÜSSEN wir auch das [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) festlegen, indem wir den Pfad zum Speicherort verwenden, an dem diese Dateien gesammelt werden. Wir können die Haupteingabedatei auch irgendwo im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben (oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet). [Hier](/tex/{{lang.url-fragment}}net/aspose-tex-input/) finden Sie die Details zum Eingabeverzeichniskonzept in **Aspose.TeX für .NET** und den bereitgestellten Implementierungen.

Weitere TeX-Joboptionen werden [hier](/tex/{{lang.url-fragment}}net/other-options/) besprochen.

**Sie können sich auch die kostenlose LaTeX-zu-PNG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-png) ansehen, die auf der [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) basiert.**

Im Folgenden diskutieren wir die LaTeX-Konvertierung in andere unterstützte Rasterbildformate, ohne tief ins Detail zu gehen, da es eigentlich keine Details gibt. Der einzige Unterschied besteht im Typ der Eigenschaft [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) in den Konvertierungsoptionen.

## So konvertieren Sie LaTeX in JPG

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToJPEG.cs" >}}

**Sie können sich auch die kostenlose LaTeX-zu-JPG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-jpg) ansehen, die auf [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) basiert.**

## So konvertieren Sie LaTeX in TIFF

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToTIFF.cs" >}}

**Sie können sich auch die kostenlose LaTeX-zu-TIFF-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-tiff) ansehen, die auf [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) basiert.**

## So konvertieren Sie LaTeX in BMP

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToBMP.cs" >}}

**Sie können sich auch die kostenlose LaTeX-zu-BMP-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-bmp) ansehen, die auf [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) basiert.**

## So konvertieren Sie LaTeX in SVG

Und ein weiteres unterstütztes Zielformat ist [**SVG**](https://en.wikipedia.org/wiki/SVG). **Skalierbare Vektorgrafiken (SVG)** ist ein XML-basiertes Vektorbildformat zum Definieren zweidimensionaler Grafiken mit Unterstützung für Interaktivität und Animation.

**SVG**-Bilder werden in einem Vektorgrafikformat definiert und in XML-Textdateien gespeichert. **SVG**-Bilder können somit ohne Qualitätsverlust in der Größe skaliert werden und **SVG**-Dateien können durchsucht, indiziert, mit Skripts versehen und komprimiert werden. Die XML-Textdateien können mit Texteditoren oder Vektorgrafik-Editoren erstellt und bearbeitet werden und werden von den gängigsten Webbrowsern gerendert.

Es gibt die Bibliothek [**Aspose.SVG**](https://products.aspose.com/svg/), die verschiedene Funktionen im Zusammenhang mit **SVG** bereitstellt. Dazu gehören das Erstellen, Laden, Bearbeiten und Konvertieren von **SVG**-Dokumenten.

Die Konvertierung von LaTeX in SVG ist ebenfalls so einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}net/latex-to-image/), außer dass [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) auf eine Instanz der Klasse [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/) gesetzt sein MUSS und das Gerät darauf MUSS in eine Instanz der Klasse [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/) geändert.

{{< gist "aspose-com-gists" "58d1c43acd187f1cde7917fa9a430281" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**Sie können sich auch die kostenlose LaTeX-zu-SVG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-svg) ansehen, die auf der [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) basiert.**
