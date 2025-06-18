---
translation: true
template: /templates/_template-python-net.md
title: Pacchetti in LaTeX esterni | Python
linktitle: Pacchetti di LaTeX esterni
weight: 19
url: /python-net/external-latex-packages/
description: API ASPUSE.TEX per Python supporta l'uso di pacchetti esterni che non sono inclusi nella biblioteca stessa, come i pacchetti FancyBox e PGFPlots
lastmod: "2025-06-13"
---

{{<section overview>}}

## Pacchetti di LaTeX esterni

La libreria **Aspose.TeX** viene fornita con una varietà di [pacchetti in LaTeX comuni](/tex/{{lang.url-fragment}}net/embedded-packages/), quindi non è necessario fornire manualmente questi pacchetti al motore TEX. Tuttavia, potrebbero esserci situazioni in cui il tuo file latex richiede un pacchetto che non è incluso nel "pacchetto" della biblioteca dei pacchetti. In tali casi, è possibile provare a fornire l'input necessario, come i file di origine del pacchetto richiesto, tramite l'opzione [Remow_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) dell'istanza di classe [texoptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Esploreremo come funziona con due esempi.

### Input richiesto fornito in una forma non impacchettata (il pacchetto `FancyBox`).

Supponiamo di avere il seguente file in LaTeX di base denominato `richiesto-input-fs.tex`, che fa parte della nostra [soluzione di esempio](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

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

La terza riga del file indica che richiede il pacchetto `FancyBox`, che non è incluso nel supporto" nativo ". Supponiamo che abbiamo il file di origine per il pacchetto `FancyBox`. Poiché si tratta di un pacchetto semplice costituito da un singolo file, possiamo posizionare questo file ovunque nel nostro file system e specificare il percorso della directory come segue:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Una volta eseguito un lavoro Tex con questa opzione (ricorda di regolare le altre opzioni se necessario), otterremo il documento di output, che in questo caso è un'immagine PNG.

![Documento di output](/tex/images/python-net/Conversion-RequiredInputFs.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Fornendo l'input richiesto in una forma archiviata (il pacchetto `pgfplots`)

Ora, supponiamo di avere il seguente file Latex denominato `richiesto Input-Zip.tex`, che è anche un semplice file dalla nostra soluzione di esempio:


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

Sulla terza riga, si può osservare che il file richiede il pacchetto "pgfplots", che non è "nativo" supportato. Ancora una volta, supponendo che possediamo i file di origine per il pacchetto `pgfplots`, questi file sono piuttosto numerosi e si trovano in due diverse directory all'interno della directory di installazione di qualsiasi applicazione di composizione in LaTeX. La cartella `pgfplots` può essere trovata nelle directory`\tex\generic` e `\tex\latex`. Affinché la libreria Aspose.TeX funzioni correttamente, è necessario fornire il contenuto di entrambe queste cartelle come input. Per raggiungere questo obiettivo, desideriamo impacchettare questi file di origine in un archivio con zip. Di seguito è riportato il layout desiderato dell'archivio:

![Layout dell'archivio](/tex/images/python-net/pgfplots-zip-layout.png)

Ed ecco il metodo con cui definiamo l'accessibilità a questi file di origine:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Dopo aver eseguito un lavoro Tex con questa opzione, otteniamo il documento di output:

![Documento di output](/tex/images/python-net/Conversion-RequiredInputZip.png)

Ecco il codice sorgente completo per l'esempio:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_NOTA:_** Il risultato è stato verificato utilizzando il pacchetto `pgfplots` versione 1.18.1. Mentre la versione del pacchetto `pfg` inclusa nella libreria **Aspose.TeX** è la 3.1.9a.

<!--
### Utilizzo di pacchetti di font esterni

In genere, le distribuzioni LaTeX includono un set predefinito di font che possono essere utilizzati per la composizione. Tuttavia, oltre a questi font predefiniti, **Aspose.TeX** include anche diversi pacchetti di font non standard come `amsfonts`, `eurosym` e `wasysym`. Come discusso in precedenza, Aspose.TeX supporta anche l'uso di pacchetti esterni, sebbene la maggior parte delle nostre discussioni precedenti si sia concentrata su pacchetti che non includono font.

L'estensione del motore *Object TeX* di **Aspose.TeX** richiede mappe di font, ovvero file di testo in un formato specifico con estensione `.map`, per determinare i font fisici corrispondenti a ciascun nome di font interno di TeX. Queste mappe di font devono essere caricate nella memoria di TeX durante la fase di inizializzazione e devono essere incluse nel pacchetto che si sta utilizzando. Poiché il motore non conosce i nomi di tutte le mappe di font, cerca i file con estensione `.map`. Pertanto, quando si specifica un valore per l'opzione [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/), l'implementazione dell'interfaccia [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) dovrebbe consentire l'accesso alle raccolte di nomi di file in base all'estensione. Inoltre, questa implementazione dovrebbe implementare anche l'interfaccia [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Le implementazioni standard, come [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), soddisfano già questi requisiti.

Di seguito è riportato un esempio di directory di input personalizzata che illustra come implementare l'interfaccia [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Questo esempio si concentra sulla raccolta dei nomi dei file per estensione e omette intenzionalmente i dettagli relativi all'archiviazione e al recupero dei file.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.py" >}}
-->

### Restrizioni

Se ti imbatti in un pacchetto che viene sviluppato sotto il kernel e il kernel*è richiesto dal tuo file LaTeX, è improbabile che funzioni con la libreria **aspy.tex**. Questo perché la biblioteca si basa sul kernel * latex2e *.

Inoltre, potrebbero esserci casi in cui un pacchetto richiesto dal file Latex utilizza direttamente comandi primitivi dipendenti dal dispositivo che non sono supportati dal motore **Object*della libreria*della libreria** **. In tali casi, il pacchetto non funzionerà con la biblioteca.