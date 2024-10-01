---
translation: true
template: /templates/_template-net.md
title: Що таке LaTeX? | Aspose.TeX .NET
linktitle: Що таке LaTeX?
weight: 16
url: /net/what-is-latex/
keywords: що таке латекс, латекс що це таке
description: Щоб відповісти на запитання "Що таке LaTeX?" Варто зазначити, що однією з найбільш вражаючих функцій є нова схема вибору шрифтів (NFSS).
lastmod: 2024-09-20
---

{{<section overview>}}

Отже, що таке LaTeX?

Коротше кажучи, LaTeX — це формат [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/).

LaTeX (*LAH-tekh або LAY-tekh*, часто стилізований як LATEX) — це програмна система для підготовки документів, яка була спочатку написана на початку 1980-х років <a href="https://en.wikipedia.org/wiki/ Leslie_Lamport" target=_blank rel="nofollow">Леслі Лемпорт</a> у <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a>. Ось що розповідає <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Вікіпедія</a>.

Відповідаючи на запитання "Що таке LaTeX?" ми хотіли б згадати деякі його особливості.

Однією з найбільш вражаючих особливостей LaTeX є нова схема вибору шрифтів (NFSS). Це підсистема макросів, яка дозволяє вам змінювати окремі властивості поточного шрифту, а не визначати новий шрифт у цілому, як це працювало в оригінальному TeX (Plain TeX також не пропонував багато для цього). Наприклад, у вас є поточний шрифт Computer Modern Roman italic, і ви хочете переключитися на жирний шрифт того самого типу, який фізично розташований в іншому файлі шрифту. В оригінальному TeX вам потрібно керувати послідовністю, яка відображається в іменах файлів шрифтів, тому, щоб переключитися, вам просто потрібно викликати іншу команду. Але ціна занадто багато контрольних послідовностей. У LaTeX вам потрібно просто попросити механізм змінити шрифт. Він вибере для вас відповідний поточний шрифт.

Іншою особливістю є ряд так званих класів документів. Це допоміжні вхідні файли, які містять значення внутрішніх параметрів TeX, що відповідають певному типу документа, наприклад книзі, статті, листу чи будь-чому іншому.

LaTeX також включає підтримку різних функцій, які можуть бути зручними для автора документа. Ці функції зазвичай збираються у допоміжних вхідних файлах, які називаються пакетами. У пакетах ви можете знайти розширені інструменти для математичного набору, малювання графіки, підтримки шрифтів, які не є частиною дистрибутива LaTeX, тощо. Навіть для малювання двовимірних хімічних формул.

Ось відносно невеликий приклад:


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

А ось дві сторінки результату:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Приклад сторінки 1">![Приклад сторінки 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Приклад сторінки 2">![Приклад сторінки 2](/tex/images/net/tutorial/example-page-2.png)</a>


Природно, ми не претендуємо на повну відповідь на питання «Що таке LaTeX?», оскільки це досить великий обсяг інформації. Оскільки написання файлу LaTeX все ще є програмуванням, вам доведеться витратити деякий час, якщо ви хочете краще з ним ознайомитися. Хочеш чи ні.

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/conversion/latex/), створену на основі [Aspose.TeX для .NET API](https://products.aspose.com/tex/net/).**