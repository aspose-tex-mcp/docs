---
translation: true
template: /templates/_template-net.md
title: Cos'è il LaTeX? 
linktitle: Cos'è il LaTeX?
weight: 16
url: /net/what-is-latex/
keywords: Cos'è il LaTeX, LaTeX che cos'è
description: Per rispondere alla domanda "Cos'è il LaTeX?" Vale la pena ricordare che una delle sue caratteristiche più impressionanti è il nuovo schema di selezione dei caratteri (NFSS).
lastmod: "2026-11-04"
---

{{<section overview>}}

Allora, cos'è il LaTeX?

Il LaTeX è il formato [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/), in breve.

LaTeX (*LAH-tekh or LAY-tekh*, spesso stilizzato come LaTeX) è un sistema software per la preparazione dei documenti che è stato originariamente scritto nei primi anni '80 da <a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> presso <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a>. Questo è ciò che <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a> dice.

Rispondere alla domanda "Che cos'è il LaTeX?" Vorremmo menzionare alcune delle sue caratteristiche.

Una delle caratteristiche più impressionanti del LaTeX è il nuovo schema di selezione dei caratteri (NFSS). È il sottosistema macro che consente di cambiare le singole proprietà dell'attuale carattere, piuttosto che definire un nuovo carattere nel suo insieme, poiché ha funzionato nel TeX originale (Plain TeX non ha offerto molto per questo). Ad esempio, hai l'attuale carattere che è un computer moderno di computer moderno e si desidera passare a un carattere audace lo stesso tipo che è fisico situato in un file di carattere diverso. In originale TeX è necessario controllare le sequenze mappate sui nomi dei file di carattere, per così dire, devi solo chiamare un altro comando. Ma il prezzo è troppe sequenze di controllo. In LaTeX è necessario chiedere al motore di cambiare il carattere tipografico. Selezionerà il carattere corrente appropriato per te.

Un'altra caratteristica è una serie di cosiddette classi di documenti. Questi sono file di input ausiliari che contengono i valori dei parametri interni di TeX corrispondenti a un tipo di documento specifico, come un libro, un articolo, una lettera o qualsiasi altra cosa.

Il LaTeX include anche il supporto per varie funzionalità che possono essere convenienti per un autore di documenti. Queste funzionalità sono generalmente raccolte in file di input ausiliari chiamati pacchetti. Nei pacchetti è possibile trovare strumenti avanzati per la composizione matematica, disegnare grafica, supporto per caratteri che non fanno parte della distribuzione del LaTeX, ecc. Anche per il disegno di formule chimiche 2D.

Ecco un esempio relativamente piccolo:


```tex
\documentclass[]{article}
%%%%%%%%%%%%%%%%%%%
% Packages/Macros %
%%%%%%%%%%%%%%%%%%%
\usepackage{amssymb,latexsym,amsmath}     % Standard packages
%%%%%%%%%%%
% Margins %
%%%%%%%%%%%
\addtolength{\textwidth}{1.0in}
\addtolength{\textheight}{1.00in}
\addtolength{\evensidemargin}{-0.75in}
\addtolength{\oddsidemargin}{-0.75in}
\addtolength{\topmargin}{-.50in}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Theorem/Proof Environments %
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newtheorem{theorem}{Theorem}
\newenvironment{proof}{\noindent{\bf Proof:}}{$\hfill \Box$ \vspace{10pt}}  
%%%%%%%%%%%%
% Document %
%%%%%%%%%%%%
\begin{document}
\makeatletter
\def\@date{May 17, 2021}
\makeatother

\title{Sample \LaTeX ~File}
\author{David P. Little}
\maketitle
\begin{abstract}

This document represents the output from the file `sample.tex` once compiled using your favorite \LaTeX compiler.  This file should serve as a good example of the basic structure of a `.tex` file as well as many of the most basic commands needed for typesetting documents involving mathematical symbols and expressions.  For more of a description on how each command works, please consult the links found on our course webpage.

\end{abstract}
\section{Lists}
%%%%%%%%%%%%%%%
\begin{enumerate}
\item {\bf First Point (Bold Face)}
\item {\em Second Point (Italic)}
\item {\Large Third Point (Large Font)}
    \begin{enumerate}
        \item {\small First Subpoint (Small Font)} 
        \item {\tiny Second Subpoint (Tiny Font)} 
        \item {\Huge Third Subpoint (Huge Font)} 
    \end{enumerate}
\item[$\bullet$] {\sf Bullet Point (Sans Serif)}
\item[$\circ$] {\sc Circle Point (Small Caps)} 
\end{enumerate}
\section{Equations}
%%%%%%%%%%%%%%%%%%%
\subsection{Binomial Theorem}
\begin{theorem}[Binomial Theorem]
For any nonnegative integer $n$, we have
$$(1+x)^n = \sum_{i=0}^n {n \choose i} x^i$$
\end{theorem}
\subsection{Taylor Series}
The Taylor series expansion for the function $e^x$ is given by
\begin{equation}
e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + \cdots = \sum_{n\geq 0} \frac{x^n}{n!}
\end{equation}
\subsection{Sets}
\begin{theorem}
For any sets $A$, $B$ and $C$, we have
$$ (A\cup B)-(C-A) = A \cup (B-C)$$
\end{theorem}
\begin{proof}
\begin{eqnarray*}
(A\cup B)-(C-A) &=& (A\cup B) \cap (C-A)^c\\
&=& (A\cup B) \cap (C \cap A^c)^c \\
&=& (A\cup B) \cap (C^c \cup A) \\
&=& A \cup (B\cap C^c) \\
&=& A \cup (B-C)
\end{eqnarray*}
\end{proof}
\section{Tables}
%%%%%%%%%%%%%%%%
\begin{center}
\begin{tabular}{l||c|r}
left justified & center & right justified \\ \hline
1 & 3.14159 & 5 \\
2.4678 & 3 &  1234 \\ \hline \hline
3.4678 & 6.14159 & 1239
\end{tabular}
\end{center}
\section{A Picture}
%%%%%%%%%%%%%%%%%%%
\begin{center}
\begin{picture}(100,100)(0,0)
\setlength{\unitlength}{1pt}
\put(20,70){\circle{30}}  \put(20,70){\circle*{10}}   % left eye
\put(80,70){\circle{30}}  \put(80,70){\circle*{10}}   % right eye
\put(40,40){\line(1,2){10}} \put(60,40){\line(-1,2){10}} \put(40,40){\line(1,0){20}} % nose
\put(50,20){\oval(80,10)[b]} % mouth
\multiput(0,90)(4,0){10}{\line(1,3){4}}  % left eyebrow
\multiput(100,90)(-4,0){10}{\line(-1,3){4}}  % right eyebrow
\end{picture}
\end{center}
\end{document}
```

