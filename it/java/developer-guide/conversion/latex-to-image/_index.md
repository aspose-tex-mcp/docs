---
translation: true
template: /templates/_template-java.md
title: LaTeX all'immagine | Java
linktitle: LaTeX all'immagine
weight: 10
url: /java/latex-to-image/
keywords: LaTeX a PNG, LaTeX PNG, LaTeX all'immagine, Image Latex, LaTeX a JPG, LaTeX JPG, LaTeX a JPEG, LaTeX JPEG, LaTeX a TIFF, LaTeX Tiff, LaTeX a BMP, LaTeX BMP
description: Per convertire i formati di TEX in immagine usando la soluzione API Aspose.TeX per Java Impara questo articolo che descrive come fare questo e gli esempi di codice.
lastmod: "2026-04-21"
---

{{<section overview>}}

**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## Come convertire il LaTeX in PNG

Diamo un'occhiata più da vicino al codice Java che fornisce il modo più semplice per convertire il LaTeX in formato PNG.

Impostare `inputFile` sul percorso completo del file LaTeX, ad esempio `hello-world.ltx`, e `outputDirectory` su una cartella di output esistente. Importare le classi di `com.aspose.tex` e `com.aspose.tex.rendering` utilizzate nel frammento. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza come descritto nella [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione. L'esempio utilizza l'elaborazione non interattiva e chiude le risorse di output. L'esempio PNG utilizza una risoluzione di 300 DPI. Per l'input di una pagina `hello-world.ltx`, i file di output automatici sono `hello-world.png`, `hello-world.jpg`, `hello-world.tif`, `hello-world.bmp` o `hello-world.svg`, a seconda del formato selezionato.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Simplest.java" >}}

Quindi, la prima cosa che dobbiamo fare (a volte non la prima, come scopriremo più avanti) è creare un'istanza della classe [Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). L'unico metodo statico che fa questo è [ConsoleAppoptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), quindi non ci preoccupiamo del significato del suo nome. Il metodo prende l'istanza [ObjectLatex()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) della classe [TexConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), che è esattamente adatto per la conversione di un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object Tex di caricare il formato Object Latex e di essere pronto ad accettare il file LaTeX. Il formato di LaTeX oggetto è in realtà solo il formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), tranne per il fatto che utilizza le primitive specifiche [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per impostare le metriche di pagina.

La prima delle opzioni richieste è [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) che definisce lo spazio o l'area, in cui verrà scritto l'output di Tex. [Qui](/tex/{{lang.url-fragment}}java/aspose-tex-output/) sono i dettagli sul concetto di directory di output in **Aspose.TeX per java**. In questo esempio, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), che ci consente di scrivere l'output nella directory o nella cartella specificata.

La seconda opzione è un'istanza di classe [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) che controllerà la trasformazione del [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato target. Dal momento che stiamo convertendo il LaTeX in PNG, è l'istanza di classe [PNGSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/), che ci consente di specificare la risoluzione delle immagini di output.

