---
translation: true
template: /templates/_template-net.md
title: O que é LaTeX? 
linktitle: O que é LaTeX?
weight: 16
url: /net/what-is-latex/
keywords: o que é LaTeX, LaTeX o que é
description: Para responder à pergunta "O que é LaTeX?" Vale ressaltar que um de seus recursos mais impressionantes é o novo esquema de seleção de fontes (NFSS).
lastmod: "2025-06-16"
---

{{<section overview>}}

Então, o que é LaTeX?

O LATEX é o formato [Tex](/tex/{{lang.url-fragment}}net/what-is-tex/), em resumo.

O LATEX (*lah-tekh ou ley-tekh*, geralmente estilizado como LaTeX) é um sistema de software para a preparação de documentos que foi originalmente escrito no início dos anos 80 por <a href = "https://en.wikipedia.org/wiki/leslie_lamport" alvo = _blank Rel = "NOFLIGHT"> href = "https://en.wikipedia.org/wiki/sri_international" Target = _blank rel = "nofollow"> sri internacional </a>. É isso que <a href = "https://en.wikipedia.org/wiki/latex" Target = _blank rel = "Nofollow"> Wikipedia </a> Diz.

Respondendo à pergunta "O que é LaTeX?" Gostaríamos de mencionar alguns de seus recursos.

Um dos recursos mais impressionantes do LaTex é o novo esquema de seleção de fontes (NFSS). É o subsistema macro que permite alterar as propriedades individuais da fonte atual, em vez de definir uma nova fonte como um todo, pois funcionava no Tex original (Pleno Tex não ofereceu muito para isso). Por exemplo, você tem a fonte atual que é o Itálico Romano Moderno do computador e deseja mudar para uma fonte em negrito do mesmo tipo que está física localizada em um arquivo de fonte diferente. No Tex original, você precisa controlar as seqüências mapeadas para os nomes de arquivos da Fonte; portanto, para alternar, basta chamar outro comando. Mas o preço é muitas sequências de controle. No LATEX, você precisa apenas pedir ao motor para alterar o tipo de letra. Ele selecionará a fonte atual apropriada para você.

Outro recurso é várias classes de documentos. Estes são arquivos de entrada auxiliares que contêm os valores dos parâmetros internos da TEX correspondentes a um tipo de documento específico, como um livro, artigo, carta ou qualquer outra coisa.

O LATEX também inclui suporte para vários recursos que podem ser convenientes para um autor de documentos. Esses recursos geralmente são coletados em arquivos de entrada auxiliares chamados pacotes. Nos pacotes, você pode encontrar ferramentas avançadas para matemática, desenhar gráficos, suporte para fontes que não fazem parte da distribuição de LaTeX, etc. Mesmo para desenhar fórmulas químicas 2D.

Aqui está um exemplo relativamente pequeno:


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

E aqui estão duas páginas de saída:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Example Page 1">![Exemplo Página 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Example Page 2">![Exemplo Página 2](/tex/images/net/tutorial/example-page-2.png)</a>


Naturalmente, não pretendemos ter uma resposta completa para a pergunta "O que é LaTeX?", Como essa é uma quantidade bastante grande de informações. Como escrever um arquivo de LaTeX ainda está programando, você precisará gastar algum tempo se quiser se familiarizar com ele. Você quer ou não.

**Você também pode conferir o [aplicativo da web] gratuito (4) construído com base em [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**