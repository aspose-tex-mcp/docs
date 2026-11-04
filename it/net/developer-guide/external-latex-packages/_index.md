---
translation: true
template: /templates/_template-net.md
title: Pacchetti LaTeX esterni | Aspose.TeX per .NET
linktitle: Pacchetti di LaTeX esterni
weight: 20
url: /net/external-latex-packages/
description: API Aspose.TeX per .NET consente l'utilizzo di pacchetti esterni, ovvero quelli non inclusi nella libreria stessa come pacchetti FancyBox e PGFPLOTS.
keywords: pacchetti latex esterni, aspose tex, .net tex, pacchetti latex, fancybox, pgfplots, directory di input richiesta, zip di input, directory di input personalizzata, conversione tex
lastmod: "2026-11-04"
---

{{<section overview>}}

## Pacchetti di LaTeX esterni

La libreria **Aspose.TeX** include un numero di [pacchetti di LaTeX comuni](/tex/{{lang.url-fragment}}net/embedded-packages/). Quindi non devi preoccuparti di come fornire questi pacchetti al TeX machine della biblioteca. Ma a volte (o abbastanza spesso) il tuo file LaTeX può richiedere un pacchetto oltre il pacchetto "supportato in modo nativo" dei pacchetti. In tal caso, è possibile provare a fornire l'input richiesto, ovvero i file di origine del pacchetto richiesti, tramite l'opzione [RequiredInputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/) dell'istanza di classe [TeXOptions](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/). Vedremo come funziona con due esempi.

### Input richiesto non pacchettato (pacchetto `FancyBox`)

