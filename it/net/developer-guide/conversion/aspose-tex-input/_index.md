---
translation: true
template: /templates/_template-net.md
title: Asspose.Tex's Input Interface | .NET
linktitle: Aspose.TeX's Input Interface
weight: 15
url: /net/aspose-tex-input/
description: Funzionalità di conversione della soluzione API Aspose.TeX per .NET con Tex, come un formato di input viene spiegato qui con gli esempi di codice.
keywords: input aspose tex, .net tex, directory di input, zip di input, console di input, opzioni tex, iinputworkingdirectory, inputzipdirectory, inputterminal, conversione tex
lastmod: "2025-06-13"
---

{{<section overview>}}

Si prega di fare riferimento a **Aspose.TeX per .net** [riferimento API](https://reference.aspose.com/tex/net/aspose.tex.io/) per definizioni formali di implementazione I/O.

## Il concetto della directory di input

Poiché i primitivi I/O della lingua tex possono solo gestire i nomi dei file, **aspose.tex per .net** definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IinputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia definisce il metodo [getFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), che restituisce il flusso di dati e determina il nome completo del file, pur assumendo un po ', ipoteticamente diverso, il nome come il primo argomento, che, in effetti, è il tasto di mappatura.

### Ottenere l'input del file dal file system disco

Ecco come lo faremmo:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.cs" >}}

Questo caso d'uso è abbastanza semplice, quindi non c'è più bisogno di concentrarsi su di esso.

### Ottenere l'input di file da un archivio con zip

Possiamo anche mettere i file di input in un archivio ZIP e considerarlo una directory di input. In questo caso, dovremmo procedere come segue:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputZipDirectory.cs" >}}

Innanzitutto, creiamo il flusso contenente il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) per essere un'istanza della classe [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). Il secondo argomento del costruttore è il percorso di base all'interno dell'archivio. Se vogliamo che l'intero archivio sia una directory di input, dovremmo passare la stringa vuota. 

## Il concetto del terminale di input

Ora è il momento di ricordare che c'è anche l'input del terminale. Per quanto riguarda questo, **Aspose.TeX per .NET** definisce l'interfaccia generale [iinputterminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) con una sola proprietà che restituisce un'istanza di implementazione [Textreader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). Le implementazioni a condizione che siano discusse di seguito.

### Ottenere l'input del terminale dalla console

Per fare ciò, dobbiamo impostare l'opzione [Terminalin](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) per essere un'istanza della classe [InputConsoleterminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.cs" >}}

Ma, per dirti la verità, questo è il valore predefinito dell'opzione, quindi non è necessario specificarla. Per questo fatto, e fintanto che non ci sono altre implementazioni, questa sezione ha solo scopi dimostrativi.

Teoricamente, se abbiamo un file TEX interattivo (o script) con un comportamento prevedibile, potremmo voler implementare una versione del terminale di input che contiene uno script complementare per rispondere alle richieste del motore TEX. Prova la tua mano quando hai tempo!