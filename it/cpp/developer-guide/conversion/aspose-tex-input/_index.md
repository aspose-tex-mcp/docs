---
translation: true
template: /templates/_template-cpp.md
title: Asspose.Tex's Input Interface | C++
linktitle: Aspose.TeX's Input Interface
weight: 15
url: /cpp/aspose-tex-input/
description: Funzionalità di conversione della soluzione API Aspose.TeX per C++ con Tex, come formato di input, è spiegata qui con gli esempi di codice.
lastmod: "2026-04-20"
---

{{<section overview>}}

Si prega di fare riferimento a **Aspose.TeX per C ++** [Riferimento API](https://reference.aspose.com/tex/cpp/aspose.tex.io/) per definizioni formali di implementazione I/O.

## Il concetto della directory di input

Poiché i primitivi I/O della lingua tex possono solo gestire i nomi dei file, **aspy.tex per C ++** definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IinputworkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/), che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia definisce il metodo [getFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/getfile/), che restituisce il flusso di dati e determina il nome completo del file, pur assumendo un po ', ipoteticamente diverso, il nome come il primo argomento, che, in effetti, è il tasto di mappatura.

### Ottenere l'input del file dal file system disco

Ecco come lo faremmo:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));

```

Questo caso d'uso è abbastanza semplice, quindi non c'è più bisogno di concentrarsi su di esso.

### Ottenere l'input di file da un archivio con zip

Possiamo anche mettere i file di input in un archivio ZIP e considerarlo una directory di input. In questo caso, dovremmo procedere come segue:

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Innanzitutto, creiamo il flusso contenente il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/) per essere un'istanza della classe [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory/). Il secondo argomento del costruttore è il percorso di base all'interno dell'archivio. Se vogliamo che l'intero archivio sia una directory di input, dovremmo passare la stringa vuota. 

## Il concetto del terminale di input

Ora è il momento di ricordare che c'è anche l'input del terminale. Per quanto riguarda questo, **Aspose.TeX per C ++** definisce l'interfaccia generale [iinputterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal/) con una sola proprietà che restituisce un'istanza di implementazione [Textreader](https://reference.aspose.com/tex/cpp/system.io/textreader/). Le implementazioni a condizione che siano discusse di seguito.

### Ottenere l'input del terminale dalla console

Per fare ciò, dobbiamo impostare l'opzione [Terminalin](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin/) per essere un'istanza della classe [InputConsoleterminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputconsoleterminal/).

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

Ma, per dirti la verità, questo è il valore predefinito dell'opzione, quindi non è necessario specificarla. :-) A causa di questo fatto, e fintanto che non ci sono altre implementazioni, questa sezione ha solo scopi dimostrativi.

Teoricamente, se abbiamo un file TEX interattivo (o script) con un comportamento prevedibile, potremmo voler implementare una versione del terminale di input che contiene uno script complementare per rispondere alle richieste del motore TEX. Prova la tua mano quando hai tempo!