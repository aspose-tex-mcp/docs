---
translation: true
template: /templates/_template-net.md
title: LaTeX all'immagine | .NET
linktitle: LaTeX all'immagine
weight: 10
url: /net/latex-to-image/
keywords: LaTeX a PNG, LaTeX PNG, LaTeX all'immagine, Image Latex, LaTeX a JPG, LaTeX JPG, LaTeX a JPEG, LaTeX JPEG, LaTeX a TIFF, LaTeX Tiff, LaTeX a BMP, LaTeX BMP
description: Per convertire i formati di TEX in immagine usando la soluzione API Aspose.TeX per .NET Impara questo articolo per vedere che descrive come fare questo e gli esempi di codice.
lastmod: "2026-11-04"
---

{{<section overview>}}

**Aspose.TeX per .NET** ci consente di convertire i file in LaTeX in un numero di formati di immagini raster.

## Come convertire il LaTeX in PNG

Diamo uno sguardo dettagliato al codice in C# fornendo il modo più semplice per convertire il LaTeX in formato PNG.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Quindi, la prima cosa che dobbiamo fare (beh, a volte non il primo) è creare un'istanza della classe [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/). L'unico metodo statico che fa questo è [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/consoleappoptions/), quindi non essere perplessi dal significato del suo nome. Il metodo prende l'istanza [ObjectLatex](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) della classe [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), che è esattamente adatta per la conversione di un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object Tex di caricare il formato Object Latex e di essere pronto ad accettare il file Latex. Il formato di LaTeX oggetto è in realtà solo il formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), tranne per il fatto che utilizza le primitive specifiche [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per impostare le metriche di pagina.

La prima delle opzioni richieste è [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/outputworkingdirectory/) che definisce lo spazio o l'area, in cui verrà scritto l'output di Tex. [Qui](/tex/{{lang.url-fragment}}net/aspose-tex-output/) sono i dettagli sul concetto di directory di output in **Aspose.TeX per .net**. In questo esempio, utilizziamo la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), che ci consente di scrivere l'output alla directory o alla cartella specificata.

La seconda opzione è un'istanza di classe [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) che controllerà la trasformazione del [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato target. Dal momento che stiamo convertendo il LaTeX in PNG, è l'istanza di classe [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/PngSaveOptions/), che ci consente di specificare la risoluzione delle immagini di output.

