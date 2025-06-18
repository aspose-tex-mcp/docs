---
translation: true
template: /templates/_template-python-net.md
title: LaTeX a PDF | Aspose.TeX per Python
linktitle: LaTeX a PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: LaTeX a PDF, PDF in LaTeX, convertite in LaTeX in PDF
description: Scopri come convertire Tex in PDF usando la soluzione API Aspose.TeX per Python con questo articolo, che fornisce una spiegazione dettagliata e esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Convertire il LaTeX in PDF

Ora, esaminiamo il codice Python che offre l'approccio più semplice alla conversione del formato di LaTeX in PDF in profondità.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Per iniziare, dobbiamo creare un'istanza della classe [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Il metodo [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) è l'unico metodo statico che lo fa, quindi non preoccuparti del suo nome. Questo metodo accetta un'istanza [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) della classe [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), perfetta per convertire un file [LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object TeX di caricare il formato Object LaTeX e di prepararsi a elaborare il file LaTeX. Il formato Object LaTeX è essenzialmente lo stesso del formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), ma utilizza primitive specifiche di [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per definire le metriche della pagina.

La prima opzione che deve essere specificata è [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), che determina la posizione in cui verrà salvato l'output Tex. Se necessario, è possibile trovare maggiori informazioni sulla [concetto della directory di output in **aspose.tex**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). In questo caso particolare, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), che ci consente di scrivere l'output su una directory o una cartella designata.

La seconda opzione richiede un'istanza della classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), che determina come il [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) viene trasformato nel formato desiderato. Nel nostro caso, poiché stiamo convertendo il LaTeX in PDF, si riferisce a un'istanza della classe [PDFSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Per convertire un file LaTeX archiviato nel file system, dobbiamo creare un'istanza della classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) usando il [costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions) che prende il percorso completo del file come parametro. Se non specifichiamo il percorso completo, il motore cercherà il file nella directory corrente (che è la directory di lavoro dello script) e potrebbe non trovarlo. Tuttavia, possiamo omettere l'estensione se il nostro file ha l'estensione `.tex`, poiché il motore la aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza della classe [dispositivo](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Nel nostro caso, dal momento che stiamo convertendo il LaTeX in PDF, è un'istanza della classe [PDFDEVICE](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Infine, passiamo le opzioni di conversione recentemente preparate come ultimo argomento.

Ora, tutto ciò che rimane è [correre](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) il lavoro.

Dopo l'esecuzione, indipendentemente dal fatto che abbia avuto successo o no, la prima cosa che vedremo è l'output del terminale. Se l'esecuzione ha esito positivo, l'output sembrerà simile a questo:

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

Nella cartella che abbiamo specificato come directory di output, troveremo il file di trascrizione e, **qui è!**, il principale file PDF di output, tra gli altri risultati del lavoro del motore.

## Un modo alternativo per scrivere il file PDF di output principale

La classe *pdfdevice* ha un altro [costruttore](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase) che ci consente di ottenere il file PDF risultante in modo diverso.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

Il file PDF di output principale verrà denominato `qualsiasi name.pdf` e sarà posizionato nella directory specificata. Tuttavia, a differenza dell'output [immagine](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files), non ci saranno altri file PDF nella directory di output specificati dalle opzioni di conversione. L'eccezione è se `any-name.pdf` si trova nella stessa directory del file system assegnato all'opzione *output_working_directory *utilizzando *outputfilesystemdirectory*.

## Sulle opzioni di input

Se il nostro file di input principale richiede dipendenze, come pacchetti che non sono inclusi nel sistema in LaTeX di base e nei pacchetti supportati, è necessario impostare l'opzione [richiesta_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) in modo simile a quando impostiamo l'opzione * output_working_directory * e posizionare le dipendenze in quella directory. Le dipendenze possono essere organizzate nelle sottodirectory come desiderato. Inoltre, se abbiamo i nostri file da includere nel processo di composizione, come i file grafici esterni, dobbiamo anche impostare [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) utilizzando il percorso per la posizione in cui tali file sono archiviati. Possiamo anche posizionare il file di input principale all'interno della directory di input e specificare il percorso relativo nel metodo `run()` o specificare alcun percorso se il file di input principale è nella radice. Per maggiori dettagli sul concetto di directory di input in **Aspose.TeX per python** e le implementazioni fornite, fare riferimento a [qui](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Ci sono anche [altre opzioni di lavoro di Tex](/tex/{{lang.url-fragment}}python-net/other-options/) discusse.

**Puoi anche esplorare la conversione gratuita [app Web per la latex-to-pdf](https://products.aspose.app/tex/conversion/latex-to-pdf), che è sviluppata utilizzando [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**