---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX all'immagine | C++
linktitle: LaTeX all'immagine
weight: 10
url: /cpp/latex-to-image/
keywords: LaTeX a PNG, LaTeX PNG, LaTeX all'immagine, Image Latex, LaTeX a JPG, LaTeX JPG, LaTeX a JPEG, LaTeX JPEG, LaTeX a TIFF, LaTeX Tiff, LaTeX a BMP, LaTeX BMP
description: Per convertire i formati di Tex in immagine usando la soluzione API Aspose.TeX per C ++ Impara questo articolo che descrive come fare questo e gli esempi di codice.
lastmod: 2023-03-23
---

{{<section overview>}}

**Aspose.TeX per C ++** ci consente anche di convertire i file in LaTeX in un numero di altri formati di immagini raster.

## Come convertire il LaTeX in PNG

Diamo uno sguardo dettagliato al codice in C ++ fornendo il modo più semplice per convertire il LaTeX in formato PNG.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Quindi, la prima cosa che dobbiamo fare (beh, a volte non il primo) è creare un'istanza della classe [texoptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). L'unico metodo statico che fa questo è [ConsoleAppoptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), quindi non essere perplessi dal significato del suo nome. Il metodo prende l'istanza [get_objectlatex()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) della classe [TexConfig](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/), che è esattamente adatta per la conversione di un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object Tex di caricare il formato Object Latex e di essere pronto ad accettare il file Latex. Il formato di LaTeX oggetto è in realtà solo il formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), tranne per il fatto che utilizza le primitive specifiche [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per impostare le metriche di pagina.

La prima delle opzioni richieste è [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) che definisce lo spazio o l'area, in cui verrà scritto l'output di Tex. [Qui](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) sono i dettagli sul concetto di directory di output in **Aspose.TeX per c ++**. In questo esempio, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/), che ci consente di scrivere l'output alla directory o alla cartella specificata.

La seconda opzione è un'istanza di classe [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/) che controllerà la trasformazione del [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato target. Dal momento che stiamo convertendo il LaTeX in PNG, è l'istanza di classe [pngsaveoptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), che ci consente di specificare la risoluzione delle immagini di output.

Successivamente, dobbiamo creare un'istanza della classe [Texjob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Volendo convertire un file LaTeX archiviato nel file system, utilizziamo [questa](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) versione del costruttore. Dobbiamo specificare l'intero percorso del file. Altrimenti, il motore lo cercherà nella directory corrente (che è [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) e molto probabilmente non lo troverà. Tuttavia, possiamo omettere l'estensione se il nostro file ha quello *.tex*. Il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza di classe [dispositivo](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Dal momento che stiamo convertendo il LaTeX in PNG, è una classe [imagevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) (che è comune a tutti i formati di immagini supportati). Come ultimo argomento, passiamo le opzioni di conversione recentemente preparate.

Tutto ciò che resta da fare ora è [correre](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb) il lavoro.

Indipendentemente dal fatto che la corsa abbia avuto successo o meno, il primo risultato che vedremo sarà l'output del terminale. In caso di successo, assomiglia a questo:

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

Troveremo altri "frutti" del lavoro del motore nella cartella che abbiamo specificato come directory di output. Quelli saranno il file di trascrizione e, **eccolo!**, i principali file di immagine PNG di output.

## Un modo alternativo per scrivere i file PNG di output principale

Esiste un altro modo per ottenere i dati dell'immagine come un matrice di array di byte, ogni array nella seconda dimensione rappresenta i dati di immagine per una pagina separata.

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
I file *"Page-n.png"* saranno scritti su qualsiasi percorso che specificiamo. A differenza di [Output PDF](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), duplicheranno i file PNG di output scritti nella directory di output.

## Sulle opzioni di input

Nel caso in cui il nostro file di input principale richieda dipendenze, ad esempio pacchetti, che non sono inclusi nel sistema di LaTeX di base e nei pacchetti supportati, dobbiamo impostare l'opzione [RecomeinputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) nel modo simile che impostiamo l'opzione [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) e mettere le dipendenze in quella directory. Le dipendenze possono essere organizzate arbitrariamente nelle sottodirectory. Nel caso in cui abbiamo i nostri file da includere lungo il processo di composizione, ad esempio file di grafica esterna, dobbiamo anche impostare [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) utilizzando il percorso per la posizione in cui tali file vengono raccolti. Potremmo anche posizionare il file di input principale da qualche parte all'interno della directory di input e specificare il percorso relativo nel metodo `run()` (o specificare alcun percorso se il file di input principale è nella radice). [Qui](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) sono i dettagli sul concetto di directory di input in **Aspose.TeX per c ++** e hanno fornito implementazioni.

Altre opzioni di lavoro di Tex sono discusse [qui](/tex/{{lang.url-fragment}}cpp/other-options/).

**È inoltre possibile controllare la conversione gratuita di lattici a PNG [app Web](https://products.aspose.app/tex/conversion/latex-to-png) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/cpp/) è la pagina della versione C ++.**

Di seguito, discutiamo della conversione in LaTeX ad altri formati di immagine raster supportati. Non entreremo nei dettagli solo perché in realtà non ci sono dettagli. L'unica differenza è nel tipo di proprietà [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) nelle opzioni di conversione.

## Come convertire il LaTeX in jpeg

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**È inoltre possibile controllare la conversione gratuita di lattine a jpeg [app Web](https://products.aspose.app/tex/conversion/latex-to-jpg) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/cpp/) è la pagina della versione C ++.**

## Come convertire il LaTeX in tiff

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**È inoltre possibile controllare la conversione da LaTeX a tiff gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-tiff) basata sulla base dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/cpp/) è la pagina della versione C ++.**

## Come convertire il LaTeX in BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**È inoltre possibile controllare la conversione da lattoce a BMP gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-bmp) basata sulla base dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/cpp/) è la pagina della versione C ++.**