E qui ci sono due pagine di output:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Example Page 1">![Esempio Pagina 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Example Page 2">![Esempio Pagina 2](/tex/images/net/tutorial/example-page-2.png)</a>


Naturalmente, non pretendiamo di avere alcuna risposta completa alla domanda "Che cos'è il LaTeX?", Dal momento che questa è una grande quantità di informazioni. Poiché scrivere un file in LaTeX è ancora programmazione, dovrai trascorrere un po 'di tempo se vuoi conoscerlo meglio. Lo vuoi o no.

**Puoi anche controllare la [app Web](https://products.aspose.app/tex/conversion/latex/) gratuita in base a [Aspose.TeX per .NET API](https://products.aspose.com/tex/net/).**

## Markup logico e formattazione diretta

A differenza dei tradizionali software di impaginazione desktop di tipo WYSIWYG ("ciò che vedi è ciò che ottieni") — in cui la creazione dei contenuti e la definizione dello stile visivo avvengono simultaneamente — LaTeX impone una netta separazione tra contenuto e presentazione.

Quando scrivono in LaTeX, gli autori utilizzano un markup semantico per definire la natura degli elementi (`\section{Introduction}`, `\begin{equation}`), senza doversi preoccupare del loro aspetto grafico. Il motore di composizione sottostante gestisce automaticamente regole di impaginazione complesse, spaziatura tra i caratteri (kerning), interruzioni di riga, numerazione delle pagine e allineamento di formule matematiche. Ciò garantisce una coerenza tipografica assoluta in documenti tecnici estesi e complessi o in articoli scientifici, liberando sviluppatori e ricercatori dal tedioso compito della formattazione manuale.

## Caratteristiche principali

Di seguito è riportata una tabella comparativa che illustra come le funzionalità standard di LaTeX vengano gestite a livello programmatico all'interno di Aspose.TeX:

| **Funzionalità/Sistema** | **Distribuzione TeX standard (CLI)** | **Motore Aspose.TeX per .NET** |
| :- | :- | :- |
| **Composizione matematica** | Gestita tramite `amsmath`/`amssymb` | Analizzata e renderizzata nativamente in formati vettoriali o raster |
| **Classi di documento** | Richiede file `.cls` presenti localmente sul disco | Caricate tramite `IInputWorkingDirectory` personalizzate o virtuali |
| **Riferimenti incrociati e indice (TOC)** | Richiede passaggi multipli da riga di comando | Un secondo passaggio viene attivato dall'opzione `TeXOptions.Repeat` |
| **Formati di output** | Genera DVI, PS o PDF tramite strumenti separati | Conversione diretta in un unico passaggio verso PDF, XPS, SVG, PNG, JPEG, BMP, TIFF |

**Per approfondire:**

- [Input/Output in TeX (tex-io)](/tex/{{lang.url-fragment}}net/tex-io/): scopri come `IInputWorkingDirectory` e `IOutputWorkingDirectory` gestiscono le risorse su disco e i flussi di dati (stream).
- [Grafica in LaTeX (latex-graphics)](/tex/{{lang.url-fragment}}net/latex-graphics/): inclusione di immagini esterne tramite `\includegraphics` utilizzando il pacchetto `graphicx`. - [Aspose.TeX e Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/): Comprendere il modello a oggetti gestito sottostante.