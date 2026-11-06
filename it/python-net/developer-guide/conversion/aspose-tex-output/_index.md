---
translation: true
template: /templates/_template-python-net.md
title: Aspose.TeX's Output Interface | Python tramite .NET
linktitle: Aspose.TeX's Output Interface
weight: 16
url: /python-net/aspose-tex-output/
description: Ecco una spiegazione della funzionalità di conversione della soluzione API Aspose.Tex per Python, con Tex come formato di output, con esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}


> Per le definizioni formali dell'implementazione I/O, fare riferimento al [riferimento API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) di **Aspose.TeX per Python**.

## L'idea alla base della directory di output

Aspose.TeX definisce una directory come una mappatura tra nomi e numeri di dati, in cui le buse dei dati possono essere file, flussi, array o altri tipi di dati. L'API consente la specifica di directory di lavoro input e output separate. Per l'output, l'API fornisce l'interfaccia generale [IoutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), che può essere implementata dall'utente per le loro esigenze specifiche. Inoltre, l'API fornisce implementazioni pronte all'uso, che saranno discusse di seguito. L'interfaccia * IoutputWorkingDirectory * estende [iInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), poiché il motore può prima creare e scrivere un file e quindi riatterlo. L'interfaccia include il metodo [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), che restituisce il flusso per scrivere, in contrasto con il metodo [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), che restituisce il flusso da leggere.

### Salvare l'output come file nel file system disco

Come accennato [sopra](/tex/{{lang.url-fragment}}net/latex-to-image/), la [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) è comunemente impostata come istanza della classe [outputfilesystemdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Ecco come lo imposteremmo:

Impostare `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output (predefinita: `output`). Applicare prima una licenza. [Licensing](/tex/it/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Il flusso plain TeX incluso genera `texput.xps` e `texput.log` nella directory di output.

### Salvare l'output come file di archivio zip.

Un'altra opzione è quella di creare un file o uno streaming e utilizzarlo come archivio zip per archiviare i file di output. Ecco un esempio:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

`zip-xps-out.zip` viene aperto in modalità binaria `wb`. Chiamare `finish()` su `OutputZipDirectory` prima di chiudere il flusso. L’archivio contiene `texput.xps` e `texput.log`.

Per iniziare, creiamo un flusso di output per il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione * output_working_directory * per essere un'istanza della classe [outputzipdirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## L'idea alla base del terminale di uscita

L'output del terminale è un altro aspetto importante dell'output. Per questo, **Aspose.TeX per Python** definisce l'interfaccia generale [IoutPutterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), che ha una singola proprietà che restituisce un'istanza dell'implementazione [Terminalwriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). Le implementazioni disponibili saranno discusse di seguito.

### Scrivere l'output del terminale sulla console

Per raggiungere questo obiettivo, dobbiamo impostare l'opzione [terminale_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) come istanza della classe [outputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Ancora una volta, questo è il valore predefinito dell'opzione, quindi non è necessario specificarlo. Pertanto, questa sezione è fornita esclusivamente a fini dimostrativi.

### Scrivere l'output del terminale in un file

Contrariamente al terminale di input, **Aspose.TeX per Python** include un'implementazione dell'interfaccia*IoutPutterminal*che ci consente di scrivere l'output del terminale in un file all'interno di una directory di output specificata.

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}}

Il costruttore di `OutputFileTerminal` riceve la directory di lavoro di output e vi scrive `texput.trm`, accanto a `texput.xps` e `texput.log`.
