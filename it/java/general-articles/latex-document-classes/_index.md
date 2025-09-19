---
translation: true
template: /templates/_template-java.md
linktitle: Classi di documenti in LaTeX
title: Classi di documenti in LaTeX 
weight: 20
url: /java/latex-document-classes/
keywords: Classe di articoli in LaTeX, Classe di documenti in LaTeX, modello di documento in LaTeX, articolo in LaTeX, libro in LaTeX, diapositive in LaTeX, report Latex, lettera Latex, Document Class in Latex
description: Questo articolo è un digest conciso delle classi di documenti in LaTeX e delle loro opzioni. Fornisce anche alcuni esempi.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Cos'è una classe di documenti in LaTeX?

Il LaTeX definisce alcune regole che ogni autore del documento deve seguire. Definisce anche la struttura del file di origine, che è essenzialmente un programma di composizione. Secondo questa struttura, il codice sorgente del documento deve contenere una parte responsabile del contenuto stesso del documento - *body* - che è racchiuso in una coppia di comandi: `\begin{document}` e `\end{document}`. Il LaTeX ignora tutto ciò che segue la fine del corpo. La parte del codice sorgente prima di `\begin{document}` è chiamata *preamble*.

In genere, il primo comando nel preambolo deve essere `\documentclass`, che prende un singolo argomento richiesto che è il nome della **Classe di documenti**. La stessa classe di documenti è un insieme di parametri di formattazione, metriche di layout, macro, ecc. Che sono adatte e utili per sviluppare documenti di un determinato tipo e raccolti sotto il nome unico. In questo articolo, discuteremo delle classi di documenti predefinite **Latex** che sono incorporate in LaTeX e mostrerebbero i loro usi, differenze e somiglianze. Citeremo anche alcuni argomenti opzionali che il comando `\documentclass` può assumere e che personalizza l'aspetto del documento.

## Classi di documenti in LaTeX predefinito