Diciamo che abbiamo il seguente semplice file in LaTeX, che è `richiesto-input-fs.tex` dalla nostra [soluzione di esempio](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

Nella terza riga, possiamo vedere che il file richiede il pacchetto `FancyBox`, che non è" nativo "supportato. Supponiamo anche che abbiamo il file di origine del pacchetto `FancyBox`. È un pacchetto semplice, quindi consiste davvero in un singolo file. Possiamo posizionare questo file ovunque nel nostro file system e specificare il percorso della directory come mostrato di seguito:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Dopo aver eseguito un TeX job con questa opzione (non dimenticare di regolare le altre opzioni secondo necessità), otteniamo il documento di output (ovvero un'immagine PNG).

![Documento di output](/tex/images/net/Conversion-RequiredInputFs.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Input richiesto archiviato (pacchetto `pgfplots`)

Diciamo ora che abbiamo anche il seguente file in LaTeX abbastanza semplice, che è "richiesto-input-zip.tex` dalla nostra soluzione di esempio:


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```


Nella terza riga, possiamo vedere che il file richiede il pacchetto `pgfplots`, che non è anche" nativo "supportato. Ancora una volta, supponiamo che abbiamo i file di origine del pacchetto `pgfplots`. È un numero piuttosto elevato di file che sono divisi tra due posizioni se le si trovano nella directory di installazione di qualsiasi applicazione di composizione in LaTeX. Puoi trovare la cartella `pgfplots` nelle cartelle`\tex\generic` e `\tex\latex`. E il contenuto di entrambe queste cartelle deve essere fornito come input richiesto alla libreria Aspose.TeX. Vogliamo che questi file di origine siano confezionati in un archivio con zip, quindi ecco il layout dell'archivio:

![Layout dell'archivio](/tex/images/net/pgfplots-zip-layout.png)

Ed è così che specifichiamo l'accesso a questi file di origine:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Dopo aver eseguito un TeX job con questa opzione, otteniamo il documento di output:

![Documento di output](/tex/images/net/Conversion-RequiredInputZip.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_NOTA:_** Il risultato è stato verificato utilizzando il pacchetto `pgfplots` versione 1.18.1. Mentre la versione del pacchetto `pfg` inclusa nella libreria **Aspose.TeX** è la 3.1.9a.

### Impiegando pacchetti di caratteri esterni

Di norma, le distribuzioni in LaTeX forniscono una serie di caratteri predefiniti disponibili per la composizione. Tranne questi caratteri, **Aspose.TeX** include una serie di pacchetti di carattere non standard. Ad esempio, `amsfonts`,` eurosym` e `wasysym`. Come abbiamo visto sopra, Aspose.TeX consente anche di impiegare pacchetti esterni. Ma soprattutto stavamo parlando di pacchetti che non contengono caratteri.
**Aspose.TeX** 's*Object TeX*Il motore estensione ha bisogno di mappe dei caratteri (che sono file di testo in un determinato formato con l'estensione `.map` per convenzione) per determinare quali caratteri fisici corrispondono al nome del carattere interno di ciascun tex. Queste mappe dei caratteri devono essere caricate nella TeX memory durante la fase di inizializzazione. E, naturalmente, devono essere presenti tra i file del pacchetto che si sta collegando. Poiché il motore non conosce i nomi di tutte le mappe dei caratteri, cerca tutti i file con l'estensione `.map`. Pertanto, un'implementazione dell'interfaccia [IInputWorkingDirectory](https://reference.aspose.com/tex/net/Aspose.TeX.io/iinputworkingdirectory/) che viene utilizzata come valore dell'opzione [RequiredInputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/) deve fornire un modo per accedere alle raccolte di nomi di file per estensione. Più specificamente, questa implementazione deve anche implementare l'interfaccia [IFileCollector](https://reference.aspose.com/tex/net/Aspose.TeX.io/ifilecollector/). Le implementazioni standard - [InputFileSystemDirectory](https://reference.aspose.com/tex/net/Aspose.TeX.io/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/net/Aspose.TeX.io/inputzipdirectory/) - lo fanno già.

Di seguito, forniamo un esempio illustrativo di una directory di input richiesta personalizzata che implementa anche l'interfaccia [IFileCollector](https://reference.aspose.com/tex/net/Aspose.TeX.io/ifilecollector/). Mentre ci concentriamo sulla raccolta dei nomi dei file per estensione, omettiamo intenzionalmente i dettagli di archiviazione e recupero dei file.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}


### Restrizioni

Può succedere che un pacchetto richiesto dal tuo file LaTeX sia sviluppato sotto il kernel *LaTeX3e*. Molto probabilmente tale pacchetto non funzionerà con la libreria **Aspose.TeX** poiché quest'ultima si basa sul kernel*LaTeX2e*.

Può anche succedere che un pacchetto richiesto dal file LaTeX chiami direttamente comandi primitivi dipendenti dal dispositivo che non sono supportati dal motore Object TeX della biblioteca Aspose.TeX. Tale pacchetto, sfortunatamente, non funzionerà sicuramente.

## Creazione di un agente AI per l'ottimizzazione dei pacchetti LaTeX incorporati

Se è necessario creare un agente AI che ottimizzi il contenuto per l'inventario di pacchetti integrato senza lente ricerche dinamiche di rete o nel file system durante la generazione, è possibile utilizzare il flusso di lavoro descritto di seguito.

Invece di costringere un LLM a indovinare quali pacchetti siano sicuri o veloci da usare, l'agente si basa su questo specifico inventario di pacchetti precompilati per evitare errori dovuti a pacchetti mancanti.

![Architettura di assemblaggio del documento con agente AI incorporato](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png)

1. Estrazione dell'intento di layout (livello di analisi LLM)
L'utente fornisce dati non strutturati in più formati o direttive conversazionali. L'LLM associa direttamente le richieste all'elenco dei pacchetti incorporati di Aspose (`colortbl` per l'ombreggiatura delle righe, `geometry` per i margini e `multirow` per le celle che occupano più righe).

2. Isolamento AST e iniezione del preambolo
Anziché scrivere importazioni di pacchetti ingombranti, l'agente verifica i requisiti del codice rispetto all'elenco dei pacchetti incorporati.
Scrive nel preambolo solo i comandi `\usepackage` necessari.

3. Sandboxing ed esecuzione dello stream (nodo motore Aspose.TeX)
Il codice sorgente LaTeX viene passato a un `TeXJob` come flusso, con `TeXOptions` creato per `TeXConfig.ObjectLaTeX`. `TeXJob.Run()` è sincrono, quindi l'agente lo esegue in un worker in background.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,multirow,colortbl}
```

4. Serializzazione delle risorse (Livello di rendering dell'output)
Il processo scrive il risultato con un dispositivo di output, come `PdfDevice` o `SvgDevice`, e l'agente lo restituisce al client.