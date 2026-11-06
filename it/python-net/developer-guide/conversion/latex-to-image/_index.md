---
translation: true
template: /templates/_template-python-net.md
title: LaTeX all'immagine | Python tramite .NET
linktitle: LaTeX all'immagine
weight: 10
url: /python-net/latex-to-image/
keywords: LaTeX a PNG, LaTeX PNG, LaTeX all'immagine, Image Latex, LaTeX a JPG, LaTeX JPG, LaTeX a JPEG, LaTeX JPEG, LaTeX a TIFF, LaTeX Tiff, LaTeX a BMP, LaTeX BMP
description: Per convertire i formati di TEX in immagine usando la soluzione API Aspose.TeX per Python Impara questo articolo per vedere che descrive come fare questo e gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

**Aspose.TeX per Python** ci fornisce la capacità di convertire i file in LaTeX in vari formati di immagini raster.

## Convertire il LaTeX in PNG

Ora, esaminiamo il codice Python che offre l'approccio più semplice alla conversione del formato di LaTeX in PNG in profondità.

Impostare `ASPOSE_TEX_INPUT_FILE` sul file LaTeX e `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output, oppure modificare i percorsi nell’esempio. I valori predefiniti sono `hello-world.ltx` e `output`. Applicare prima una licenza. I file di input aggiuntivi vengono cercati accanto al documento principale; l’elaborazione non è interattiva. [Licenze](/tex/it/python-net/licensing/)

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Per cominciare, dobbiamo creare un'istanza della classe [texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) usando il metodo [Console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig)  . Non preoccuparti del nome, è solo il metodo statico che crea l'istanza. Questo metodo prende l'istanza [Object_Latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) della classe [TexConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), che è perfetta per convertire un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione imposta il motore Object Tex per caricare il formato Object Latex ed essere pronto a elaborare il file Latex. Il formato di LaTeX oggetto è essenzialmente lo stesso del [formato latex](/tex/{{lang.url-fragment}}net/what-is-latex/), ma utilizza [oggetto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) primitive specifiche per definire le metriche di pagina.

La prima delle opzioni necessarie è [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), che specifica la posizione in cui verrà salvato l'output Tex. Se interessato, puoi conoscere ulteriori informazioni sul concetto di [directory di output in **Aspose.TeX per python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). In questo esempio particolare, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) per scrivere l'output su una directory o una cartella specifica.

La seconda opzione è un'istanza della classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), che è responsabile della gestione della conversione dal [modello a oggetti](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato desiderato. In questo caso, dal momento che stiamo convertendo il LaTeX in PNG, utilizziamo l'istanza di classe [PNGSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), che ci consente di specificare la risoluzione delle immagini di output.

Successivamente, creiamo un'istanza della classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). In questo caso, dal momento che vogliamo convertire un file LaTeX memorizzato nel file system, utilizziamo [questa versione del costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions)  . Dobbiamo fornire l'intero percorso al file, altrimenti il ​​motore lo cercherà nella directory corrente (che è la directory di lavoro dello script) e potrebbe non trovarlo. Tuttavia, l'estensione `.tex` può essere omessa poiché il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza della classe [dispositivo](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Dal momento che stiamo convertendo il LaTeX in PNG, è un'istanza di classe [imagevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), che è comune a tutti i formati di immagine supportati. Infine, passiamo le opzioni di conversione preparate come ultimo argomento.

Ora, tutto ciò che rimane è [correre](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) il lavoro.

L’esempio acquisisce l’output del terminale in `OutputMemoryTerminal`. La directory di output contiene anche un registro `.log`. Una conversione riuscita produce un registro simile al seguente; le informazioni sulla versione possono variare:

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

I risultati del lavoro del motore sono disponibili nella directory di output che abbiamo specificato. Ciò includerà il file di trascrizione e, soprattutto, i principali file di immagine PNG di output.

## Un modo alternativo per scrivere i file PNG di output principale

Esiste un metodo alternativo per ottenere i dati dell'immagine come array di array di byte, in cui ciascun array nella seconda dimensione rappresenta i dati dell'immagine per una pagina separata.

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

L’esempio imposta `device_writes_images = False` su `PngSaveOptions` prima di assegnarlo a `options.save_options`. Salva i byte delle pagine restituite come `page-1.png`, `page-2.png` e così via. Il dispositivo non crea quindi file PNG duplicati.

## Per quanto riguarda le opzioni di input

Se il nostro file di input principale richiede dipendenze, come pacchetti che non sono inclusi nel sistema di base in LaTeX o pacchetti supportati, è necessario impostare l'opzione [Recome_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) in modo simile a come impostiamo l'opzione * output_working_directory * e posizionare le dipendenze in quella directory. Le dipendenze possono essere organizzate nelle sottodirectory se necessario. Se abbiamo i nostri file da includere nel processo di composizione, come i file grafici esterni, dobbiamo anche impostare [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) nella posizione in cui tali file sono archiviati. Possiamo anche posizionare il file di input principale all'interno della directory di input e specificare il percorso relativo al costruttore `TeXJob` o specificare alcun percorso se il file di input principale è nella directory di root. Ci sono anche maggiori dettagli sul [concetto di directory di input](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) in **aspose.tex** e le implementazioni fornite descritte.

Impara anche le [altre opzioni di lavoro di Tex qui](/tex/{{lang.url-fragment}}python-net/other-options/).

**Puoi anche esplorare la conversione gratuita [Web App](https://products.aspose.app/tex/conversion/latex-to-png) per la conversione da lattoce a PNG, che viene sviluppata utilizzando [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

Di seguito, spiegheremo brevemente la conversione del LaTeX ad altri formati di immagini raster supportati, senza immergersi in troppi dettagli in quanto non vi sono differenze significative. L'unica variazione risiede nel tipo di proprietà [Save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) nelle opzioni di conversione.

## Convertire il LaTeX in jpg

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**Puoi anche esplorare la conversione gratuita [app Web per LaTeX a jpg](https://products.aspose.app/tex/conversion/latex-to-jpg), che viene sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**

## Convertire il LaTeX in TIFF

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Puoi anche esplorare la conversione gratuita [app Web per LaTeX-tiff](https://products.aspose.app/tex/conversion/latex-to-tiff), che viene sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**

## Convertire il LaTeX in BMP

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Puoi anche esplorare la conversione gratuita [app Web per LaTeX-a-BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), che viene sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**


## Convertire il LaTeX in SVG

Un altro formato target supportato è [**svg**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** è un formato di immagine vettoriale basato su XML che viene utilizzato per definire la grafica bidimensionale. Supporta l'interattività e l'animazione.

**Le immagini SVG** sono archiviate in file di testo XML e definite in un formato grafico vettoriale. Ciò significa che le immagini **svg** possono essere ridimensionate senza perdere la qualità e i file **svg** stessi possono essere cercati, indicizzati, scritti e compressi. I file di testo XML possono essere creati e modificati utilizzando editor di testo o redattori di grafica vettoriale e possono essere resi dai browser Web più comunemente usati.

L'API [**Aspose.svg**](https://products.aspose.com/svg/) offre una gamma di funzionalità per lavorare con **svg**, come la creazione, il caricamento, la modifica e la conversione di documenti **svg**.

La conversione del LaTeX in SVG è semplice quanto [la conversione in formati di immagini raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/), con l'unica differenza è che i [Save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) devono essere impostati su un'istanza della classe [SVGSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) e il dispositivo deve essere modificato in un'istanza della classe [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "3616f5e300517031e6a4ae4158e24776" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Puoi anche esplorare la conversione gratuita [app Web per la latex-a-SVG](https://products.aspose.app/tex/conversion/latex-to-svg), che viene sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**