---
translation: true
template: /templates/_template-java.md
title: Pacchetti in LaTeX esterni | Java
linktitle: Pacchetti di LaTeX esterni
weight: 30
url: /java/external-latex-packages/
description: API Aspose.TeX per Java consente l'uso di pacchetti esterni, ovvero quelli che non sono inclusi nella libreria stessa come pacchetti FancyBox o PGFPLOTS.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Pacchetti di LaTeX esterni

Esiste un certo numero di [pacchetti di LaTeX comuni](/tex/{{lang.url-fragment}}net/embedded-packages/) inclusi nella libreria **aspose.tex** per java. Quindi non devi prenderti cura di come fornire questi pacchetti al motore Tex della biblioteca. Ma a volte (forse spesso) il tuo file in LaTeX può richiedere un pacchetto oltre il pacchetto "supportato in modo nativo" dei pacchetti. In questo caso, è possibile provare a fornire l'input richiesto, ovvero i file di origine del pacchetto richiesti, utilizzando il metodo [setrequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) dell'istanza di classe [Texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Vedremo come funziona con due esempi.

Impostare `inputFile` sul percorso completo del documento LaTeX corrispondente e `outputDirectory` su una cartella di output esistente. Entrambi gli esempi di conversione generano PNG a 150 DPI. Importare le classi Aspose.TeX utilizzate nell’esempio scelto, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions` e, per l’input ZIP, `java.io.InputStream` e `java.nio.file.Files`. Gestire o dichiarare le eccezioni nel metodo chiamante. Applicare una licenza secondo la [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/).

### Input richiesto non pacchettato (pacchetto `FancyBox`)

Diciamo che abbiamo il seguente semplice file in LaTeX, che è `richiesto-input-fs.tex` dalla nostra [soluzione di esempio](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

La terza riga richiede il pacchetto esterno `fancybox`. Impostare `packagesDirectory` su una cartella locale con `fancybox.sty` e le sue dipendenze. L’esempio completo seguente assegna questa cartella a `RequiredInputDirectory` e genera un’immagine PNG. Il dispositivo e le directory di lavoro rimangono aperti fino al termine del lavoro, quindi vengono rilasciati o chiusi.

![Documento di output](/tex/images/java/Conversion-RequiredInputFs.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-FileSystem.java" >}}

### Input richiesto archiviato (pacchetto `pgfplots`)

Supponiamo ora che abbiamo anche il seguente file in LaTeX abbastanza semplice, che è `richiesto Input-Zip.tex` dalla nostra soluzione di esempio:


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

Nella terza riga, vediamo che il file richiede il pacchetto `pgfplots`, che non è anche" nativo "supportato. Ancora una volta, supponiamo che abbiamo i file di origine del pacchetto `pgfplots`. È una serie piuttosto ampia di file che sono divisi tra due posizioni se le si trovano nella directory di installazione di qualsiasi applicazione di composizione in LaTeX. Puoi trovare la cartella `pgfplots` nelle cartelle`\tex\generic` e `\tex\latex`. E il contenuto di entrambe queste cartelle deve essere fornito come input richiesto alla libreria ASPIPE.Tex. Vogliamo che questi file di origine siano confezionati in un archivio con zip, quindi ecco il layout dell'archivio:

![Layout dell'archivio](/tex/images/java/pgfplots-zip-layout.png)

Impostare `packagesZip` su un `java.nio.file.Path` all’archivio contenente i sorgenti generici e LaTeX del pacchetto. L’esempio Java completo seguente lo apre con `Files.newInputStream(...)` e assegna un `InputZipDirectory` a `RequiredInputDirectory`. L’argomento del percorso base vuoto seleziona l’intero archivio. Tenere aperti il flusso ZIP e la directory fino al termine del lavoro TeX, quindi chiuderli. Il risultato è un’immagine PNG con i due grafici.

![Documento di output](/tex/images/java/Conversion-RequiredInputZip.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-Zip.java" >}}

> **_NOTA:_** Il risultato è stato verificato utilizzando il pacchetto `pgfplots` versione 1.18.1. Mentre la versione del pacchetto `pfg` inclusa nella libreria **Aspose.TeX** è la 3.1.9a.

### Utilizzo di pacchetti di caratteri esterni

In genere, le distribuzioni in LaTeX sono dotate di una selezione di caratteri predefiniti che possono essere utilizzati per la composizione. Oltre a questi caratteri, **Aspose.TeX** offre diversi pacchetti di caratteri non standard, come `amsfonts`,` eurosym` e `wasysym`. Come accennato in precedenza, **Aspose.TeX** supporta anche l'uso di pacchetti esterni, sebbene la nostra attenzione sia stata principalmente su pacchetti che non includono caratteri.

L'estensione del motore *Object TeX* in **Aspose.TeX** richiede mappe di font, ovvero file di testo con estensione `.map` che specificano i font fisici corrispondenti al nome di ciascun font interno di TeX. Queste mappe di font devono essere caricate nella memoria di TeX durante la fase di inizializzazione e devono essere incluse nei file del pacchetto. Poiché il motore non conosce i nomi di tutte le mappe di font, cerca tutti i file con estensione `.map`. Pertanto, l'implementazione dell'interfaccia [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) utilizzata come valore dell'opzione [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) deve fornire un modo per accedere a raccolte di nomi di file in base alla loro estensione. Nello specifico, questa implementazione deve implementare anche l'interfaccia [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Le implementazioni standard, [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), soddisfano già questo requisito.

Il `RequiredInputDirectory` personalizzato seguente implementa entrambe le interfacce e legge file locali registrati esplicitamente. Salvarlo come `RequiredInputDirectory.java` con gli import inclusi. Registrare ogni file con `storeFileName(...)`, assegnare l’istanza con `options.setRequiredInputDirectory(...)` e chiuderla dopo il lavoro. È un registro piatto: i nomi dei file devono essere univoci quando richiesti senza un percorso completo. Le estensioni vengono confrontate senza distinguere maiuscole e minuscole; il percorso di raccolta facoltativo seleziona una directory del file system. Registrare tutti i file necessari di pacchetti, mappe dei font, metriche e font fisici. La raccolta rende individuabili le mappe, ma non fornisce dati dei font mancanti.

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInputDirectory.java" >}}

### Restrizioni

Un pacchetto richiesto dal file LaTex può essere sviluppato sotto il kernel *LaTeX3e*. Molto probabilmente tale pacchetto non funzionerà con la libreria **aspose.tex** poiché quest'ultima si basa sul kernel*LaTeX2e*.

Inoltre, un pacchetto richiesto dal file Latex può chiamare direttamente comandi primitivi dipendenti dal dispositivo che non sono supportati dal motore*oggetto*della libreria*della libreria **. Tale pacchetto, sfortunatamente, non funzionerà sicuramente.