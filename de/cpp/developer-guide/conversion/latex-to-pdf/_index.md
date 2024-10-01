---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX zu PDF | Aspose.TeX API-Lösung für C++
linktitle: LaTeX in PDF
weight: 11
url: /cpp/latex-to-pdf/
keywords: Latex in PDF, Latex PDF, Latex in PDF konvertieren
description: Um TeX mit der Aspose.TeX-API-Lösung für C++ in PDF zu konvertieren, lesen Sie diesen Artikel, in dem die Vorgehensweise und die Codebeispiele beschrieben werden.
lastmod: "2024-09-26"
---

{{<section overview>}}

## So konvertieren Sie LaTeX in PDF

Werfen wir einen detaillierten Blick auf den Code in C++, der die einfachste Möglichkeit zur Konvertierung von LaTeX in das PDF-Format bietet.

{{<app/converter
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf">}}
{{</app/converter>}}

Das erste, was wir also tun müssen (na ja, manchmal nicht das allererste), ist, eine Instanz der Klasse [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions) zu erstellen. Die einzige statische Methode, die dies tut, ist [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions). Lassen Sie uns also nicht über die Bedeutung ihres Namens rätseln. Die Methode benötigt eine [Instanz](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) der Klasse [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), die genau zum Konvertieren einer [LaTeX-Datei](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) geeignet ist. Diese Konfiguration weist die Object TeX-Engine an, das Object LaTeX-Format zu laden und bereit zu sein, die LaTeX-Datei zu akzeptieren. Das Object LaTeX-Format ist eigentlich nur das [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/)-Format, außer dass es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)-spezifische Grundelemente verwendet, um die Seitenmetriken einzurichten.

Die erste der erforderlichen Optionen ist [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), die den Raum oder Bereich definiert, in den die TeX-Ausgabe geschrieben wird. [Hier](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) finden Sie die Details zum Ausgabeverzeichniskonzept in **Aspose.TeX für C++**. In diesem Beispiel verwenden wir die Klasse [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), mit der wir die Ausgabe in das angegebene Verzeichnis oder den angegebenen Ordner schreiben können.

Die zweite Option ist eine Klasseninstanz [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), die die Transformation des [Objektmodells](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) in das Zielformat steuert. Da wir LaTeX in PDF konvertieren, handelt es sich um die Klasseninstanz [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Dann müssen wir eine Instanz der Klasse [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) erstellen. Wenn wir eine im Dateisystem gespeicherte LaTeX-Datei konvertieren möchten, verwenden wir [diese](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) Version des Konstruktors. Wir müssen den vollständigen Pfad zur Datei angeben. Andernfalls sucht die Engine im aktuellen Verzeichnis ([CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) danach und wird es höchstwahrscheinlich nicht finden. Dennoch können wir die Erweiterung weglassen, wenn unsere Datei die Erweiterung *.tex* hat. Die Engine wird es automatisch anhängen. Das zweite Argument des Konstruktors ist eine Klasseninstanz [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Da wir LaTeX in PDF konvertieren, handelt es sich um eine [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)-Klasseninstanz. Als letztes Argument übergeben wir die kürzlich vorbereiteten Konvertierungsoptionen.

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Weitere „Früchte“ der Engine-Arbeit finden wir in dem Ordner, den wir als Ausgabeverzeichnis angegeben haben. Dabei handelt es sich um die Transkriptdatei und, **hier ist sie!**, die Hauptausgabe-PDF-Datei.

## Eine alternative Möglichkeit, die Hauptausgabe-PDF-Datei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), mit dem wir die resultierende PDF-Datei auf alternative Weise erhalten können.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> pdfStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.pdf"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ pdfsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in PDF format.
            options->set_SaveOptions(System::MakeObject<PdfSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<PdfDevice>(pdfStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

Die Datei *any-name.pdf* im angegebenen Verzeichnis ist unsere Hauptausgabe-PDF-Datei. Gleichzeitig finden wir im Gegensatz zu [Bildausgabe](/tex/{{lang.url-fragment}}cpp/latex-to-png/#an-alternative-way-to-write-main-output-png-files) keine PDF-Dateien in dem durch die Konvertierungsoptionen definierten Ausgabeverzeichnis. Ausnahme: *any-name.pdf* befindet sich (durch seinen Pfad) im selben Dateisystemverzeichnis, das der Option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) mit [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory) zugewiesen ist.

## Über Eingabemöglichkeiten

Falls unsere Haupteingabedatei Abhängigkeiten erfordert, beispielsweise Pakete, die nicht im grundlegenden LaTeX-System und den unterstützten Paketen enthalten sind, MÜSSEN wir die Option [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) auf die gleiche Weise festlegen, wie wir die Option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) festlegen. Option und legen Sie die Abhängigkeiten in diesem Verzeichnis ab. Abhängigkeiten können beliebig in Unterverzeichnissen organisiert werden. Falls wir unsere eigenen Dateien in den Schriftsatzprozess einbeziehen möchten, beispielsweise externe Grafikdateien, MÜSSEN wir auch das [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) festlegen, indem wir den Pfad zum Speicherort verwenden, an dem diese Dateien gesammelt werden. Wir können die Haupteingabedatei auch irgendwo im Eingabeverzeichnis platzieren und den relativen Pfad in der Methode „run()“ angeben (oder überhaupt keinen Pfad angeben, wenn sich die Haupteingabedatei im Stammverzeichnis befindet). [Hier](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) finden Sie die Details zum Eingabeverzeichniskonzept in **Aspose.TeX für C++** und den bereitgestellten Implementierungen.

Weitere TeX-Joboptionen werden [hier](/tex/{{lang.url-fragment}}cpp/other-options/) besprochen.

**Sie können sich auch die kostenlose LaTeX-zu-PDF-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-pdf) ansehen, die auf der [Aspose.TeX for C++ API](https://products.aspose.com/tex/cpp/) basiert.**