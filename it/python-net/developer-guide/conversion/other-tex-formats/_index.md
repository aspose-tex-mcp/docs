---
translation: true
template: /templates/_template-python-net.md
title: Altri formati di output di conversione Tex | Python tramite .NET
linktitle: Altri formati di Tex
weight: 18
url: /python-net/other-tex-formats/
description: La soluzione API Aspose.TeX per Python fornisce funzionalità che consente di convertire file in LaTeX e file TEX personalizzati. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

È improbabile che tu sia attualmente necessario convertire un file Tex scritto in un formato diverso dal LaTeX. Tuttavia, se stai studiando gli interni di Tex Language o Tex per qualsiasi motivo, è ancora possibile. In ogni caso, **Aspose.TeX per Python** consente di convertire i file scritti in un formato*semplice tex*e consente anche di creare formati personalizzati e documenti di composizione progettati in questi formati.

Per iniziare, creeremo un formato personalizzato.

## Creazione di un formato personalizzato

Un file di formato è una rappresentazione binaria dello stato interno del motore TeX. Applicare prima una [licenza](/tex/{{lang.url-fragment}}python-net/licensing/). Inserire `customtex.tex` nella sottocartella `CustomTeXFormat` di `ASPOSE_TEX_INPUT_DIR` (predefinita: `input`). `ASPOSE_TEX_OUTPUT_DIR` indica la cartella di output (predefinita: `output`), dove il primo esempio crea `customtex.fmt`.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

Come puoi vedere, il codice ha una somiglianza con il codice per la conversione di un file Tex. Tuttavia, ci sono alcune distinzioni.

In primo luogo, in questo caso, utilizziamo la configurazione del lavoro [TexConfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/). Questa configurazione garantisce che lo stato del motore sia "vergine", il che significa che i parametri interni hanno i loro valori predefiniti e l'insieme di sequenze di controllo si allinea con l'insieme di primitive. Nel nostro esempio, l'insieme di primitivi viene ampliato [nell'articolo Aspy.tex e Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

In seguito, procediamo con la configurazione delle directory di lavoro input e output come al solito. La directory di lavoro input dovrebbe includere il file di origine del formato principale e tutte le sue dipendenze.

E la seconda grande differenza è il metodo con cui eseguiamo il lavoro. In questo caso, utilizziamo il metodo statico [create_format ()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions), che, insieme alle opzioni, richiede che il nome del file di origine principale sia identico al nome del formato.

## Compromettere un file tex nel tuo formato personalizzato

L’esempio seguente crea prima `customtex.fmt` per poter essere eseguito autonomamente. Poi carica il formato e compone il testo di un flusso binario in `typeset-with-custom-format.xps`.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

Per specificare il formato, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/). Nel costruttore di opzioni, utilizziamo la configurazione [TexConfig.Object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider), che richiede il nostro provider di formato come argomento e carica il formato in cima allo stato "vergine" del motore.

Il codice rimanente dovrebbe essere familiare, in quanto utilizza le caratteristiche discusse in precedenza in questa [guida](/tex/{{lang.url-fragment}}python-net/conversion/).

## Testa di un file tex in un formato Tex semplice

Se rimuoviamo il provider di formato dal codice mostrato sopra, il motore caricherà il formato predefinito, che è [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) nel suo quarto senso. Pertanto, se hai un file Tex scritto nel semplice formato Tex, è possibile convertirlo in qualsiasi formato target supportato usando questo approccio.