---
translation: true
template: /templates/_template-net.md
title: Altri modi per fornire il principale file di input TeX | .NET
linktitle: Altri modi per fornire il principale file di input TeX
weight: 14
url: /net/other-ways-of-main-input/
description: La funzionalità di conversione della soluzione API Aspose.TeX per .NET ha un costruttore che accetta un flusso come primo argomento. Ecco alcuni esempi di codice.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Fornire il file di input principale al motore TeX come flusso

Fino a questo punto, sapevamo solo come passare il [file di input principale](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motore TeX come nome di un file, sia completamente specificato che in breve, sia con un'estensione che senza di essa. Ma c'è un altro [costruttore](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) della classe `TeXJob`, che prende un flusso come primo argomento. Questo è conveniente se per qualche motivo abbiamo il file di input principale in un modulo diverso da un file sul file system disco. Ecco come può essere implementato:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-StreamInput-LaTeX.cs" >}}

Si noti che tutti i file di output avranno il nome *texput*. Questo perché il motore non può ottenere nessun altro nome da nessuna parte. *texput* è il nome del lavoro predefinito. [Qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [qui](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) sono dettagli sui nomi dei lavori.

## Immettere il file di input TeX principale dal terminale

C'è ancora un altro [costruttore](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) della classe `TeXJob`, che non ci consente affatto di specificare l'input. Allora, cosa sta per elaborare un lavoro del genere, potresti chiederti? Questa volta avremo bisogno di un terminale di input. Il motore TeX ci chiederà di inserire il nome del file dal terminale.

Ecco il codice:

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-MainInputTerminal.cs" >}}

Non appena viene eseguito, il motore si attacca, aspettando che inseriamo il nome del file (con o senza percorso, con o senza estensione):


![Finestra terminale](/tex/images/net/Conversion-MainInputTerminal.png)

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
