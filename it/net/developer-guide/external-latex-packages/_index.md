---
translation: true
template: /templates/_template-net.md
title: Pacchetti in LaTeX esterni | .NETTO
linktitle: Pacchetti di LaTeX esterni
weight: 20
url: /net/external-latex-packages/
description: API ASPUSE.TEX per .NET consente l'utilizzo di pacchetti esterni, ovvero quelli non inclusi nella libreria stessa come pacchetti FancyBox e PGFPLOTS.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Pacchetti di LaTeX esterni

La libreria **aspose.tex** include un numero di [pacchetti di LaTeX comuni](/tex/{{lang.url-fragment}}net/embedded-packages/). Quindi non devi preoccuparti di come fornire questi pacchetti al motore Tex della biblioteca. Ma a volte (o abbastanza spesso) il tuo file LaTeX può richiedere un pacchetto oltre il pacchetto "supportato in modo nativo" dei pacchetti. In tal caso, è possibile provare a fornire l'input richiesto, ovvero i file di origine del pacchetto richiesti, tramite l'opzione [RebledInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) dell'istanza di classe [Texoptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Vedremo come funziona con due esempi.

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

Dopo aver eseguito un lavoro Tex con questa opzione (non dimenticare di regolare le altre opzioni secondo necessità), otteniamo il documento di output (ovvero un'immagine PNG).

![Documento di output](/tex/images/net/Conversion-RequiredInputFs.png)

Ecco il codice sorgente completo per l'esempio:

{{<gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""aspose.tex.examples-conversion-requiredinput-filesystem.cs">}}}}}}}}}}}}}}}}}}

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


Nella terza riga, possiamo vedere che il file richiede il pacchetto `pgfplots`, che non è anche" nativo "supportato. Ancora una volta, supponiamo che abbiamo i file di origine del pacchetto `pgfplots`. È un numero piuttosto elevato di file che sono divisi tra due posizioni se le si trovano nella directory di installazione di qualsiasi applicazione di composizione in LaTeX. Puoi trovare la cartella `pgfplots` nelle cartelle`\tex\generic` e `\tex\latex`. E il contenuto di entrambe queste cartelle deve essere fornito come input richiesto alla libreria ASPIPE.Tex. Vogliamo che questi file di origine siano confezionati in un archivio con zip, quindi ecco il layout dell'archivio:

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

Dopo aver eseguito un lavoro Tex con questa opzione, otteniamo il documento di output:

![Documento di output](/tex/images/net/Conversion-RequiredInputZip.png)

Ecco il codice sorgente completo per l'esempio:

{{<gist "aspose-com-gisti""76c7e5770ac8b3f6d409f6ec60f02030""aspose.tex.examples-conversion-requiredinput-zip.cs">}}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### Impiegando pacchetti di caratteri esterni

Di norma, le distribuzioni in LaTeX forniscono una serie di caratteri predefiniti disponibili per la composizione. Tranne questi caratteri, **Aspose.TeX** include una serie di pacchetti di carattere non standard. Ad esempio, `amsfonts`,` eurosym` e `wasysym`. Come abbiamo visto sopra, Aspose.TeX consente anche di impiegare pacchetti esterni. Ma soprattutto stavamo parlando di pacchetti che non contengono caratteri.
**aspose.tex** 's*Object tex*Il motore estensione ha bisogno di mappe dei caratteri (che sono file di testo in un determinato formato con l'estensione `.map` per convenzione) per determinare quali caratteri fisici corrispondono al nome del carattere interno di ciascun tex. Queste mappe dei caratteri devono essere caricate nella memoria di Tex durante la fase di inizializzazione. E, naturalmente, devono essere presenti tra i file del pacchetto che si sta collegando. Poiché il motore non conosce i nomi di tutte le mappe dei caratteri, cerca tutti i file con l'estensione `.map`. Pertanto, un'implementazione dell'interfaccia [IinputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) che viene utilizzata come valore dell'opzione [RecomeInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) deve fornire un modo per accedere alle raccolte di nomi di file per estensione. Più specificamente, questa implementazione deve anche implementare l'interfaccia [IfileCollector (10). Le implementazioni standard - [InputFilesystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) e [inputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - lo fanno già.

Di seguito, forniamo un esempio illustrativo di una directory di input richiesta personalizzata che implementa anche l'interfaccia [IfileCollector (13). Mentre ci concentriamo sulla raccolta dei nomi dei file per estensione, omettiamo intenzionalmente i dettagli di archiviazione e recupero dei file.

{{<gist "aspose-com-gisti""76c7e5770ac8b3f6d409f6ec60f02030""aspose.tex.examples-conversion-requiredInputDirectory.cs">}}}}}}}}}}}}}}}}}}

### Restrizioni

Può succedere che un pacchetto richiesto dal tuo file LaTeX sia sviluppato sotto il kernel *LaTeX3e*. Molto probabilmente tale pacchetto non funzionerà con la libreria **aspose.tex** poiché quest'ultima si basa sul kernel*LaTeX2e*.

Può anche succedere che un pacchetto richiesto dal file Latex chiama direttamente comandi primitivi dipendenti dal dispositivo che non sono supportati dal motore*oggetto*della libreria*della libreria **. Tale pacchetto, sfortunatamente, non funzionerà sicuramente.