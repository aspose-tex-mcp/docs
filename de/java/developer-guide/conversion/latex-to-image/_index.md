---
translation: true
template: /templates/_template-java.md
title: LaTeX zum Bild | Java
linktitle: LaTeX zum Bild
weight: 10
url: /java/latex-to-image/
keywords: Latex zu PNG, Latex PNG, Latex zu Bild, Latex Bild, Latex zu JPG, Latex JPG, Latex zu JPEG, Latex JPEG, Latex zu TIFF, Latex TIFF, Latex zu BMP, Latex BMP
description: Um TeX mit der Aspose.TeX für Java in Bildformate zu konvertieren, lesen Sie diesen Artikel, der die Vorgehensweise und die Codebeispiele beschreibt.
lastmod: "2026-04-21"
---

{{<section overview>}}
**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## So konvertieren Sie LaTeX in PNG

Schauen wir uns den Java-Code genauer an, der die einfachste Möglichkeit bietet, LaTeX in das PNG-Format zu konvertieren.

Setzen Sie `inputFile` auf den vollständigen Pfad Ihrer LaTeX-Datei, beispielsweise `hello-world.ltx`, und `outputDirectory` auf einen vorhandenen Ausgabeordner. Importieren Sie die im Beispiel verwendeten Klassen aus `com.aspose.tex` und `com.aspose.tex.rendering`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie eine Lizenz gemäß der [Lizenzierungsanleitung](/tex/{{lang.url-fragment}}java/licensing/) an, um Evaluierungseinschränkungen zu vermeiden. Das Beispiel verwendet einen nichtinteraktiven Modus und schließt seine Ausgaberessourcen. Das PNG-Beispiel verwendet 300 DPI. Für die einseitige Eingabe `hello-world.ltx` heißen die automatischen Ausgabedateien je nach Format `hello-world.png`, `hello-world.jpg`, `hello-world.tif`, `hello-world.bmp` oder `hello-world.svg`.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

Das erste, was wir also tun müssen (manchmal nicht das allererste, wie wir später herausfinden werden), ist, eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/) zu erstellen. Die einzige statische Methode, die dies tut, ist [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), also kümmern wir uns nicht um die Bedeutung ihres Namens. Die Methode verwendet die [objectLaTeX()-Instanz](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) der Klasse [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), die genau zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) geeignet ist. Diese Konfiguration weist die Object-TeX-Engine an, das Object-LaTeX-Format zu laden und bereit zu sein, die LaTeX-Datei zu akzeptieren. Das Object LaTeX-Format ist eigentlich nur das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, außer dass es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente verwendet, um die Seitenmetriken einzurichten.

Die erste der erforderlichen Optionen ist [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--), die den Raum oder Bereich definiert, in den die TeX-Ausgabe geschrieben wird. [Hier](/tex/{{lang.url-fragment}}java/aspose-tex-output/) finden Sie die Details zum Ausgabeverzeichniskonzept in **Aspose.TeX für Java**. In diesem Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), die es uns ermöglicht, die Ausgabe in das angegebene Verzeichnis oder den angegebenen Ordner zu schreiben.

