---
translation: true
template: /templates/_template-python-net.md
title: Metodi alternativi per fornire il file di input tex principale | Python tramite .NET
linktitle: Altri modi per fornire il principale file di input Tex
weight: 14
url: /python-net/other-ways-of-main-input/
description: Aspose.TeX Soluzione API per Python include un costruttore che accetta un flusso come primo argomento, fornendo funzionalità di conversione.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Fornire il file di input principale al motore TEX utilizzando un flusso

Finora abbiamo imparato solo come fornire il [file di input principale](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motore TEX come nome di file, sia nella sua forma completa che in una forma abbreviata, con o senza estensione. Tuttavia, è disponibile [un altro costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) nella classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) che accetta un flusso come primo argomento. Ciò è utile se, per qualche motivo, il file di input principale non è sotto forma di un file sul file system del disco. Ecco un esempio di come può essere implementato:

Impostare `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output (predefinita: `output`). Applicare prima una licenza. [Licensing](/tex/it/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Codificare un documento LaTeX completo in un flusso binario `BytesIO` e passarlo a `TeXJob` con `TeXConfig.object_latex`. Mantenere aperto il flusso durante il lavoro. Risultato: `texput.xps` e `texput.log`.

Si noti che tutti i file di output verranno denominati `texput`. Questo perché il motore non ha accesso a nessun altro nome. `Texput` è il nome del lavoro predefinito. È possibile trovare informazioni più dettagliate sui nomi dei lavori [output tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [come impostare il nome del lavoro](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) paragrafi.

## Inserimento del file di input tex principale tramite il terminale

È disponibile [un altro costruttore](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) nella classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) che non ci consente di specificare affatto l'input. Potresti chiederti cosa avrebbe elaborato un lavoro del genere. In questo caso, dovremmo utilizzare un terminale di input. Il motore Tex ci spingerà a inserire il nome del file dal terminale.

Ecco il codice:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Salvare il seguente testo plain TeX come `hello-world.tex` in `ASPOSE_TEX_INPUT_DIR` (predefinita: `input`). L’esempio usa `TeXConfig.object_tex()`. Alla richiesta, digitare `hello-world.tex` e premere Invio, oppure fornire il nome tramite input standard. Risultato: `hello-world.xps` e `hello-world.log`.

```tex
Hello, World!
\end
```
