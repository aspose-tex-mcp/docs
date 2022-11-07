---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Caricamento di TeX da un disco | API .NET
url: /net/load-tex-from-disk/
description: "Soluzione API .NET per lavorare con TeX. Scopri nell'esempio come caricare un file TeX dal disco con poche righe di codice C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Carica i file sorgente di TeX dal disco
h2: ".NET API Soluzione per caricare file TeX/LaTeX dal disco"
---

{{<section overview>}}
---
p1: "TeX è conosciuto come un linguaggio di composizione. Significa che non formatti il ​​tuo testo nel documento, ma inserisci il testo normale insieme ai comandi. Come output, otterrai il file formattato del formato necessario (specificato). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) è il nucleo centrale del sistema di pubblicazione (composizione computerizzata). Un lavoro TeX viene eseguito su un file TeX esplicitamente specificato. Per ottenere una maggiore comprensione dell'input e dell'output di TeX, apprendere [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della Documentazione."
p2: "Come è noto, lo scopo principale di TeX è quello di aiutare a creare testi matematici o tecnici. Ma prima di qualsiasi manipolazione, il file dovrebbe essere prima caricato. Qui troverai frammenti di codice che spiegano come caricare i file sorgente di TeX dal disco utilizzando le directory del file system per input e output, l'output sul dispositivo XPS, la scrittura dell'output del terminale sulla console."
p3: "Per eseguire gli esempi abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: Passaggi per caricare TeX da un disco C#.
h3: "Codice C# per caricare TeX"
item1: "Crea opzioni di conversione per un formato personalizzato sull'estensione del motore ObjectTeX utilizzando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metodo di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item2: "Specificare una directory di lavoro del file system per l'input. Utilizzare la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) per questo."
item3: "Specificare una directory di lavoro del file system per l'output utilizzando la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Specificare la console come terminale di output utilizzando la classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Specificare un terminale di memoria come terminale di uscita, se necessario. Per questo utilizzare la classe [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Eseguire il metodo di lavoro [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) per [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Perfeziona l'output.
---