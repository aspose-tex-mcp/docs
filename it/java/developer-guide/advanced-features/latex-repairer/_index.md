---
translation: true
template: /templates/_template-java.md
title: Riparazione del file in LaTeX | Aspose.TeX per java
linktitle: Riparazione dei file in LaTeX
weight: 30
url: /java/latex-repair/
description: La funzione di riparatore di file latex all'interno di API ASPUS.TEX per Java è descritta in questo articolo. Impara gli esempi di codice su come utilizzare la funzionalità.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Come controllare e riparare un file in LaTeX

Se non sei sicuro che un file di testo sia un file in LaTeX e desideri che sia composto, è possibile utilizzare la funzione di controllo e riparazione del LaTeX offerto dall'API Aspose.TeX per Java. Nell'esempio seguente, controlleremo e riparare un file di esempio, `Invalid-latex.tex`, da Aspose.TeX per il progetto di esempio Java.

Per cominciare, è importante notare che il file di esempio sembra impiegare la sintassi di Tex ma manca della struttura richiesta dal LaTeX. Come forse saprai, un file in LaTeX deve includere un preambolo che inizia con il comando \documentclass, nonché un corpo racchiuso nell'ambiente del documento, in particolare tra \begin{document} e \end{document}.

Diamo ora un'occhiata al campione del codice Java.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Simile a un normale lavoro Tex, iniziamo creando un oggetto che contiene le opzioni per il processo che stiamo per eseguire. La maggior parte di queste opzioni sono le stesse di quelle per un normale lavoro Tex. In effetti, chiamando il metodo [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), specifichiamo lo spazio da cui dovrebbero essere letti i file di input. Tuttavia, in questo esempio, non lo utilizziamo qui perché forniamo il percorso completo al file di input principale nel file system e nessun file personalizzato deve essere incluso nel file di input principale. Successivamente, chiamiamo il metodo [SetOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) per specificare lo spazio in cui i file di output devono essere scritti. Se chiamato, il metodo [setreQueratoInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) fa indicare le opzioni allo spazio in cui è possibile archiviare pacchetti in LaTeX che non sono incorporati nella libreria Aspose.TeX. Infine, il metodo [setGessPackAgeCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) sarà discusso in seguito.

Una volta assegnate le opzioni, possiamo procedere con l'esecuzione del processo.

Allora, com'è il processo di controllo e riparazione? Inizia con l'API alla ricerca di un evento `\documentclass` nel file di input. Se non viene trovato, l'API presuppone che `\documentclass{article}` debba essere inserito all'inizio del file. Queste informazioni sono registrate nel file del rapporto di riparazione (.log).

Successivamente, il processo inizia a scansionare il file di input regolato dall'inizio. Il motore Tex dotato del formato in LaTeX può, ad un certo punto, lanciare un errore indicando che `\begin{document}` non è stato ancora trovato quando avrebbe già dovuto. In questo modo, la posizione in cui `\begin{document}` deve essere inserita viene definita e riflessa nel rapporto.

Durante la scansione ulteriormente il file, il motore può presentarsi in comandi o ambienti indefiniti. In tali casi, l'API può fare ipotesi su [pacchetti richiesti incorporati](/tex/{{lang.url-fragment}}net/embedded-packages/) (quelli che definiscono i comandi e gli ambienti che non sono definiti fino a quando questi pacchetti non sono inclusi) per alcuni dei comandi e ambienti più comuni. Tuttavia, è possibile fare tali ipotesi esternamente da una classe che implementa l'interfaccia [IGUesspackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). Una volta sviluppata una tale classe, un'istanza di essa dovrebbe essere passata al processo chiamando il metodo `setGessPackAgeCallback().

Ecco un esempio di base che mappa semplicemente il comando `\head` al pacchetto `fancyhdr`:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

Per quanto riguarda il file di esempio, il motore incontra innanzitutto il comando `\chapter`, che non è definito nella classe documento `article`, ma è definito nella classe documento `book`. L'API modifica la classe documento in modo che la versione finale del file riparato inizi con `\documentclass{book}`. Quindi, il motore trova il comando `\lhead` sopra menzionato e determina che `\usepackage{fancyhdr}` deve essere inserito nel preambolo. I comandi `\href` e `\includegraphics` presenti più avanti nel file fanno sì che il Repairer inserisca rispettivamente `\usepackage{hyperref}` e `\usepackage{graphics}` nel preambolo. Queste decisioni vengono prese in base alle mappature interne dell'API. Come in precedenza, tutte queste riparazioni vengono registrate nel file di report.

Infine, il motore termina in modo anomalo perché manca la corretta conclusione di un documento in LaTeX. Di conseguenza, il riparatore aggiunge `\end{document}` alla fine del file e include queste informazioni nel rapporto.

Dopo aver creato la versione fissa del file originale, il riparatore esegue un lavoro Tex per la verifica finale. Nel nostro esempio, questa corsa non rileva alcun errore critico, quindi la versione fissa può essere più o meno come previsto.

Ecco il rapporto completo:

```
Tentativo di riparazione del file originale...
--------------------------------------------------------------------------------
\documentclass manca nel file originale. Inserito all'inizio.
\begin{document} manca nel file originale. Inserito alla riga 3, posizione 0.
Il comando \chapter alla riga 3, posizione 0, non è definito. Si consiglia di utilizzare \usepackage{package_name} nel preambolo,
dove 'package_name' è il nome del pacchetto che definisce questo comando.
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