Successivamente, dobbiamo creare un'istanza della classe [Texjob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/). Volendo convertire un file LaTeX archiviato nel file system, utilizziamo [questa](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versione del costruttore. Dovremmo specificare l'intero percorso del file. Altrimenti, il motore lo cercherà nella directory corrente (che è definita [qui](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) e molto probabilmente non lo troverà. Tuttavia, possiamo omettere l'estensione se il nostro file ha quello *.tex*. Il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza di classe [dispositivo](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Dal momento che stiamo convertendo il LaTeX in PNG, è una classe [imagevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/) (che è comune a tutti i formati di immagini supportati). Come ultimo argomento, passiamo le opzioni di conversione recentemente preparate.

Tutto quello che dobbiamo fare ora è [correre](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--) il lavoro.

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

Troveremo altri prodotti dell'esecuzione del motore nella cartella che abbiamo specificato come directory di output. Quelli saranno il file trascrizione (.log) e, **voilà!**, il principale file di immagine PNG di output.

## Un modo alternativo per scrivere i file PNG di output principale

Esiste un altro modo per ottenere i dati dell'immagine come un matrice di array di byte, ogni array nella seconda dimensione rappresenta i dati di immagine per una pagina separata.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToPNG-Alternative.java" >}}

L'esempio manuale richiede anche `java.nio.file.Files` e `java.nio.file.Paths`. Salva i dati delle pagine di `ImageDevice.getResult()` come `page-1.png`, `page-2.png` e così via. Impostando `deviceWritesImages(false)`, l'output PNG automatico viene disabilitato e le pagine salvate manualmente non vengono duplicate nella directory di output. Questo comportamento differisce dall'[output PDF tramite flusso](/tex/{{lang.url-fragment}}java/latex-to-pdf/#un-modo-alternativo-per-scrivere-il-file-pdf-di-output-principale), in cui il flusso definisce la destinazione di un singolo documento PDF.

## Sulle opzioni di input

Nel caso in cui il nostro file di input principale richieda dipendenze, ad esempio pacchetti, che non sono inclusi nel sistema di LaTeX di base e nei pacchetti supportati, dobbiamo impostare l'opzione [RecomeinputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) nel modo simile che impostiamo l'opzione [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) e mettere le dipendenze in quella directory. Le dipendenze possono essere organizzate arbitrariamente nelle sottodirectory. Nel caso in cui abbiamo i nostri file da includere lungo il processo di composizione, ad esempio file di grafica esterna, dobbiamo anche impostare [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) utilizzando il percorso per la posizione in cui tali file vengono raccolti. Potremmo anche posizionare il file di input principale da qualche parte all'interno della directory di input e passare il percorso relativo al costruttore di `TeXJob` (o specificare alcun percorso se il file di input principale è nella radice). [Qui](/tex/{{lang.url-fragment}}java/aspose-tex-input/) sono i dettagli sul concetto di directory di input in **Aspose.TeX per java** e hanno fornito implementazioni.

Altre opzioni di lavoro di Tex sono discusse [qui](/tex/{{lang.url-fragment}}java/other-options/).

**È inoltre possibile controllare la conversione gratuita di lattici a PNG [app Web](https://products.aspose.app/tex/conversion/latex-to-png) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**

Di seguito, discutiamo della conversione in LaTeX ad altri formati di immagine raster supportati. Non entreremo nei dettagli solo perché in realtà non ci sono dettagli. L'unica differenza è nel tipo di proprietà [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) nelle opzioni di conversione.

## Come convertire il LaTeX in jpg

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToJPEG.java" >}}

**È inoltre possibile controllare la conversione da lattoce a jpg gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-jpg) basata in base all'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**

## Come convertire il LaTeX in tiff

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToTIFF.java" >}}

**È inoltre possibile controllare la conversione da LaTeX a tiff gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-tiff) basata sulla base dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**

## Come convertire il LaTeX in BMP

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToBMP.java" >}}

**È inoltre possibile controllare la conversione da lattoce a BMP gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-bmp) basata sulla base dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**


## Come convertire il LaTeX in SVG

E ancora un altro formato target supportato è [**svg**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** è un formato di immagine vettoriale basato su XML per definire la grafica bidimensionale, con supporto per l'interattività e l'animazione.

**Le immagini SVG** sono definite in un formato grafico vettoriale e memorizzate in file di testo XML. Ciò significa che le immagini **svg** possono essere ridimensionate senza perdita di qualità e i file **svg** possono essere cercati, indicizzati, script e compressi. I file di testo XML possono essere creati e modificati con editor di testo o redattori grafici vettoriali. Thay sono resi dai browser Web più usati.

Inoltre, esiste la libreria [**Aspose.svg**](https://products.aspose.com/svg/) che ha varie funzionalità basate sul formato **svg**. Questi includono la creazione, il caricamento, la modifica e la conversione di documenti **SVG**.

La conversione in SVG è semplice quanto la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}java/latex-to-image/), tranne che oltre alle [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), dobbiamo cambiare il dispositivo in un'istanza della classe [SVGDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SvgDevice).

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToSVG-Simplest.java" >}}

**È inoltre possibile controllare la conversione da lattici a SVG gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-svg) basata in base a [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**