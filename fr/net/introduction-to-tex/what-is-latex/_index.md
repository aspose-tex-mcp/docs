---
translation: true
template: /templates/_template-net.md
title: Qu’est-ce que LaTeX ? | Aspose.TeX .NET
linktitle: Qu’est-ce que LaTeX ?
weight: 16
url: /net/what-is-latex/
keywords: qu'est-ce que le latex, qu'est-ce que le latex
description: Pour répondre à la question « Qu'est-ce que LaTeX ? », découvrez sa fonctionnalité la plus impressionnante - le nouveau système de sélection de polices.
lastmod: "2024-09-27"
---

{{<section overview>}}

Alors, qu’est-ce que LaTeX ?

LaTeX est le format [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/), en bref.

LaTeX (*LAH-tekh ou LAY-tekh*, souvent stylisé comme LATEX) est un système logiciel de préparation de documents initialement écrit au début des années 1980 par <a href="https://en.wikipedia.org/wiki/ Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> sur <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</ une>. C'est ce que dit <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a>.

Répondre à la question « Qu'est-ce que LaTeX ? » nous aimerions mentionner certaines de ses caractéristiques.

L'une des fonctionnalités les plus impressionnantes de LaTeX est le nouveau système de sélection de polices (NFSS). C'est le sous-système de macro qui vous permet de modifier les propriétés individuelles de la police actuelle, plutôt que de définir une nouvelle police dans son ensemble, comme cela fonctionnait dans le TeX d'origine (Plain TeX n'offrait pas grand-chose non plus pour cela). Par exemple, votre police actuelle est Computer Modern Roman italique et vous souhaitez passer à une police grasse du même type qui se trouve physiquement dans un fichier de police différent. Dans TeX original, vous devez contrôler les séquences mappées sur les noms de fichiers de polices, donc pour changer, il vous suffit d'appeler une autre commande. Mais le prix est trop de séquences de contrôle. Dans LaTeX, il vous suffit de demander au moteur de changer la police. Il sélectionnera la police actuelle appropriée pour vous.

Une autre caractéristique réside dans un certain nombre de classes de documents. Ce sont des fichiers d'entrée auxiliaires qui contiennent les valeurs des paramètres internes de TeX correspondant à un type de document spécifique, comme un livre, un article, une lettre ou quoi que ce soit d'autre.

LaTeX inclut également la prise en charge de diverses fonctionnalités qui peuvent être pratiques pour un auteur de document. Ces fonctionnalités sont généralement collectées dans des fichiers d’entrée auxiliaires appelés packages. Dans les packages, vous pouvez trouver des outils avancés pour la composition mathématique, le dessin de graphiques, la prise en charge des polices qui ne font pas partie de la distribution LaTeX, etc. Même pour dessiner des formules chimiques 2D.

Voici un exemple relativement petit :

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

Et voici deux pages de sortie :

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Exemple de page 1">![Exemple de page 1](/tex/images/net/tutorial/example-page-1.png)</a>

<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Exemple de page 2">![Exemple de page 2](/tex/images/net/tutorial/example-page-2.png)</a>


Naturellement, nous ne prétendons pas avoir de réponse complète à la question « Qu'est-ce que LaTeX ? », car il s'agit d'une quantité d'informations assez importante. Étant donné que l'écriture d'un fichier LaTeX relève toujours de la programmation, vous devrez y consacrer du temps si vous souhaitez mieux le connaître. Tu le veux ou pas.

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/conversion/latex/) gratuite construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**