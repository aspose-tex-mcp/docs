---
translation: true
template: /templates/_template-java.md
title: Altri formati di output di conversione Tex | Java
linktitle: Altri formati di Tex
weight: 18
url: /java/other-tex-formats/
description: La funzionalità di conversione della soluzione API Aspose.TeX per Java consente di convertire i file in LaTeX e i tuoi file TEX personalizzati. Ecco alcuni esempi di codice.
lastmod: "2026-04-21"
---

{{<section overview>}}

È altamente improbabile che tu voglia attualmente convertire un file Tex scritto in qualsiasi altro formato rispetto a LaTex. Ma questo è possibile se stai studiando la lingua Tex e/o gli interni per qualche motivo. Ad ogni modo, **Aspose.TeX per java** ti consente di convertire i file scritti in semplice formato tex. Inoltre, consente di creare formati personalizzati e documenti di composizione progettati in questi formati.

Inizieremo con la creazione di un formato personalizzato.

## Creazione di un formato personalizzato

Ricordiamo che il file di formato è una dump binaria dello stato interno del motore Tex.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.java" >}}

Come puoi vedere, il codice è simile al codice per la conversione di un file Tex. Ma ci sono alcune differenze.

Innanzitutto, qui utilizziamo la configurazione del lavoro [TexConfig.ObjectInitex()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectIniTeX--). Questa è una configurazione speciale che lascia lo stato del motore "vergine", ovvero i parametri interni hanno i loro valori predefiniti e l'insieme di sequenze di controllo coincide con l'insieme di primitive. Nel nostro esempio, l'insieme di primitive è esteso nel senso menzionato [qui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Successivamente, impostiamo le directory di lavoro input e output come al solito. La directory di lavoro input deve contenere il file di origine del formato principale e tutte le sue dipendenze.

E la seconda differenza chiave è il modo in cui gestiamo il lavoro. Questa volta utilizziamo il metodo statico [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#createFormat-java.lang.String-com.aspose.tex.TeXOptions-), che insieme alle opzioni prende il nome del file di origine principale, che deve essere uguale al nome del formato.

## Compromettere un file tex nel tuo formato personalizzato

Ora che abbiamo il nostro formato tex, vogliamo scrivere un file Tex scritto in questo formato. Ecco il codice:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.java" >}}

Ovviamente, dobbiamo in qualche modo specificare il formato. Prima di tutto, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/FormatProvider). Quindi, nel costruttore di opzioni, utilizziamo la configurazione [TexConfig.objectx()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectTeX--), che prende il nostro fornitore di formato come argomento e carica il formato in cima allo stato "vergine" del motore.

Il resto del codice dovrebbe essere familiare a te. Utilizza le funzionalità discusse in precedenza in questa [guida](/tex/{{lang.url-fragment}}java/conversion/).

## Testa di un file tex in un formato Tex semplice

Se gettiamo via il provider di formato dal codice appena dimostrato, il motore caricherà il formato predefinito, che è [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) nel suo quarto senso. Pertanto, se hai un file Tex scritto in un semplice formato Tex, in questo modo puoi convertirlo in qualsiasi formato target supportato.