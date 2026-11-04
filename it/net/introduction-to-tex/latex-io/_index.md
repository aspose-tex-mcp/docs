---
translation: true
template: /templates/_template-net.md
title: Input/output in LaTeX
linktitle: LaTeX i/o 
weight: 17
url: /net/latex-io/
description: Questa pagina descrive brevemente le peculiarità del lavoro con il LaTeX come output o formato di input e il file *.aux* come parte obbligatoria del LaTeX.
keywords: LaTeX IO, LaTeX I, LaTeX O, file di input LaTeX, input in LaTeX
lastmod: "2026-04-22"
---

{{<section overview>}}

## File LaTeX {#latex-file}

Se abbiamo un [file tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) che ha la seguente struttura, chiameremo questo file un *file LaTeX *:


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

Dove `<una classe di documento>` è il nome di una [classe di documenti](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes) che è un file di input TeX che definisce la apparenza delle pagine del documento di output e delle macro che sono più adatte per un certo tipo di documento.

Ad essere onesti, è possibile inserire sequenze di controllo primitive prima di `\DocumentClass {}`, come `\non -stopmode`, ecc. Ma ogni macro LaTeX controlla se si trova in una parte corretta di un file.

Ci sono alcune cose che vale la pena notare su TeX [input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) e [output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) nel contesto di lavorare con i file in LaTeX.

## File di output in LaTeX {#latex-output-file}

Un tipico lavoro in LaTeX crea un file di output ausiliario con il [nome del lavoro](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) come nome ed estensione *.aux *. Questo file di solito contiene dati di riferimento che il motore raccoglie lungo il lavoro, se si dice, imposta etichette per le formule di matematica (equazioni) e quindi fai riferimento a loro da qualche parte nel testo. Nel caso in cui non usi nulla di questo tipo, questo file contiene solo la sequenza di controllo `\Relax` (che è una delle primitive TeX). Quindi non essere sorpreso.

Sebbene non siano vietati i primitivi `\Open`,`\write` e `\chiusure` non siano vietati, i pacchetti sono il luogo più adatto per loro. Pertanto dovresti meglio usarli nei tuoi pacchetti personalizzati se li stai sviluppando.

Altre parti dell'output sono arbitrarie, seguono anche il concetto generale [output tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e dipendono da cosa dovrebbe fare esattamente il tuo file (programma), quali pacchetti (vedi sotto) stai usando, ecc.

## File di input in LaTeX

Il file *.aux* sopra menzionato è una parte obbligatoria dell'input in LaTeX. Algoritmicamente, LaTeX non può eseguire queste attività relative ai riferimenti in una singola esecuzione, quindi lo stesso processo deve essere eseguito due volte: la prima per raccogliere i dati, la seconda per utilizzarli. Molti sistemi software basati su LaTeX eseguono automaticamente i processi LaTeX due volte. Spoiler: esiste un'opzione [option](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) nell'API di Aspose.TeX che ci permette di controllare questo comportamento.

Un'altra parte obbligatoria è una [classe di documenti](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Il file della classe di documenti, a sua volta, può implicitamente dipendere da altri file, che sono quindi inclusi anche nell'input di LaTeX.

Se si desidera utilizzare funzionalità oltre l'ambito del LaTeX di base e le sue classi di documenti ma supportate da una certa implementazione del motore TEX, in genere si utilizza un pacchetto, che è necessario avvisare il motore nel preambolo. Un pacchetto *LaTeX* è un file o un gruppo di file assemblati con un solo nome, che fornisce tali funzionalità. Per avvisare il motore, è necessario utilizzare il comando `\usapackage` con il nome del pacchetto e le opzioni omesse, se il pacchetto definisce uno.

Per esempio,


```tex
\usepackage[a6paper,landscape]{geometry}
```

Sebbene le primitive `\input`, `\openin`, `\read` e `\closein` non siano vietate, i pacchetti sono il luogo più adatto per utilizzarle. Pertanto, è consigliabile utilizzarle nei propri pacchetti personalizzati se si stanno sviluppando.

Altre parti dell'input sono arbitrarie, seguono anche il concetto generale [input tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) e dipendono da cosa dovrebbe fare esattamente il tuo file (programma), quali pacchetti stai usando, ecc.