---
translation: true
template: /templates/_template-python-net.md
title: Metodi alternativi per fornire il file di input tex principale | Python
linktitle: Altri modi per fornire il principale file di input Tex
weight: 14
url: /python-net/other-ways-of-main-input/
description: Aspose.TeX Soluzione API per Python include un costruttore che accetta un flusso come primo argomento, fornendo funzionalità di conversione.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Fornire il file di input principale al motore TEX utilizzando un flusso

Finora abbiamo imparato solo come fornire il [file di input principale](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motore TEX come nome di file, sia nella sua forma completa che in una forma abbreviata, con o senza estensione. Tuttavia, è disponibile [un altro costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) nella classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) che accetta un flusso come primo argomento. Ciò è utile se, per qualche motivo, il file di input principale non è sotto forma di un file sul file system del disco. Ecco un esempio di come può essere implementato:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Si noti che tutti i file di output verranno denominati `texput`. Questo perché il motore non ha accesso a nessun altro nome. `Texput` è il nome del lavoro predefinito. È possibile trovare informazioni più dettagliate sui nomi dei lavori [output tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [come impostare il nome del lavoro](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) paragrafi.

## Inserimento del file di input tex principale tramite il terminale

È disponibile [un altro costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) nella classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) che non ci consente di specificare affatto l'input. Potresti chiederti cosa avrebbe elaborato un lavoro del genere. In questo caso, dovremmo utilizzare un terminale di input. Il motore Tex ci spingerà a inserire il nome del file dal terminale.

Ecco il codice:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Non appena viene eseguito, il motore si fermerà e ci aspetterà di inserire il nome del file (con o senza un percorso e con o senza un'estensione):


![Finestra terminale](/tex/images/python-net/.png)

Ed ecco come apparirebbe sul terminale di uscita (console):

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