Il LaTeX standard contiene le seguenti classi di documenti:

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | La classe LaTeX per articoli viene utilizzata per creare articoli per riviste scientifiche, brevi report, documentazione di programmi e, in generale, qualsiasi documento breve che non richieda una complessa suddivisione in capitoli e parti. |
| **report** | La classe LaTeX per report viene utilizzata per articoli lunghi che possono contenere diversi capitoli (ad esempio, piccoli libri e tesi). |
| **book** | Questa classe viene utilizzata per la composizione di libri veri e propri. Include tutti i tipi di standard tipografici adatti ai libri stampati: capitoli e parti, due tipi di pagine, frontespizio, retroscena, ecc.|
| **slides** | Può essere utilizzato per produrre slide, sebbene esista il pacchetto esterno [beamer](https://ctan.org/pkg/beamer) che è molto più potente per questo scopo. |
| **letter** | Questa classe di documento viene utilizzata per scrivere lettere. |

Le prime due classi di documenti sono di base. Quindi, inizia con **articolo** ogni volta che non sei sicuro di quale classe hai bisogno.

La classe **rapporto** è molto simile. La differenza principale dall'articolo **** è che è possibile inserire capitoli con il comando `\capitolo`, mentre l'articolo ** la classe di documenti non definisce tale unità di sezionamento.

## La classe del libro **del LaTeX**

I libri, negli standard tipografici, hanno la materia anteriore e la materia posteriore, che sono la differenza principale tra libri e, diciamo, rapporti o articoli. La questione anteriore di un libro di solito è costituita da una pagina di mezzo titolo, una pagina principale, una pagina del copyright, una prefazione o una prefazione e un contenuto di una tabella. Le parti meno obbligatorie sono riconoscimenti, una dedizione, un elenco di cifre, un elenco di tabelle, un elenco di altri libri della stessa serie e altri contenuti editoriali e promozionali. La materia posteriore in genere include un indice e può contenere una postfazione, nonché riconoscimenti, una bibliografia, un colophone, ecc.

La classe di documenti del libro offre comandi per produrre le suddette strutture logiche, mentre altre classi di documenti non possono fornirti tali strumenti. Tuttavia, diversi editori di solito hanno i propri pacchetti con ulteriori comandi per esprimere strutture in base al proprio stile.

## I comandi anteriori, materia principale e materia posteriore

La questione principale è ciò che include il corpo del libro, che inizia con il primo capitolo o parte e termina con le appendici. Le questioni anteriori, principali e posteriori iniziano con i comandi `\Frontmatter`,`\mainmatter` e `\backmatter`, rispettivamente.

> Nella classe di libri standard, le pagine del frontespizio sono numerate con numeri romani, mentre le pagine del frontespizio e del retro sono numerate con numeri arabi.

> Il comando `\chapter` non genera un numero di capitolo nel frontespizio e nel retro, sebbene crei una voce nell'indice. Questo comando viene in genere utilizzato per creare una sezione di prefazione o di ringraziamenti. All'interno di tali capitoli, si dovrebbero utilizzare solo le versioni con asterisco degli altri comandi di suddivisione in sezioni (come `\section*` e `\subsection`).

## Un esempio di utilizzo della classe del libro in LaTeX

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

Di seguito è riportata la struttura dei documenti generata da questo codice Latex:

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Esempio di output](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

Ed ecco il tavolo dei contenuti in dettaglio:

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Sommario](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **dispari** e **anche** pagine nei libri

Nei libri, **dispari** e **anche** le pagine non sembrano uguali. I margini, e di solito intestazioni e piè di pagina, differiscono per rendere il libro più leggibile quando è legato. La classe di documenti in LaTeX gestisce questo e potresti scoprire che:
- **Le pagine a sinistra (pari)** hanno un margine sinistro più grande, il numero di pagina è in alto a destra della pagina e il titolo del capitolo corrente è sulla destra;
- **Le pagine a destra (dispari)** hanno un margine destro più grande e solo il numero di pagina in alto a destra della pagina.

Si noti che i nuovi capitoli iniziano sempre sulla pagina giusta, in cui la testa della pagina è vuota, lasciando solo il numero di pagina al centro del piede.

## **La sezione astratta** manca

Gli articoli accademici, come articoli o report, di solito includono una sezione introduttiva chiamata **"Abstract"**. Il suo scopo è quello di fornire una rapida panoramica dell'argomento trattato nel documento. Potresti trovarlo stampato subito dopo il titolo e prima del contenuto, con l'intestazione "Abstract" impostata in grassetto. Nel LaTeX, una tale struttura è implementata come l'ambiente `Abstract`.

L'ambiente **Abstract** non è fornito dalla classe del documento del libro, e questa è un'altra differenza rispetto all'articolo e alle lezioni di report.

## Classe di lettere **Latex**

Al momento, la classe di documenti di lettere sembra essere in qualche modo vecchio stile (così è la classe di documenti di diapositiva, in realtà). Se hai bisogno di creare lettere tradizionali, per metterle in buste e inviarle per posta, questa classe di documenti sarà probabilmente utile. Sebbene questo sia una specie di modo obsoleto di comunicazione, ci sono ancora casi in cui potresti dover preparare un documento simile a una lettera. Ad esempio, una lettera di raccomandazione o una lettera di presentazione.

Quindi, ecco la breve panoramica della classe.

È possibile generare un numero qualsiasi di lettere con un singolo file di input. Il tuo nome e indirizzo, che in genere sono gli stessi per tutte le lettere, sono generalmente specificati nel preambolo del documento. L'indirizzo di ritorno è dichiarato da un comando `\indirizzo`, che accetta più righe separate da` \\ `(il comando di interruzione della riga LaTeX) come argomento. Allo stesso modo, il comando `\Signature` accetta più righe tra cui nome, titolo, ecc. Tuttavia, è possibile modificare l'indirizzo di ritorno e la firma in qualsiasi momento.

Ogni lettera è generata da un ambiente `lettera` separato che richiede il nome e l'indirizzo del destinatario come argomento. La lettera inizia con un comando `\apertura`, producendo il saluto e termina con un comando `\chiusura`, producendo la frase di chiusura e la firma. Il corpo della lettera è normale input in LaTeX.

Tutti questi comandi sono facili da usare e molto potenti poiché LaTex si occupa automaticamente della formattazione delle lettere. Quindi non lasciare che il numero di comandi ti spaventino o ti confondhi.

L'esempio seguente dimostra come funziona tutto.

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![Un esempio di classe di documenti di lettera](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

Si noti che anche la data corrente viene prodotta automaticamente. Tuttavia, puoi ridefinire il comando `\oggi 'per modificare la data nelle tue lettere. Ecco come lo fai:

```tex
\renewcommand{\today}{01th of March of 2492}
```

Se si inserisce questa dichiarazione in un determinato ambiente `lettera`, cambierà la data solo per quella lettera. Altrimenti, se lo si inserisce nel preambolo, sarà in vigore per tutte le lettere generate dal file di input (a meno che non sia inserito in un determinato ambiente `lettera").

## Opzioni di classe dei documenti in LaTeX

Diamo ora un'occhiata alle opzioni di comando `\Documentclass" menzionate all'inizio dell'articolo.

### Dimensione del carattere

La dimensione del carattere è controllata da tre opzioni: 10pt, 11pt, 12pt. Per impostazione predefinita, 10pt è in vigore. Queste opzioni determinano la dimensione del carattere di base utilizzata in tutto il documento a meno che non sia stata modificata ad un certo punto. Colpiscono anche i fattori di scala per alcune dimensioni di formattazione.

```tex
\documentclass[12pt]{article}
```

> These options are not recognizable by the `slides` class.

### Dimensione della carta
La "dimensione della carta" qui si riferisce alle dimensioni del foglio di carta su cui si sta **Pianificazione** per stampare il documento. Non influisce sulle dimensioni della rappresentazione della pagina nell'output di sistemi di composizione come **PDF Tex**. È controllato da 6 opzioni: `LetterPaper` (8.5in x 11in),` LegalPaper` (8.5in x 14in), `Executive Paper` (7.25in x 10.5in),` A4Paper` (210mm x 297mm), `A5paper` (148mm x 210mm) e` b5paper` (176mm xm). L'impostazione predefinita è `letterpaper '.

```tex
\documentclass[a4paper]{article}
```

### Orientamento della pagina

L'opzione `paesaggio` rende l'uscita formattata per la stampa del paesaggio sulla dimensione della carta selezionata. In effetti, rende lo scambio di LaTeX la dimensione della larghezza e dell'altezza ovunque vengano utilizzate lungo il processo di composizione. L'opzione `Ritratto 'non ha un tale effetto e viene utilizzata per impostazione predefinita.

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### Modalità di bozza

Ogni volta che Tex non può fare una rottura abbastanza buona (ha un algoritmo di stima della "bontà") lungo il processo di costruzione del paragrafo, produce una linea che si diffonde sul bordo destro dell'area di testo. Riferisce inoltre tali incidenti nel file di trascrizione (e nel terminale) con avvisi di "scatole eccessive". L'opzione `Draft` fa in modo che il LaTeX contrassegna tali linee con scatole nere nell'output. L'opzione `Final` non produce Black Box e viene utilizzata per impostazione predefinita.

### Due stampa laterali

L'opzione `OpenAny` consente ai capitoli di iniziare su qualsiasi pagina, mentre l'opzione` OpenRight` fa iniziare tutti i capitoli su una pagina di destra. L'impostazione predefinita è `OpenNany` nella classe` report` e `OpenRight` nella classe` Book`. Entrambe le opzioni non sono riconosciute in altre classi di documenti.

### Pagina per il titolo

Con l'opzione `titlepage`, LaTex crea una pagina separata per il titolo prodotto dal comando `\maketitle`. Fa anche avviare l'ambiente `Abstract` avviare l'abstract su una nuova pagina e fare una pausa di pagina dopo di essa. L'impostazione predefinita è `titlepage` per tutte le classi tranne` articolo`, per il quale è `Notitlepage`. 

> Queste opzioni non sono riconosciute dalla classe `letter`.

### Formule visualizzate numerate

L'opzione `Leqno` rende i numeri o tag Equazione (Formula matematica visualizzati), o tag, sul lato sinistro, anziché sul lato destro, che è il comportamento predefinito.

### Allineamento delle formule visualizzate

L'opzione `Fleqn` allinea le formule visualizzate a sinistra. Altrimenti, sono centrati per impostazione predefinita.
