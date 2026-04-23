---
translation: true
template: /templates/_template-java.md
title: LaTeX a PDF | Java
linktitle: LaTeX a PDF
weight: 11
url: /java/latex-to-pdf/
keywords: LaTeX a PDF, PDF in LaTeX, convertite in LaTeX in PDF
description: Per convertire TEX in PDF usando la soluzione API Aspose.Tex per Java impara questo articolo per vedere che descrive come fare questo e gli esempi di codice.
lastmod: "2026-04-21"
---

{{<section overview>}}


## Come convertire il LaTeX in PDF

Diamo un'occhiata più da vicino al codice Java che fornisce il modo più semplice per convertire il LaTeX in formato PDF.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

Quindi, la prima cosa che dobbiamo fare (a volte non la prima, come scopriremo più avanti) è creare un'istanza della classe [Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). L'unico metodo statico che fa questo è [ConsoleAppoptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), quindi non ci preoccupiamo del significato del suo nome. Il metodo prende una [istanza](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) della classe [TexConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), che è esattamente adatta per la conversione di un [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Questa configurazione indica al motore Object Tex di caricare il formato Object Latex e di essere pronto ad accettare il file LaTeX. Il formato di LaTeX oggetto è solo il formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), tranne per il fatto che utilizza le primitive specifiche [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) per impostare le metriche di pagina.

La prima delle opzioni richieste è [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) che definisce lo spazio o l'area, in cui verrà scritto l'output di Tex. [Qui](/tex/{{lang.url-fragment}}java/aspose-tex-output/) sono i dettagli sul concetto di directory di output in **Aspose.TeX per java**. In questo esempio, utilizziamo la classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), che ci consente di scrivere l'output nella directory o nella cartella specificata.

La seconda opzione è un'istanza di classe [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions) che controllerà la trasformazione del [modello a oggetto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato target. Dal momento che stiamo convertendo il LaTeX in PDF, è l'istanza di classe [PDFSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Quindi dobbiamo creare un'istanza della classe [Texjob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Volendo convertire un file LaTeX archiviato nel file system, utilizziamo [questa](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) versione del costruttore. Dovremmo specificare l'intero percorso del file. Altrimenti, il motore lo cercherà nella directory corrente (che è definita [qui](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) e molto probabilmente non lo troverà. Tuttavia, possiamo omettere l'estensione se il nostro file ha quello *.tex*. Il motore lo aggiungerà automaticamente. Il secondo argomento del costruttore è un'istanza di classe [dispositivo](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Dal momento che stiamo convertendo il LaTeX in PDF, è un'istanza di classe [PDFDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice). Come ultimo argomento, passiamo le opzioni di conversione recentemente preparate.

Tutto quello che dobbiamo fare ora è [correre](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--) il lavoro.

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

Troveremo altri prodotti dell'esecuzione del motore nella cartella che abbiamo specificato come directory di output. Quelli saranno il file trascrizione (.log) e, **voilà!**, il file PDF di output principale.

## Un modo alternativo per scrivere il file PDF di output principale

C'è un altro costruttore della classe [PDFDEVICE](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), che ci consente di ottenere il file PDF risultante in modo alternativo.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

Il file *Any-name.pdf* nella directory specificata sarà il nostro principale file PDF di output. Allo stesso tempo, a differenza di [output di immagini](/tex/{{lang.url-fragment}}java/latex-to-png/#an-alternative-way-to-write-main-output-png-files), non troveremo alcun file PDF nella directory di output definita dalle opzioni di conversione. Eccezione: *Any-name.pdf* si trova (dal suo percorso) nella stessa directory del file system assegnato all'opzione [outputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) utilizzando [outputfilesystemdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

## Sulle opzioni di input

Nel caso in cui il nostro file di input principale richieda dipendenze, ad esempio pacchetti, che non sono inclusi nel sistema di LaTeX di base e nei pacchetti supportati, dobbiamo impostare l'opzione [richiesta inputdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) nel modo simile che impostiamo l'opzione [outputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) e mettere le dipendenze in quella directory. Le dipendenze possono essere organizzate arbitrariamente nelle sottodirectory. Nel caso in cui abbiamo i nostri file da includere lungo il processo di composizione, ad esempio file di grafica esterna, dobbiamo anche impostare [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) utilizzando il percorso per la posizione in cui tali file vengono raccolti. Potremmo anche posizionare il file di input principale da qualche parte all'interno della directory di input e specificare il percorso relativo nel metodo `run()` (o specificare alcun percorso se il file di input principale è nella radice). [Qui](/tex/{{lang.url-fragment}}java/aspose-tex-input/) sono i dettagli sul concetto di directory di input in **Aspose.TeX per java** e hanno fornito implementazioni.

Altre opzioni di lavoro di Tex sono discusse [qui](/tex/{{lang.url-fragment}}java/other-options/).

**È inoltre possibile controllare la conversione gratuita di LaTeX-to-PDF [app Web](https://products.aspose.app/tex/conversion/latex-to-pdf) basata sulla base dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**