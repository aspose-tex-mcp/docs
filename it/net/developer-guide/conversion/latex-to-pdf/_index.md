---
translation: true
template: /templates/_template-net.md
title: LaTeX a pdf | .NET
linktitle: LaTeX a pdf
weight: 11
url: /net/latex-to-pdf/
keywords: LaTeX a PDF, PDF in LaTeX, convertite in LaTeX in PDF
description: Per convertire TEX in PDF usando la soluzione API Aspose.TeX per .NET Impara questo articolo per vedere che descrive come fare questo e gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}


## Come convertire il LaTeX in PDF

Diamo uno sguardo dettagliato al codice in C# fornendo il modo più semplice per convertire il LaTeX in formato PDF.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Quindi, la prima cosa che dobbiamo fare (beh, a volte non il primo) è creare un'istanza della classe [texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). L'unico metodo statico che fa questo è [ConsoleAppoptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), quindi non essere perplessi dal significato del suo nome. Il metodo prende una [istanza](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) della classe [TexConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), che è esattamente adatta per la conversione di un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object Tex di caricare il formato Object Latex e di essere pronto ad accettare il file Latex. Il formato di LaTeX oggetto è in realtà solo il formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), tranne per il fatto che utilizza le primitive specifiche [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per impostare le metriche di pagina.

La prima delle opzioni richieste è [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) che definisce lo spazio o l'area, in cui verrà scritto l'output di Tex. [Qui](/tex/{{lang.url-fragment}}net/aspose-tex-output/) sono i dettagli sul concetto di directory di output in **Aspose.TeX per .net**. In questo esempio, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), che ci consente di scrivere l'output alla directory o alla cartella specificata.

La seconda opzione è un'istanza di classe [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) che controllerà la trasformazione del [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato target. Dal momento che stiamo convertendo il LaTeX in PDF, è l'istanza di classe [PDFSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Quindi dobbiamo creare un'istanza della classe [Texjob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Volendo convertire un file LaTeX archiviato nel file system, utilizziamo [questa](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) versione del costruttore. Dobbiamo specificare l'intero percorso del file. Altrimenti, il motore lo cercherà nella directory corrente (che è [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) e molto probabilmente non lo troverà. Tuttavia, possiamo omettere l'estensione se il nostro file ha quello *.tex*. Il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza di classe [dispositivo](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Dal momento che stiamo convertendo il LaTeX in PDF, è un'istanza di classe [PDFDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). Come ultimo argomento, passiamo le opzioni di conversione recentemente preparate.

Tutto ciò che resta da fare ora è [correre](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) il lavoro.

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Troveremo altri "frutti" del lavoro del motore nella cartella che abbiamo specificato come directory di output. Quello sarà il file di trascrizione e, **eccolo qui!**, il principale file PDF di output.

## Un modo alternativo per scrivere il file PDF di output principale

C'è un altro costruttore della classe [PDFDEVICE](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), che ci consente di ottenere il file PDF risultante in modo alternativo.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Alternative.cs" >}}

Il file *Any-name.pdf* nella directory specificata sarà il nostro principale file PDF di output. Allo stesso tempo, a differenza di [output di immagini](/tex/{{lang.url-fragment}}net/latex-to-png/#an-alternative-way-to-write-main-output-png-files), non troveremo alcun file PDF nella directory di output definita dalle opzioni di conversione. Eccezione: *Any-name.pdf* si trova (dal suo percorso) nella stessa directory del file system assegnato all'opzione [outputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) utilizzando [outputfilesystemdirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

## Sulle opzioni di input

Nel caso in cui il nostro file di input principale richieda dipendenze, ad esempio pacchetti, che non sono inclusi nel sistema di LaTeX di base e nei pacchetti supportati, dobbiamo impostare l'opzione [richiesta inputdirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) nel modo simile che impostiamo l'opzione [outputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) e mettere le dipendenze in quella directory. Le dipendenze possono essere organizzate arbitrariamente nelle sottodirectory. Nel caso in cui abbiamo i nostri file da includere lungo il processo di composizione, ad esempio file di grafica esterna, dobbiamo anche impostare [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) utilizzando il percorso per la posizione in cui tali file vengono raccolti. Potremmo anche posizionare il file di input principale da qualche parte all'interno della directory di input e specificare il percorso relativo nel metodo `run()` (o specificare alcun percorso se il file di input principale è nella radice). [Qui](/tex/{{lang.url-fragment}}net/aspose-tex-input/) sono i dettagli sul concetto di directory di input in **Aspose.TeX per .net** e hanno fornito implementazioni.

Altre opzioni di lavoro di Tex sono discusse [qui](/tex/{{lang.url-fragment}}net/other-options/).

**È inoltre possibile controllare la conversione gratuita Latex-to-PDF [app Web](https://products.aspose.app/tex/conversion/latex-to-pdf) basata su [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**
