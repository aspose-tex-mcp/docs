---
translation: true
template: /templates/_template-net.md
title: Was ist LaTeX?
linktitle: Was ist LaTeX?
weight: 16
url: /net/what-is-latex/
keywords: Was ist Latex, Latex was ist das?
description: Zur Beantwortung der Frage „Was ist LaTeX?“ Es ist erwähnenswert, dass eines der beeindruckendsten Features das New Font Selection Scheme (NFSS) ist.
lastmod: "2024-09-26"
---

{{<section overview>}}

Was ist LaTeX?

Kurz gesagt ist LaTeX das [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/)-Format.

LaTeX (*LAH-tekh oder LAY-tekh*, oft stilisiert als LATEX) ist ein Softwaresystem zur Dokumentenvorbereitung, das ursprünglich in den frühen 1980er Jahren von <a href="https://en.wikipedia.org/wiki/ geschrieben wurde. Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> bei <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a>. Das sagt <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a>.

Beantwortung der Frage „Was ist LaTeX?“ Wir möchten einige seiner Funktionen erwähnen.

Eines der beeindruckendsten Features von LaTeX ist das New Font Selection Scheme (NFSS). Es ist das Makro-Subsystem, mit dem Sie einzelne Eigenschaften der aktuellen Schriftart ändern können, anstatt eine neue Schriftart als Ganzes zu definieren, wie es im ursprünglichen TeX funktionierte (Plain TeX bot hierfür auch nicht viel). Beispielsweise haben Sie die aktuelle Schriftart „Computer Modern Roman Italic“ und möchten zu einer Fettschrift desselben Typs wechseln, die sich physisch in einer anderen Schriftartendatei befindet. Im Original-TeX müssen Sie Sequenzen steuern, die Schriftartdateinamen zugeordnet sind. Um zu wechseln, müssen Sie also nur einen anderen Befehl aufrufen. Aber der Preis sind zu viele Steuersequenzen. In LaTeX müssen Sie lediglich die Engine auffordern, die Schriftart zu ändern. Es wird die passende aktuelle Schriftart für Sie ausgewählt.

Ein weiteres Feature sind eine Reihe sogenannter Dokumentenklassen. Hierbei handelt es sich um Hilfseingabedateien, die die Werte der internen Parameter von TeX enthalten, die einem bestimmten Dokumenttyp entsprechen, beispielsweise einem Buch, einem Artikel, einem Brief oder etwas anderem.

LaTeX bietet außerdem Unterstützung für verschiedene Funktionen, die für den Autor eines Dokuments nützlich sein können. Diese Funktionen werden normalerweise in Hilfseingabedateien, sogenannten Paketen, gesammelt. In den Paketen finden Sie erweiterte Werkzeuge für den mathematischen Schriftsatz, das Zeichnen von Grafiken, Unterstützung für Schriftarten, die nicht Teil der LaTeX-Distribution sind usw. Auch zum Zeichnen chemischer 2D-Formeln.

Hier ist ein relativ kleines Beispiel:


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
This document represents the output from the file ``sample.tex" once compiled using your favorite \LaTeX compiler.  This file should serve as a good example of the basic structure of a ``.tex" file as well as many of the most basic commands needed for typesetting documents involving mathematical symbols and expressions.  For more of a description on how each command works, please consult the links found on our course webpage.
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

Und hier sind zwei Ausgabeseiten:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Beispielseite 1">![Beispielseite 1](/tex/images/net/tutorial/example-page-1.png)</a>

<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Beispielseite 2">![Beispielseite 2](/tex/images/net/tutorial/example-page-2.png)</a>


Natürlich erheben wir keinen Anspruch darauf, eine vollständige Antwort auf die Frage „Was ist LaTeX?“ zu haben, da es sich hierbei um eine recht große Menge an Informationen handelt. Da das Schreiben einer LaTeX-Datei immer noch Programmierarbeit ist, müssen Sie einige Zeit aufwenden, wenn Sie sich besser damit vertraut machen möchten. Willst du es oder nicht?

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/conversion/latex/) ansehen, die auf der Grundlage von [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) erstellt wurde.**