Die zweite Option ist eine Klasseninstanz [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions), die die Transformation des [Objektmodells](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das Zielformat steuert. Da wir LaTeX in PNG konvertieren, ist es die Klasseninstanz [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/), die es uns ermöglicht, die Auflösung der Ausgabebilder anzugeben.

Als nächstes müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/) erstellen. Wenn wir eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) Version des Konstruktors. Wir sollten den vollständigen Pfad zur Datei angeben. Andernfalls sucht die Engine im aktuellen Verzeichnis (das [hier](https://docs.oracle.com/javase/7/docs/api/java/io/File.html) definiert ist) danach und wird es höchstwahrscheinlich nicht finden. Dennoch können wir die Erweiterung weglassen, wenn unsere Datei die Erweiterung *.tex* hat. Die Engine wird es automatisch anhängen. Das zweite Argument des Konstruktors ist eine Klasseninstanz [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Da wir LaTeX in PNG konvertieren, handelt es sich um eine Instanz der Klasse [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/), die allen unterstützten Bildformaten gemeinsam ist. Als letztes Argument übergeben wir die kürzlich vorbereiteten Konvertierungsoptionen.

Jetzt müssen wir nur noch den Job [ausführen](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--).

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Weitere Produkte des Motorlaufs finden wir in dem Ordner, den wir als Ausgabeverzeichnis angegeben haben. Dabei handelt es sich um die Transkriptdatei (.log) und, **Voila!**, die Hauptausgabe-PNG-Bilddatei(en).

## Eine alternative Möglichkeit, die Hauptausgabe-PNG-Datei(en) zu schreiben.

Es gibt eine andere Möglichkeit, Bilddaten als Array von Byte-Arrays abzurufen. Jedes Array in der zweiten Dimension repräsentiert Bilddaten für eine separate Seite.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

Das manuelle Beispiel benötigt auch `java.nio.file.Files` und `java.nio.file.Paths`. Es speichert Seitendaten aus `ImageDevice.getResult()` als `page-1.png`, `page-2.png` usw. Durch `deviceWritesImages(false)` ist die automatische PNG-Ausgabe deaktiviert; die manuell gespeicherten Seiten werden nicht im Ausgabeverzeichnis dupliziert. Dies unterscheidet sich von der [PDF-Stream-Ausgabe](/tex/{{lang.url-fragment}}java/latex-to-pdf/#eine-alternative-möglichkeit-die-hauptausgabe-pdf-datei-zu-schreiben), bei der der Stream das Ziel eines einzelnen PDF-Dokuments bestimmt.

## Über Eingabemöglichkeiten

Falls unsere Haupteingabedatei Abhängigkeiten erfordert, beispielsweise Pakete, die nicht im grundlegenden LaTeX-System und den unterstützten Paketen enthalten sind, MÜSSEN wir die Option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) auf die gleiche Weise festlegen, wie wir die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) festlegen. Option und legen Sie die Abhängigkeiten in diesem Verzeichnis ab. Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Falls wir unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, MÜSSEN wir auch das [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) festlegen, indem wir den Pfad zum Speicherort verwenden, an dem diese Dateien gesammelt werden. Wir können die Haupteingabedatei auch irgendwo im Eingabeverzeichnis platzieren und den relativen Pfad an den `TeXJob`-Konstruktor übergeben (oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet). [Hier](/tex/{{lang.url-fragment}}java/aspose-tex-input/) finden Sie die Details zum Eingabeverzeichniskonzept in **Aspose.TeX für Java** und den bereitgestellten Implementierungen.

Weitere TeX-Joboptionen werden [hier](/tex/{{lang.url-fragment}}java/other-options/) besprochen.

**Sie können sich auch die kostenlose LaTeX-zu-PNG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-png) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**

Im Folgenden besprechen wir die LaTeX-Konvertierung in andere unterstützte Rasterbildformate. Wir gehen nicht auf Details ein, nur weil es eigentlich keine Details gibt. Der einzige Unterschied besteht im Typ der Eigenschaft [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) in den Konvertierungsoptionen.

## So konvertieren Sie LaTeX in JPG

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToJPEG.java" >}}

**Sie können sich auch die kostenlose LaTeX-zu-JPG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-jpg) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**

## So konvertieren Sie LaTeX in TIFF

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToTIFF.java" >}}

**Sie können sich auch die kostenlose LaTeX-zu-TIFF-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-tiff) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**

## So konvertieren Sie LaTeX in BMP

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToBMP.java" >}}

**Sie können sich auch die kostenlose LaTeX-zu-BMP-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-bmp) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**


## So konvertieren Sie LaTeX in SVG

Und ein weiteres unterstütztes Zielformat ist [**SVG**](https://en.wikipedia.org/wiki/SVG). **Skalierbare Vektorgrafiken (SVG)** ist ein XML-basiertes Vektorbildformat zum Definieren zweidimensionaler Grafiken mit Unterstützung für Interaktivität und Animation.

**SVG**-Bilder werden in einem Vektorgrafikformat definiert und in XML-Textdateien gespeichert. Dies bedeutet, dass **SVG**-Bilder ohne Qualitätsverlust in der Größe skaliert werden können und **SVG**-Dateien durchsucht, indiziert, mit Skripts versehen und komprimiert werden können. Die XML-Textdateien können mit Texteditoren oder Vektorgrafik-Editoren erstellt und bearbeitet werden. Sie werden von den am häufigsten verwendeten Webbrowsern gerendert.

Außerdem gibt es die Bibliothek [**Aspose.SVG**](https://products.aspose.com/svg/), die verschiedene Funktionen basierend auf dem **SVG**-Format bietet. Dazu gehören das Erstellen, Laden, Bearbeiten und Konvertieren von **SVG**-Dokumenten.

Die Konvertierung in SVG ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}java/latex-to-image/), außer dass wir zusätzlich zu den [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) das Gerät in eine Instanz von [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice)Klasse ändern müssen.

{{< gist "aspose-com-gists" "9d6b3df9df43d8caf00a0d519c504cf5" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**Sie können sich auch die kostenlose LaTeX-zu-SVG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-svg) ansehen, die auf [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/java/) ist die Java-Versionsseite.**