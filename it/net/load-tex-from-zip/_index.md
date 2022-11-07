---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Caricamento di TeX da ZIP | Soluzione API .NET
url: /net/load-tex-from-zip/
description: "Soluzione API .NET per lavorare con TeX. Scopri nell'esempio come caricare un file TeX da ZIP con poche righe di codice C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Carica i file sorgente di TeX da ZIP
h2: ".NET API Soluzione per caricare file TeX dall'archivio ZIP"
---

{{<section overview>}}
---
p1: "TeX è conosciuto come un linguaggio di composizione. Significa che non formatti il ​​tuo testo nel documento, ma inserisci il testo normale insieme ai comandi. Come output, otterrai il file formattato del formato necessario (specificato). Per ottenere una maggiore comprensione dell'input e dell'output di TeX, apprendere [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della Documentazione."
p2: "Come è noto, lo scopo principale di TeX è quello di aiutare a creare testi matematici o tecnici. Ma prima di qualsiasi manipolazione, il file dovrebbe essere prima caricato. Qui troverai frammenti di codice che spiegano come caricare i file sorgente TeX da ZIP utilizzando le directory ZIP per l'input e l'output, l'output su un dispositivo PDF, la scrittura dell'output del terminale sulla console."
p3: "Per caricare i file .tex abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: "Passaggi per caricare TeX da un archivio ZIP C#:"
h3: "Codice C# per caricare TeX"
item1: "Aprire lo stream nell'archivio ZIP per utilizzarlo come directory di lavoro di input."
item2: "Aprire il flusso nell'archivio ZIP per utilizzarlo come directory di lavoro di output."
item3: "Crea opzioni di conversione per il formato ObjectTeX predefinito sull'estensione del motore ObjectTeX utilizzando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metodo di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item4: "Specificare una directory di lavoro dell'archivio ZIP per l'input o/e specificare un percorso all'interno dell'archivio. Utilizzare i costruttori della classe [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) per questo."
item5: "Specificare una directory di lavoro dell'archivio ZIP per l'output o/e specificare un percorso all'interno dell'archivio. Utilizzare i costruttori della classe [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) per questo."
item6: "Specificare la console come terminale di output utilizzando la classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Definire le opzioni di salvataggio utilizzando la classe [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Eseguire il metodo di lavoro [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) per [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Perfeziona l'output.
---