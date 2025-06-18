---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX's Output Interface | .NETTO
linktitle: Aspose.TeX's Output Interface
weight: 16
url: /net/aspose-tex-output/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per .NET con Tex, come un formato di output è spiegato qui con gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

Si prega di fare riferimento a **Aspose.TeX per .net** [riferimento API](https://reference.aspose.com/tex/net/aspose.tex.io/) per definizioni formali di implementazione I/O.

## Il concetto della directory di output

Poiché i primitivi I/O della lingua tex possono solo affrontare i nomi dei file, Aspose.Tex definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IoutputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) per l'output, che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia estende [IinputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), poiché il motore può prima creare e scrivere un file, quindi riatterlo. Il metodo dell'interfaccia [getOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) restituisce il flusso in cui scrivere, al contrario del flusso per leggere restituito da [getFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Scrivere l'output di file sul file system disco

Come accennato [sopra](/tex/{{lang.url-fragment}}net/latex-to-png/), il valore più comune per la [outputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) sarebbe probabilmente un'istanza della classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Ecco come lo imposteremmo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Questo caso d'uso è abbastanza semplice, quindi non c'è più bisogno di concentrarsi su di esso.

### Scrivere l'output di file in un archivio zip

Possiamo anche creare un file (o streaming) e lasciare che il motore TEX lo utilizzi come archivio zip per archiviare i file di output. Ecco qui:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Innanzitutto, creiamo un flusso di output per il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) per essere un'istanza della classe [OutputzipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## Il concetto del terminale di output

C'è un'altra parte importante dell'uscita --- l'output del terminale. Per quanto riguarda questo, **Aspose.TeX per .NET** definisce l'interfaccia generale [IoutPutterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) con una sola proprietà che restituisce un'istanza di implementazione [Textwriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). Le implementazioni a condizione che siano discusse di seguito.

### Scrivere l'output del terminale sulla console

Per fare ciò, dobbiamo impostare l'opzione [terminale](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) per essere un'istanza della classe [outputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Ancora una volta, questo è il valore predefinito dell'opzione, quindi non è necessario specificarlo. Per questo motivo, questa sezione ha solo scopi dimostrativi.

### Scrivere l'output del terminale in un file

A differenza del terminale di input, **Aspose.TeX per .NET** fornisce un'implementazione di [IoutPutterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), che ci consente di scrivere l'output del terminale in un file in una directory di output.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Qui chiediamo al motore TEX di scrivere l'output del terminale nel file con il nome [<Bob_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .TRM, che verrà archiviato nella stessa directory di output che abbiamo specificato per il resto dell'output. Ma questo non è necessario. Potremmo anche passare qualsiasi altra istanza di qualsiasi implementazione di [IoutPutterminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) al costruttore.