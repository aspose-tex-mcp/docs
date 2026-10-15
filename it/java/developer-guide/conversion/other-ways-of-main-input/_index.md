---
translation: true
template: /templates/_template-java.md
title: Altri modi per fornire il principale file di input Tex | Java
linktitle: Altri modi per fornire il principale file di input Tex
weight: 14
url: /java/other-ways-of-main-input/
description: La funzionalità di conversione della soluzione API ASPUS.TEX per Java ha un costruttore che accetta un flusso come primo argomento. Ecco alcuni esempi di codice.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Fornire il file di input principale al motore TEX come flusso

Fino a questo punto, sapevamo solo come passare il [file di input principale](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motore TEX come nome di un file, sia completamente specificato che in breve, sia con un'estensione che senza di essa. Ma c'è un altro [costruttore](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) della classe `Texjob`, che accetta un flusso come primo argomento. Questo è conveniente se per qualche motivo abbiamo il file di input principale in un modulo diverso da un file sul file system disco. Ecco come possiamo affrontarlo:

Impostare `outputDirectory` su una cartella di output esistente. Importare le classi Aspose.TeX utilizzate negli esempi, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` e, per l’input tramite flusso, `java.io.ByteArrayInputStream` e `java.nio.charset.StandardCharsets`. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza come descritto nella [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione. L’esempio del flusso contiene un documento LaTeX completo e non richiede quindi una directory di lavoro di input. I flussi e i dispositivi rimangono aperti fino al termine del lavoro, quindi vengono chiusi o rilasciati.

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

Se all’input tramite flusso non viene assegnato esplicitamente un nome di lavoro, il motore utilizza il nome predefinito *texput*. Questo esempio crea `texput.xps` e `texput.log`. Usare `options.setJobName(...)` per scegliere un altro nome di lavoro. Vedere [qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [qui](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) per i dettagli sui nomi dei lavori.

## Immettere il file di input tex principale dal terminale

C'è ancora un altro [costruttore](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  della classe `Texjob`, che non ci consente di specificare affatto l'input. Allora, cosa sta per elaborare un lavoro del genere, potresti chiederti? Questa volta avremo bisogno di un terminale di input. Il motore Tex ci chiederà di inserire il nome del file dal terminale.

Impostare `inputDirectory` su una cartella contenente un documento LaTeX completo chiamato `hello-world.ltx` e `outputDirectory` su una cartella di output esistente. Eseguire l’esempio in una console, inserire `hello-world.ltx` al prompt `**` e premere Invio. Crea `hello-world.xps` e scrive l’output del terminale nella console. Entrambi gli esempi utilizzano `NonstopMode` per l’elaborazione, ma il costruttore del terminale richiede comunque il nome di file iniziale. Per l’esecuzione automatica, fornire un’implementazione di `IInputTerminal` o utilizzare input da file o flusso.

Ecco il codice:

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

Non appena viene eseguito, il motore si attacca, aspettando che inseriamo il nome del file (con o senza percorso, con o senza estensione):


![Finestra terminale](/tex/images/java/Conversion-MainInputTerminal.png)

Ed è così che sembrerebbe sul terminale di uscita che è la console:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```