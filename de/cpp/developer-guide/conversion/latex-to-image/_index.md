---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX zum Bild | C++
linktitle: LaTeX zum Bild
weight: 10
url: /cpp/latex-to-image/
keywords: Latex zu PNG, Latex PNG, Latex zu Bild, Latex Bild, Latex zu JPG, Latex JPG, Latex zu JPEG, Latex JPEG, Latex zu TIFF, Latex TIFF, Latex zu BMP, Latex BMP
description: Um TeX mit der Aspose.TeX-Lösung für C++ in Bildformate zu konvertieren, lesen Sie diesen Artikel, der die Vorgehensweise und die Codebeispiele beschreibt.
lastmod: 23.03.2023
---

{{<section overview>}}

**Aspose.TeX für C++** ermöglicht uns auch die Konvertierung von LaTeX-Dateien in eine Reihe anderer Rasterbildformate.

## So konvertieren Sie LaTeX in PNG

Werfen wir einen detaillierten Blick auf den Code in C++, der die einfachste Möglichkeit bietet, LaTeX in das PNG-Format zu konvertieren.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Das erste, was wir also tun müssen (na ja, manchmal nicht das allererste), ist, eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions) zu erstellen. Die einzige statische Methode, die dies tut, ist [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions). Lassen Sie uns also nicht über die Bedeutung ihres Namens rätseln. Die Methode verwendet die [get_ObjectLaTeX()-Instanz](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) der Klasse [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), die genau zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) geeignet ist. Diese Konfiguration weist die Object TeX-Engine an, das Object LaTeX-Format zu laden und bereit zu sein, die LaTeX-Datei zu akzeptieren. Das Object LaTeX-Format ist eigentlich nur das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, außer dass es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente verwendet, um die Seitenmetriken einzurichten.

Die erste der erforderlichen Optionen ist [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), die den Raum oder Bereich definiert, in den die TeX-Ausgabe geschrieben wird. [Hier](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) finden Sie die Details zum Ausgabeverzeichniskonzept in **Aspose.TeX für C++**. In diesem Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), mit der wir die Ausgabe in das angegebene Verzeichnis oder den angegebenen Ordner schreiben können.

Die zweite Option ist eine Klasseninstanz [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/), die die Transformation des [Objektmodells](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das Zielformat steuert. Da wir LaTeX in PNG konvertieren, ist es die Klasseninstanz [PngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), mit der wir die Auflösung der Ausgabebilder festlegen können.

Als nächstes müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) erstellen. Wenn wir eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) Version des Konstruktors. Wir müssen den vollständigen Pfad zur Datei angeben. Andernfalls sucht die Engine im aktuellen Verzeichnis ([CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) danach und wird es höchstwahrscheinlich nicht finden. Dennoch können wir die Erweiterung weglassen, wenn unsere Datei die Erweiterung *.tex* hat. Die Engine wird es automatisch anhängen. Das zweite Argument des Konstruktors ist eine Klasseninstanz [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Da wir LaTeX in PNG konvertieren, handelt es sich um eine Instanz der Klasse [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device), die allen unterstützten Bildformaten gemeinsam ist. Als letztes Argument übergeben wir die kürzlich vorbereiteten Konvertierungsoptionen.

Jetzt müssen Sie nur noch den Job [ausführen](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb).

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

Weitere „Früchte“ der Engine-Arbeit finden wir in dem Ordner, den wir als Ausgabeverzeichnis angegeben haben. Dabei handelt es sich um die Transkriptdatei und, **hier ist sie!**, die Hauptausgabe-PNG-Bilddatei(en).

## Eine alternative Möglichkeit, die Hauptausgabe-PNG-Datei(en) zu schreiben.

Es gibt eine andere Möglichkeit, Bilddaten als Array von Byte-Arrays abzurufen. Jedes Array in der zweiten Dimension repräsentiert Bilddaten für eine separate Seite.

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```

Die *"page-n.png"*-Datei(en) werden in jeden von uns angegebenen Pfad geschrieben. Im Gegensatz zu [PDF-Ausgabe](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) duplizieren sie die ausgegebenen PNG-Dateien, die in das Ausgabeverzeichnis geschrieben werden.

## Über Eingabemöglichkeiten

Falls unsere Haupteingabedatei Abhängigkeiten erfordert, beispielsweise Pakete, die nicht im grundlegenden LaTeX-System und den unterstützten Paketen enthalten sind, MÜSSEN wir die Option [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) auf die gleiche Weise festlegen, wie wir die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) festlegen. Option und legen Sie die Abhängigkeiten in diesem Verzeichnis ab. Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Falls wir unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, MÜSSEN wir auch das [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) festlegen, indem wir den Pfad zum Speicherort verwenden, an dem diese Dateien gesammelt werden. Wir können die Haupteingabedatei auch irgendwo im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben (oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet). [Hier](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) finden Sie die Details zum Eingabeverzeichniskonzept in **Aspose.TeX für C++** und den bereitgestellten Implementierungen.

Weitere TeX-Joboptionen werden [hier](/tex/{{lang.url-fragment}}cpp/other-options/) besprochen.

**Sie können sich auch die kostenlose LaTeX-zu-PNG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-png) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/cpp/) ist die C++-Versionsseite.**

Im Folgenden besprechen wir die LaTeX-Konvertierung in andere unterstützte Rasterbildformate. Wir gehen nicht auf Details ein, nur weil es eigentlich keine Details gibt. Der einzige Unterschied besteht im Typ der Eigenschaft [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) in den Konvertierungsoptionen.

## So konvertieren Sie LaTeX in JPEG

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**Sie können sich auch die kostenlose LaTeX-zu-JPEG-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-jpg) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/cpp/) ist die C++-Versionsseite.**

## So konvertieren Sie LaTeX in TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**Sie können sich auch die kostenlose LaTeX-zu-TIFF-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-tiff) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/cpp/) ist die C++-Versionsseite.**

## So konvertieren Sie LaTeX in BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**Sie können sich auch die kostenlose LaTeX-zu-BMP-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-bmp) ansehen, die auf der API [Aspose.TeX für .NET](https://products.aspose.com/tex/net/) basiert. [Hier](https://products.aspose.com/tex/cpp/) ist die C++-Versionsseite.**