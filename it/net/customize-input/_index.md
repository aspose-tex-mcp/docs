---
translation: true
template: /_templates/_customize-input-net.md
title: Crea input personalizzato TeX | API .NET
url: /net/customize-input/
description: "Soluzione API .NET per lavorare con TeX. Scopri nell'esempio come creare un input personalizzato per il file TeX con poche righe di codice C#."
keywords: input personalizzato tex net api, api C# per personalizzare tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizza input
h2: ".NET API Soluzione per personalizzare l'input di file TeX"
---

{{<section overview>}}
---
p1: "TeX è conosciuto come un linguaggio di composizione. Significa che non formatti il ​​tuo testo nel documento, ma inserisci il testo normale insieme ai comandi. Come descritto nell'articolo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della documentazione, il lavoro TeX viene eseguito su un file TeX esplicitamente specificato. Quindi, includiamo questo file nell'input di un certo lavoro TeX."
p2: "In questa pagina troverai un esempio di codice che spiega come personalizzare l'input dei file sorgente TeX tenendo conto che l'input dovrebbe seguire la sintassi TeX e, idealmente, contenere solo comandi noti al motore."
p3: "Per personalizzare l'input dei file .tex abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: "Passaggi per personalizzare l'input TeX C#:"
h3: "Codice C# per la personalizzazione dell'input TeX"
item1: "Utilizzo di [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metodo di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe, crea opzioni del motore TeX per nessun formato sull'estensione del motore ObjectTeX."
item2: "Utilizzando la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), specificare una directory di lavoro del file system per l'input."
item3: "Con l'aiuto del metodo [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), creare il formato personalizzato."
---