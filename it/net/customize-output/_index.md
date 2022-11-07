---
translation: true
template: /_templates/_customize-output-net.md
title: Crea output personalizzato TeX | Soluzione API .NET
url: /net/customize-output/
description: "Soluzione API .NET per lavorare con TeX. Leggi l'esempio su come creare un output personalizzato per il file TeX con poche righe di codice C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizza l'output
h2: ".NET API Soluzione per personalizzare l'output dei file TeX"
---

{{<section overview>}}
---
p1: "TeX è conosciuto come un linguaggio di composizione. Significa che non formatti il ​​tuo testo nel documento, ma inserisci il testo normale insieme ai comandi."
p2: "L'articolo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della Documentazione ci insegna che un file TeX può non contenere dati da comporre ma solo sequenze di controllo . Tuttavia di solito contiene tali dati e un file nel formato di destinazione ha il testo digitato. Il file avrà anche lo stesso nome del file specificato come input ed è il file di output principale. Per il TeX originale, questo è un file in formato DVI. Chiameremo il nome dei file di input e di output senza estendere il nome del lavoro."
p3: "In questa pagina troverai un esempio di codice che spiega la creazione di un file in formato TeX personalizzato in cui puoi vedere come personalizzare l'output dei file TeX. Per personalizzare l'output dei file .tex abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: "Passaggi per personalizzare l'output di TeX C#:"
h3: "Codice C# per la personalizzazione dell'output TeX"
item1: "Con l'aiuto del metodo [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe, crea opzioni del motore TeX per nessun formato sull'estensione del motore ObjectTeX."
item2: "Utilizzare la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) per specificare una directory di lavoro del file system per l'input."
item3: "Utilizzare la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) per specificare una directory di lavoro del file system per l'output."
item4: "Per creare il nuovo formato, utilizzare il metodo [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Perfeziona l'output.
---