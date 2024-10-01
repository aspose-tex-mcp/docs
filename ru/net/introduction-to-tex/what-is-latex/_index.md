---
translation: true
template: /templates/_template-net.md
title: Что такое латех? | Aspose.TeX .NET
linktitle: Что такое латех?
weight: 16
url: /net/what-is-latex/
keywords: что такое латех, латех, что это такое
description: Чтобы ответить на вопрос «Что такое LaTeX?» Стоит отметить, что одной из наиболее впечатляющих особенностей является новая схема выбора шрифта (NFSS).
lastmod: "2024-09-24"
---

{{<section overview>}}

Итак, что такое LaTeX?

Короче говоря, LaTeX — это формат [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/).

LaTeX (*LAH-tekh или LAY-tekh*, часто стилизованный под LATEX) — это программная система для подготовки документов, первоначально написанная в начале 1980-х годов <a href="https://en.wikipedia.org/wiki/ Leslie_Lamport" target=_blank rel="nofollow">Лесли Лэмпорт</a> в <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</ а>. Вот что рассказывает <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Википедия</a>.

Отвечая на вопрос «Что такое LaTeX?» хотелось бы отметить некоторые его особенности.

Одной из наиболее впечатляющих особенностей LaTeX является новая схема выбора шрифта (NFSS). Это подсистема макросов, которая позволяет вам изменять отдельные свойства текущего шрифта, а не определять новый шрифт в целом, как это работало в оригинальном TeX (Plain TeX тоже мало что предлагал для этого). Например, у вас есть текущий шрифт Computer Modern Roman, курсив, и вы хотите переключиться на полужирный шрифт того же типа, который физически находится в другом файле шрифта. В оригинальном TeX вам нужно управлять последовательностями, сопоставленными с именами файлов шрифтов, поэтому для переключения вам просто нужно вызвать другую команду. Но цена — слишком много последовательностей управления. В LaTeX вам нужно просто попросить движок изменить шрифт. Он выберет для вас подходящий текущий шрифт.

Еще одной особенностью является наличие ряда так называемых классов документов. Это вспомогательные входные файлы, содержащие значения внутренних параметров TeX, соответствующие определенному типу документа, например книге, статье, письму или чему-либо еще.

LaTeX также включает поддержку различных функций, которые могут быть удобны автору документа. Эти функции обычно собираются во вспомогательных входных файлах, называемых пакетами. В пакетах можно найти продвинутые инструменты для математической верстки, рисования графики, поддержки шрифтов, не входящих в дистрибутив LaTeX, и т. д. Даже для рисования 2D химических формул.

Вот относительно небольшой пример:


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

И вот две страницы вывода:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Пример страницы 1">![Пример страницы 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Пример страницы 2">![Пример страницы 2](/tex/images/net/tutorial/example-page-2.png)</a>


Естественно, мы не претендуем на какой-то полный ответ на вопрос «Что такое LaTeX?», поскольку это достаточно большой объем информации. Поскольку написание файла LaTeX по-прежнему является программированием, вам придется потратить некоторое время, если вы хотите с ним поближе познакомиться. Хочешь ты этого или нет.

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex/), созданным на основе [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/).**