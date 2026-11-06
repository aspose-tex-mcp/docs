---
translation: true
template: /templates/_template-python-net.md
title: Asspose.Tex's Input Interface | Python tramite .NET
linktitle: Aspose.TeX's Input Interface
weight: 15
url: /python-net/aspose-tex-input/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Python con Tex, poiché un formato di input viene spiegato qui con gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

> Per definizioni formali dell'implementazione I/O in **Aspose.TeX per Python**, consultare il [riferimento API](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## L'idea alla base della directory di input

Dato che i primitivi I/O della lingua tex possono solo gestire i nomi dei file, **aspose.tex per Python** definisce una directory come una mappatura tra nomi e raccolte di dati. Queste raccolte di dati possono essere file, flussi, array o qualsiasi altro tipo. L'API consente una specifica separata di directory di lavoro input e output. Fornisce la classe generale [inputworkingdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), che gli utenti possono implementare per le loro esigenze specifiche. Inoltre, l'API fornisce implementazioni integrate, che saranno discusse più avanti. L'interfaccia include il metodo [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), che recupera il flusso di dati e determina il nome completo in base a un nome dato, che funge da tasto di mappatura.

### Recupero input di file dal file system disco

Ecco l'approccio che adotteremmo:

Impostare `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output (predefinita: `output`). Applicare prima una licenza. [Licensing](/tex/it/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Impostare `ASPOSE_TEX_INPUT_DIR` sulla cartella con `hello-world.tex` (predefinita: `input`). L’esempio usa plain TeX con `TeXConfig.object_tex()` e genera `hello-world.xps` e `hello-world.log`. Input:

```tex
Hello, World!
\end
```

### Recupero input di file da un archivio zip

Un'altra opzione è archiviare i file di input in un archivio ZIP e trattarli come una directory di input. In tale scenario, dovrebbero essere seguiti i seguenti passaggi:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` indica un archivio con `in/hello-world.tex` (predefinito: `zip-in.zip`). Aprirlo in modalità binaria `rb` e mantenere aperto il flusso fino al termine del lavoro.

Per iniziare, creiamo il flusso contenente il file ZIP. Successivamente, dopo aver creato le opzioni di conversione, assegniamo un'istanza della classe [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) alla proprietà [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). Il secondo parametro del costruttore rappresenta il percorso di base all'interno dell'archivio. Se desideriamo che l'intero archivio funzioni come directory di input, dobbiamo fornire una stringa vuota come argomento.

## L'idea alla base del terminale di input

Ora consideriamo il concetto di input terminale. **Aspose.TeX per Python** definisce l'interfaccia generale [iinputterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) specificamente a questo scopo, che include una singola proprietà che restituisce un'istanza di [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Le implementazioni disponibili saranno discusse in seguito.

### Ottenere l'input del terminale dalla console

Per raggiungere questo obiettivo, dobbiamo assegnare un'istanza della classe [inputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) all'opzione [terminale_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

L’esempio legge una riga con `\read` e la scrive in `texput.xps`. Digitare, ad esempio, `Terminal input works!` nel terminale o fornire la riga tramite input standard. `SCROLL_MODE` consente questa richiesta di input.
