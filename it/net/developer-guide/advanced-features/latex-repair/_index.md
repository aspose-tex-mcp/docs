---
translation: true
template: /templates/_template-net.md
title: Riparazione del file in LaTeX | .NET
linktitle: Riparazione dei file in LaTeX
weight: 30
url: /net/latex-repair/
description: ASPIPE.Tex Soluzione API per la riparazione del LaTeX .NET è descritta in questo articolo. Impara gli esempi di codice su come utilizzare la funzionalità.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Come controllare e riparare un file in LaTeX

Se hai un file di testo che ritieni sia un file LaTeX e vuoi che sia composto, ma non sei sicuro che sia davvero un file in LaTeX (forse sei nuovo nel mondo in LaTeX), puoi provare a utilizzare la funzione di controllo e riparazione del LaTeX fornita dall'API Aspose.TeX per .NET. Nell'esempio seguente, controlleremo e riparare un file di esempio, `Invalid-latex.tex`, da Aspose.TeX per il progetto di esempio .NET.

Prima di tutto, vale la pena ricordare che sebbene il file di esempio sembri utilizzare la sintassi di Tex, non ha la struttura richiesta dal LaTeX. Come forse saprai, un file Latex deve avere un preambolo che inizia con il comando `\documentclass` e un corpo all'interno dell'ambiente` Document`, ovvero tra `\inizio {Document}` e `\end {Document}`.

Diamo ora un'occhiata al campione del codice C#.

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-LaTeXRepairer.cs" >}}

Come con un normale lavoro Tex, creiamo prima un oggetto che contiene le opzioni del processo che stiamo per eseguire. La maggior parte di loro è uguale alle opzioni di un normale lavoro Tex. In effetti, [inputworkingdirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) è lo spazio da cui dovrebbero essere letti i file di input. Non lo utilizziamo qui perché forniamo il percorso completo al file di input principale nel file system e non si suppone che non siano inclusi file personalizzati nel file di input principale. Quindi, [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) è lo spazio in cui i file di output dovrebbero essere scritti. [RecomeNinputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), se assegnato, punta allo spazio in cui è possibile archiviare pacchetti in LaTeX che non sono incorporati nella libreria ASPIPE.Tex. La proprietà [Ipotesi di Ipotesi](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) sarà discussa più avanti.

Dopo aver assegnato le opzioni, eseguiamo semplicemente il processo!

Allora, com'è il processo di controllo e riparazione? In primo luogo, l'API cerca il file di input per un occorrenza `\documentclass`. Se fallisce, presuppone che `\documentclass{article}` debba essere inserito all'inizio del file. Questo fatto si riflette nel file del rapporto di riparazione (`.log`).

Quindi, inizia a scansionare il file di input regolato dall'inizio. Il motore TEX accusato del formato in LaTeX può lanciare un errore ad un certo punto, segnalando che finora non è stato trovato alcun `\begin{document}`, sebbene avrebbe già dovuto verificarsi. Pertanto, la posizione in cui `\inizio {documento} deve essere inserita viene definita e riflessa nel rapporto.

Man mano che il motore scruta ulteriormente il file, potrebbe trovare comandi o ambienti indefiniti. L'API può fare ipotesi su [pacchetti richiesti incorporati](/tex/{{lang.url-fragment}}net/embedded-packages/) (quelli che definiscono i comandi e gli ambienti che non sono definiti fino a quando questi pacchetti non sono inclusi) per alcuni dei comandi e ambienti più comuni. Tuttavia, esiste un modo per fare tali ipotesi esternamente implementando l'interfaccia [IGUessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/). Un'istanza di tale classe dovrebbe essere assegnata all'opzione `Indovine.

Ecco un esempio molto semplice che mappa il comando `\head` al pacchetto `fancyhdr`:

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.cs" >}}

Per quanto riguarda il file di esempio, il motore incontra per la prima volta il comando `\capitolo`, che non è definito nella classe di documenti` Articolo` ma è definito nella classe di documenti `Book`. L'API regola la classe di documenti in modo che la versione finale del file fisso inizi con `\DocumentClass {Book}`. Quindi, il motore trova il suddetto comando `\lhead` e decide che`\usapackage {FancyHDr} `deve essere inserito nel preambolo. I comandi `\href` e `\includegraphics` che si verificano in seguito a rendere il riparatore insert `\usepackage {hyperref}` e `\usepackage {graphics}` nel preambolo, rispettivamente. Queste decisioni si basano sulle mappature interne dell'API. Ancora una volta, tutte queste correzioni sono registrate nel file di report.

Infine, il motore termina in modo anomalo dalla fine normale di un documento in LaTeX. Ciò rende il riparatore append `\end{document}` alla fine del file e riflette questo fatto nel rapporto.

Una volta creata la versione fissa del file originale, il riparatore esegue il lavoro Tex per il controllo finale. Nel nostro esempio, questa corsa non trova errori critici, quindi la versione fissa potrebbe essere più o meno come previsto.

Ecco il rapporto completo:


```
Tentativo di riparazione del file originale...
--------------------------------------------------------------------------------
\documentclass mancante nel file originale. Inserito all'inizio.
\begin{document} mancante nel file originale. Inserito alla riga 3, posizione 0.
Il comando \chapter alla riga 3, posizione 0, non è definito. Si consiglia di utilizzare \usepackage{nome_pacchetto} nel preambolo,
dove 'nome_pacchetto' è il nome del pacchetto che definisce questo comando.
Il comando \lhead alla riga 5, posizione 0, non è definito. \usepackage{fancyhdr} è inserito nel preambolo
poiché il pacchetto 'fancyhdr' presumibilmente definisce il comando.
Il comando \href alla riga 8, posizione 0, non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando. Il comando \href alla riga 17, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 20, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 27, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 32, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \includegraphics alla riga 54, pos. 2 non è definito. \usepackage{graphicx} è inserito nel preambolo
poiché il pacchetto 'graphicx' presumibilmente definisce il comando.
Il comando \href alla riga 67, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 95, pos. 57 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 96, pos. 0 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
Il comando \href alla riga 98, pos. 100 non è definito. \usepackage{hyperref} è inserito nel preambolo
poiché il pacchetto 'hyperref' presumibilmente definisce il comando.
\end{document} manca nel file originale. Inserito alla fine.

Controllo del file riparato...
--------------------------------------------------------------------------------
Non ci sono errori critici nel file riparato.
```

**Puoi anche verificare la nostra app Web gratuita [** AI Latex Repair **](https://products.aspose.ai/tex/latex-repairer), che è costruita in base alla funzionalità implementata nell'interfaccia [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/) e comporta un'implementazione più avanzata dell'interfaccia `IguesspackageCallback`.**