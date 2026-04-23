---
translation: true
template: /templates/_template-net.md
title: Altri formati di output di conversione TeX | .NET
linktitle: Altri formati TeX
weight: 18
url: /net/other-TeX-formats/
description: La funzionalità di conversione della soluzione API **Aspose.TeX** per .NET consente di convertire i file in LaTeX e i tuoi file TeX personalizzati. Ecco alcuni esempi di codice.
lastmod: "2026-04-22"
---

{{<section overview>}}

È altamente improbabile che tu voglia attualmente convertire un file TeX scritto in qualsiasi altro formato rispetto a LaTeX. Ma questo è possibile se stai studiando la lingua TeX e/o gli interni per qualche motivo. Ad ogni modo, **Aspose.TeX per .NET** ti consente di convertire i file scritti in semplice formato TeX. Inoltre, consente di creare formati personalizzati e documenti di composizione progettati in questi formati.

Inizieremo con la creazione di un formato personalizzato.

## Creazione di un formato personalizzato

Ricordiamo che il file di formato è una dump binaria dello stato interno del motore TeX.

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-CreateCustomFormat.cs" >}}

Come puoi vedere, il codice è simile al codice per la conversione di un file TeX. Ma ci sono alcune differenze.

Innanzitutto, qui utilizziamo la configurazione del lavoro [TeXConfig.ObjectIniTeX](https://reference.aspose.com/TeX/net/aspose.TeX/TeXconfig/objectiniTeX/). Questa è una configurazione speciale che lascia lo stato del motore "vergine", ovvero i parametri interni hanno i loro valori predefiniti e l'insieme di sequenze di controllo coincide con l'insieme di primitive. Nel nostro esempio, l'insieme di primitive è esteso nel senso menzionato [qui](/TeX/{{lang.url-fragment}}net/aspose-TeX-and-object-TeX/#object-TeX).

Successivamente, impostiamo le directory di lavoro input e output come al solito. La directory di lavoro input deve contenere il file di origine del formato principale e tutte le sue dipendenze.

E la seconda differenza chiave è il modo in cui gestiamo il lavoro. Questa volta utilizziamo il metodo statico [CreateFormat()](https://reference.aspose.com/TeX/net/aspose.TeX/TeXjob/createformat/), che insieme alle opzioni prende il nome del file di origine principale, che deve essere uguale al nome del formato.

## Compromettere un file TeX nel tuo formato personalizzato

Ora che abbiamo il nostro formato TeX, vogliamo scrivere un file TeX scritto in questo formato. Ecco il codice:

{{< gist "aspose-com-gists" "c0eb6cbcfb001b7e6355cafa4611afed" "Example-TypesetWithCustomFormat.cs" >}}

Ovviamente, dobbiamo in qualche modo specificare il formato. Prima di tutto, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/TeX/net/aspose.TeX.resourceproviders/formatprovider/). Quindi, nel costruttore di opzioni, utilizziamo la configurazione [TeXConfig.objectx()](https://reference.aspose.com/TeX/net/aspose.TeX/TeXconfig/objectTeX/), che prende il nostro fornitore di formato come argomento e carica il formato in cima allo stato "vergine" del motore.

Il resto del codice dovrebbe essere familiare a te. Utilizza le funzionalità discusse in precedenza in questa [guida](/TeX/{{lang.url-fragment}}net/conversion/).

## Testa di un file TeX in un formato TeX semplice

Se gettiamo via il provider di formato dal codice appena dimostrato, il motore caricherà il formato predefinito, che è [Object TeX](/TeX/{{lang.url-fragment}}net/aspose-TeX-and-object-TeX/) nel suo quarto senso. Pertanto, se hai un file TeX scritto in un semplice formato TeX, in questo modo puoi convertirlo in qualsiasi formato target supportato.
