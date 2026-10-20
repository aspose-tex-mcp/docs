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

Impostare `inputDirectory` su una cartella contenente `customtex.tex` e le sue dipendenze e `outputDirectory` su una cartella di output esistente. Il sorgente del formato deve terminare con `\dump`; l’esempio crea qui `customtex.fmt`. Importare le classi Aspose.TeX utilizzate negli esempi e, per la composizione, `com.aspose.tex.rendering.XpsDevice`, `java.io.ByteArrayInputStream` e `java.nio.charset.StandardCharsets`. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza come descritto nella [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-CreateCustomTeXFormat.java" >}}

Come puoi vedere, il codice è simile al codice per la conversione di un file Tex. Ma ci sono alcune differenze.

Innanzitutto, qui utilizziamo la configurazione del lavoro [TexConfig.ObjectInitex()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) . Questa è una configurazione speciale che lascia lo stato del motore "vergine", ovvero i parametri interni hanno i loro valori predefiniti e l'insieme di sequenze di controllo coincide con l'insieme di primitive. Nel nostro esempio, l'insieme di primitive è esteso nel senso menzionato [qui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Successivamente, impostiamo le directory di lavoro input e output come al solito. La directory di lavoro input deve contenere il file di origine del formato principale e tutte le sue dipendenze.

E la seconda differenza chiave è il modo in cui gestiamo il lavoro. Questa volta utilizziamo il metodo statico [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) , che insieme alle opzioni prende il nome del file di origine principale, che deve essere uguale al nome del formato.

## Compromettere un file tex nel tuo formato personalizzato

Ora che abbiamo il nostro formato tex, vogliamo scrivere un file Tex scritto in questo formato. Ecco il codice:

Impostare `formatDirectory` sulla cartella contenente il file `customtex.fmt` creato in precedenza e `outputDirectory` su una cartella di output esistente. L’esempio compone un flusso di testo autonomo in `typeset-with-custom-format.xps`, quindi non richiede una directory di lavoro di input. Impostarla se l’input principale ha dipendenze, come immagini.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-TypesetWithCustomTeXFormat.java" >}}

Ovviamente, dobbiamo in qualche modo specificare il formato. Prima di tutto, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) . Quindi, nel costruttore di opzioni, utilizziamo la configurazione [TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-), che prende il nostro fornitore di formato come argomento e carica il formato in cima allo stato "vergine" del motore.

Entrambi gli esempi vengono eseguiti senza interazione e acquisiscono l’output del terminale in memoria. Dopo il lavoro, l’esempio di composizione chiude il flusso di input, rilascia il dispositivo XPS e chiude la directory di lavoro e il provider del formato. Queste funzionalità sono illustrate in precedenza in questa [guida](/tex/{{lang.url-fragment}}java/conversion/).

## Testa di un file tex in un formato Tex semplice

Se utilizziamo `TeXConfig.objectTeX()` senza un provider di formato, il motore caricherà il formato predefinito, che è [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) nel suo quarto senso. Pertanto, se hai un file Tex scritto in un semplice formato Tex, in questo modo puoi convertirlo in qualsiasi formato target supportato.