Quindi dobbiamo creare un'istanza della classe [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Volendo convertire un file LaTeX archiviato nel file system, utilizziamo [questa](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versione del costruttore. Dobbiamo specificare l'intero percorso del file. Altrimenti, il motore lo cercherà nella directory corrente (che è [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) e molto probabilmente non lo troverà. Tuttavia, l'estensione *.tex* può essere omessa. Il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza di classe [dispositivo](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Dal momento che stiamo convertendo il LaTeX in PNG, è un'istanza di classe [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), e questo è comune a tutti i formati di immagine supportati. Come ultimo argomento, passiamo le opzioni di conversione recentemente preparate.

Tutto ciò che resta da fare ora è [correre](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) il lavoro.

Indipendentemente dal fatto che la corsa abbia avuto successo o meno, il primo risultato che vedremo sarà l'output del terminale. Se la corsa ha avuto successo, sembrerà qualcosa del genere:


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

**Esempio di conversione alternativo**

Il seguente frammento di codice C# mostra un altro modo per ottenere l'output PNG: il dispositivo conserva i dati dell'immagine in memoria come array di byte anziché scriverli nel file system. Questo approccio è utile quando i byte PNG generati servono per ulteriori elaborazioni, ad esempio per inviarli in rete, memorizzarli in un database o eseguire trasformazioni aggiuntive prima del salvataggio.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

I file *"page-n.png"* verranno scritti in qualsiasi percorso specificato. Poiché l'opzione `DeviceWritesImages` è impostata su `false`, il dispositivo stesso non scrive file PNG nella directory di output.

## Sulle opzioni di input

Nel caso in cui il nostro file di input principale richieda dipendenze, ad esempio pacchetti, che non sono inclusi nel sistema di LaTeX di base e nei pacchetti supportati, dobbiamo impostare l'opzione [RecomeinputDirectory](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/requiredinputdirectory/) nel modo simile che impostiamo l'opzione [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/outputworkingdirectory/) e mettere le dipendenze in quella directory. Le dipendenze possono essere organizzate arbitrariamente nelle sottodirectory. Nel caso in cui abbiamo i nostri file da includere lungo il processo di composizione, ad esempio file di grafica esterna, dobbiamo anche impostare [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/inputworkingdirectory/) utilizzando il percorso per la posizione in cui tali file vengono raccolti. Possiamo anche posizionare il file di input principale da qualche parte all'interno della directory di input e specificare il percorso relativo nel metodo `run()` (o specificare nessun percorso se il file di input principale è nella radice). [Qui](/tex/{{lang.url-fragment}}net/aspose-tex-input/) sono i dettagli sul concetto di directory di input in **Aspose.TeX per .net** e hanno fornito implementazioni.

Altre opzioni di lavoro di Tex sono discusse [qui](/tex/{{lang.url-fragment}}net/other-options/).

**È inoltre possibile controllare la conversione da LaTeX a PNG gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-png) basata sulla base di [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

Di seguito, discutiamo della conversione in LaTeX ad altri formati di immagine raster supportati senza affondare in profondità i dettagli in quanto in realtà non ci sono dettagli. L'unica differenza è nel tipo di proprietà [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/saveoptions/) nelle opzioni di conversione.

## Come convertire il LaTeX in jpg

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToJPEG.cs" >}}

**È inoltre possibile controllare la conversione da LaTeX a jpg gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-jpg) basata su [Aspose.TeX per .net API](https://products.aspose.com/tex/net/).**

## Come convertire il LaTeX in tiff

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToTIFF.cs" >}}

{{% alert color="primary" %}}
Il pacchetto `Aspose.TeX.Drawing` non è ancora in grado di salvare file TIFF multipagina: con `TiffSaveOptions.Multipage` impostato su `true`, il file TIFF contiene solo la prima pagina. Impostare `Multipage` su `false` per ottenere un'immagine TIFF separata per ogni pagina. Vedere [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#known-limitations).
{{% /alert %}}

**È inoltre possibile controllare la conversione da LaTeX-tiff gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-tiff) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

## Come convertire il LaTeX in BMP

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToBMP.cs" >}}

**Puoi anche controllare la conversione gratuita in lattici a BMP [app Web](https://products.aspose.app/tex/conversion/latex-to-bmp) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

## Come convertire il LaTeX in SVG

E ancora un altro formato target supportato è [**svg**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** è un formato di immagine vettoriale basato su XML per definire la grafica bidimensionale, con supporto per l'interattività e l'animazione.

**Le immagini SVG** sono definite in un formato grafico vettoriale e memorizzate in file di testo XML. **Le immagini SVG** possono quindi essere ridimensionate senza perdita di qualità e i file **svg** possono essere cercati, indicizzati, script e compressi. I file di testo XML possono essere creati e modificati con editor di testo o redattori di grafica vettoriale e sono resi dai browser Web più utilizzati.

Esiste la libreria [**Aspose.svg**](https://products.aspose.com/svg/) che fornisce varie funzionalità relative a **svg**. Questi includono la creazione, il caricamento, la modifica e la conversione di documenti **SVG**.

La conversione da LaTeX a SVG è anche semplice come la [conversione in formati di immagini raster](/tex/{{lang.url-fragment}}net/latex-to-image/), tranne per il fatto che i [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/TeXOptions/saveoptions/) devono essere impostati su un'istanza di classe [SVGSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/) e il dispositivo deve essere modificato in un'istanza della classe [SVGDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**È inoltre possibile controllare la conversione da LaTeX a SVG gratuita [app Web](https://products.aspose.app/tex/conversion/latex-to-svg) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**
