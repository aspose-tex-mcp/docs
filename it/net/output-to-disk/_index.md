---
translation: true
template: /_templates/_output-to-disk-net.md
title: Scrivi output TeX su disco | Soluzione API .NET
url: /net/output-to-disk/
description: "Soluzione API .NET per lavorare con TeX. Scopri nell'esempio come creare un output personalizzato per il file TeX con poche righe di codice C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Scrivi l'output di TeX su disco
h2: "Salva il risultato della conversione del file TeX come disco tramite C# .NET"
---

{{<section overview>}}
---
p1: "TeX è noto come linguaggio di composizione, il che significa che non formatti il ​​testo nel documento, ma inserisci il testo normale insieme ai comandi. Come è noto dall'articolo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) della Documentazione, il lavoro TeX viene eseguito su un file TeX esplicitamente specificato. Lì puoi anche trovare informazioni sulle modalità di interazione di TeX e sulle primitive relative all'input e all'output di TeX."
p2: "L'uso principale di TeX è quello di aiutare con la creazione di testi matematici o tecnici. Ma quando il file è già stato creato e non desideri ulteriori manipolazioni su di esso, potresti voler convertirlo in un formato diverso, più popolare."
p3: "In questa pagina troverai un esempio di codice che spiega l'uso delle directory del file system per l'input e l'output, l'output sul dispositivo XPS, l'override del nome del lavoro, la scrittura dell'output del terminale su disco. In parole semplici, è una conversione con la scrittura dell'output sul disco. Per eseguire tale operazione abbiamo bisogno di:"
p4: "Aspose.TeX per .NET API che è un'API di conversione e manipolazione dei documenti ricca di funzionalità, potente e facile da usare per la piattaforma C#."
p5: "Apri il gestore di pacchetti NuGet e cerca Aspose.TeX e installa. È inoltre possibile utilizzare il seguente comando dalla Console di gestione pacchetti."
---

{{<section feature1>}}
---
title: "Passaggi per scrivere l'output del terminale sul disco C#:"
h3: "Codice C# per convertire TeX e scrivere l'output sul disco"
item1: "Crea opzioni di conversione sull'estensione del motore ObjectTeX utilizzando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Metodo di [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item2: "Specificare un nome lavoro se non si desidera che il primo argomento del costruttore TeXJob venga preso come nome lavoro."
item3: "Specificare una directory di lavoro del file system per l'input. Utilizzare la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) per questo."
item4: "Specificare una directory di lavoro del file system per l'output con l'aiuto delle entità della classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Specificare che l'output del terminale deve essere scritto in un file nella directory di lavoro dell'output."
item6: "Eseguire il metodo di lavoro [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) per [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---