---
translation: true
template: /templates/_template-net.md
title: Altri formati di output di conversione TeX | .NET
linktitle: Altri formati TeX
weight: 18
url: /net/other-tex-formats/
description: La funzionalità di conversione della soluzione API **Aspose.TeX** per .NET consente di convertire i file in LaTeX e i tuoi file TeX personalizzati. Ecco alcuni esempi di codice.
lastmod: "2026-04-03"
---

{{<section overview>}}

È altamente improbabile che al momento tu voglia convertire un file TeX scritto in un formato diverso da LaTeX. Tuttavia, questo è possibile se stai studiando il linguaggio TeX e/o i suoi meccanismi interni per qualche motivo. Ad ogni modo, **Aspose.TeX per .NET** ti permette di convertire file scritti in formato Plain TeX. Ti permette anche di creare formati personalizzati e di impaginare documenti progettati in questi formati.

Inizieremo con la creazione di un formato personalizzato.

## Creazione di un formato personalizzato

Ricordiamo che il file di formato è un dump binario dello stato interno del motore TeX.

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-CreateCustomFormat.cs" >}}

Come potete vedere, il codice è simile a quello per la conversione di un file TeX. Tuttavia, ci sono alcune differenze.

Innanzitutto, qui utilizziamo la configurazione del job [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectinitex/). Si tratta di una configurazione speciale che lascia il motore "invariato", ovvero i parametri interni mantengono i valori predefiniti e l'insieme delle sequenze di controllo coincide con l'insieme delle primitive. Nel nostro esempio, l'insieme delle primitive viene esteso nel senso descritto [qui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Successivamente, impostiamo le directory di lavoro di input e output come di consueto. La directory di lavoro di input deve contenere il file sorgente del formato principale e tutte le sue dipendenze.

La seconda differenza fondamentale riguarda la modalità di esecuzione del job. Questa volta utilizziamo il metodo statico [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), che insieme alle opzioni accetta il nome del file sorgente principale, che deve essere uguale al nome del formato.

## Impaginazione di un file TeX nel tuo formato personalizzato

Ora che abbiamo il nostro formato TeX, vogliamo impaginare un file TeX scritto in questo formato. Ecco il codice:

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-TypesetWithCustomFormat.cs" >}}

Ovviamente, dobbiamo specificare il formato in qualche modo. Innanzitutto, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/tex/net/aspose.tex.resourceproviders/formatprovider/). Successivamente, nel costruttore delle opzioni, utilizziamo la configurazione [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objecttex/), che accetta il nostro provider di formato come argomento e carica il formato sullo stato "vergine" del motore.

Il resto del codice dovrebbe esservi familiare. Utilizza le funzionalità discusse in precedenza in questa [guida](/tex/{{lang.url-fragment}}net/conversion/).

## Composizione di un file TeX in formato TeX semplice

Se rimuoviamo il provider di formato dal codice appena mostrato, il motore caricherà il formato predefinito, ovvero [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) nel suo quarto senso. Pertanto, se si dispone di un file TeX scritto in formato TeX semplice, in questo modo è possibile convertirlo in qualsiasi formato di destinazione supportato.
