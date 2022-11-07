---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Funzionalità di composizione di TeX | API .NET
url: /net/typeset-tex-files/
description: "Soluzione API .NET per lavorare con TeX. Scopri nell'esempio come creare set di testo TeX con poche righe di codice C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Digita i file TeX
h2: "Digita un file TeX utilizzando un formato TeX personalizzato C# .NET"
---

{{<section overview>}}
---
p1: "TeX è conosciuto come uno dei linguaggi di markup dei dati e/o un linguaggio di composizione allo stesso tempo. Significa che non formatti il ​​tuo testo nel documento, ma inserisci il testo normale insieme ai comandi. Come output, otterrai il file formattato del formato necessario (specificato). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) è il nucleo centrale del sistema di pubblicazione (composizione computerizzata)."
p2: "Per ottenere una maggiore comprensione della composizione di TeX, leggere [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della Documentazione. E in questa pagina troverai frammenti di codice che spiegano come comporre un file TeX utilizzando un formato TeX personalizzato."
p3: "Per eseguire gli esempi abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: Passaggi per comporre TeX usando C#.
h3: "Codice C# per la composizione di TeX"
item1: "Crea il provider di formato utilizzando la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Crea opzioni di conversione per un formato personalizzato sull'estensione del motore ObjectTeX utilizzando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metodo di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item3: "Specificare la directory di lavoro di input se l'input principale non viene fornito come flusso. Utilizzare la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) per questo."
item4: "Specificare una directory di lavoro del file system per l'output. Utilizzare la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) per questo."
item5: "Eseguire il metodo di lavoro [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) per [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Perfeziona l'output.
---