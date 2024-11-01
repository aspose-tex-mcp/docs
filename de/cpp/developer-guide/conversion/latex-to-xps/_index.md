---
translation: true
template: /templates/_template-cpp.md
title: LaTeX zu XPS | Aspose.TeX für C++
linktitle: LaTeX zu XPS
weight: 12
url: /cpp/latex-to-xps/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für C++ können LaTeX-Dateien in das XPS-Format konvertiert werden.
lastmod: "2024-09-26"
---

{{<section overview>}}

Ein weiteres von **Aspose.TeX** unterstütztes Zielformat ist [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Eine **XPS**-Datei ist eigentlich ein ZIP-Paket, das den paginierten Inhalt eines Dokuments zusammen mit den Metadaten enthält, die für die ordnungsgemäße Anzeige durch bestimmte Viewer (z. B. Windows XPS Viewer) und das Drucken erforderlich sind. Alle Daten in einem Paket werden durch Dateien repräsentiert. Einige davon sind binär und enthalten Ressourcen wie Bilder, Schriftarten und ICC-Profile. Andere sind XML-Dateien in verschiedenen spezifischen Schemata. Zu letzteren zählen Dateien, die die Dokumentdaten selbst enthalten. Dokumentdaten bestehen aus einer Reihe von Dateien – jede Datei enthält Daten für eine einzelne Seite des Dokuments. Solche Dateien bestehen aus einem einzelnen Seitenelement und einem Baum aus untergeordneten Elementen – *Canvas*, *Path* und *Glyphs*. *Canvas* ist ein Gruppierungselement, das andere *Canvases*, *Pfade* und *Glyphen* enthalten kann. Seine Aufgabe besteht darin, das Erscheinungsbild aller untergeordneten Elemente als Gruppe zu steuern. *Path*-Elemente werden zum Definieren von Vektorgrafikpfaden verwendet. Und *Glyphen*-Elemente werden verwendet, um Textinhalte zu definieren. Alle drei Elemente verfügen über Eigenschaften, um verschiedene Aspekte des Erscheinungsbilds zu definieren.

Es gibt die Bibliothek [**Aspose.Page**](https://products.aspose.com/page/), die eine API zum Bearbeiten von XPS-Dokumenten sowie zum Konvertieren dieser in PDF- und Rasterbildformate bereitstellt.

## So konvertieren Sie LaTeX in XPS

Die Konvertierung in XPS ist genauso einfach wie die [Konvertierung in Rasterbildformate](/tex/{{lang.url-fragment}}cpp/latex-to-image/), außer dass wir zusätzlich zu den [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) das Gerät in eine Instanz von [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device) ändern müssen Klasse.

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Eine alternative Möglichkeit, die XPS-Hauptausgabedatei zu schreiben

Es gibt einen weiteren Konstruktor der Klasse [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), mit dem wir die resultierende XPS-Datei auf alternative Weise erhalten können.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.xps"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in XPS format.
            options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<XpsDevice>(xpsStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

Der Effekt ist derselbe, den wir [hier](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file) erhalten.

**Sie können sich auch die kostenlose LaTeX-zu-XPS-Konvertierung [Web-App](https://products.aspose.app/tex/conversion/latex-to-xps) ansehen, die auf der [Aspose.TeX for .NET](https://products.aspose.com/tex/net/)-API basiert. [Hier](https://products.aspose.com/tex/cpp/) ist die C++-Versionsseite.**