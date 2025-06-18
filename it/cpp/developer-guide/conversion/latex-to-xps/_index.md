---
translation: true
template: /templates/_template-cpp.md
title: LaTeX a XPS | Aspose.TeX per C ++
linktitle: LaTeX a XPS
weight: 12
url: /cpp/latex-to-xps/
description: Funzionalità di conversione della soluzione API ASUP.TEX per C ++ consente di convertire i file in LaTeX in formato XPS. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

Un altro formato target supportato da **aspose.tex** è [**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un file **XPS** è in realtà un pacchetto zip che contiene contenuto paginato di un documento, insieme ai metadati richiesti per la visualizzazione corretta da specifici telespettatori (come Windows XPS Viewer) e la stampa. Tutti i dati in un pacchetto sono rappresentati dai file. Alcuni di essi sono binari e contengono risorse come immagini, caratteri e profili ICC. Altri sono file XML in vari schemi specifici. Quest'ultimo include file che contengono i dati del documento stesso. I dati del documento sono costituiti da un set di file: ogni file contiene dati per una singola pagina del documento. Tali file sono costituiti da un singolo elemento di pagina e un albero di elementi figlio - *tela*, *percorso* e *glicfi*. *Canvas*è un elemento di raggruppamento che può contenere altre*tele*,*percorsi* e *glicfi*. La sua missione è quella di controllare l'aspetto di tutti gli elementi infantili come gruppo. *Path* Gli elementi vengono utilizzati per definire percorsi grafici vettoriali. E gli elementi *glifi* vengono utilizzati per definire il contenuto testuale. Tutti e tre gli elementi hanno proprietà per definire vari aspetti dell'apparenza.

Esiste la libreria [**Aspose.Page**](https://products.aspose.com/page/) che fornisce un'API per manipolare i documenti XPS, oltre a convertirli in formati di immagini PDF e raster.

## Come convertire il LaTeX in XPS

La conversione in XPS è altrettanto semplice come la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}cpp/latex-to-image/), tranne che oltre ai [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions), dobbiamo cambiare il dispositivo in un'istanza della classe [XPSDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device).

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Un modo alternativo per scrivere il file XPS di output principale

C'è un altro costruttore della classe [XPSDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), che ci consente di ottenere il file XPS risultante in modo alternativo.

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

L'effetto è lo stesso che otteniamo [qui](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**È inoltre possibile controllare la conversione da lattoce a XPS gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-xps) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/cpp/) è la pagina della versione C ++.**