---
translation: true
template: /templates/_template-net.md
title: 什么是乳胶？ | aspose.tex .net
linktitle: 什么是乳胶？
weight: 16
url: /net/what-is-latex/
keywords: 什么是乳胶，乳胶是什么
description: 要回答“什么是乳胶？”值得一提的是，其最令人印象深刻的功能之一是新的字体选择方案(NFSS)。
lastmod: "2025-06-10"
---

{{<section overview>}}

那么，什么是乳胶？

乳胶是[Tex](/tex/{{lang.url-fragment}}net/what-is-tex/)格式，简而言之。

LaTeX（*LAH-tekh 或 LAY-tekh*，通常缩写为 LATEX）是一款用于文档准备的软件系统，最初由 <a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> 在 <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a> 于 20 世纪 80 年代初开发。<a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">维基百科</a> 介绍了以下内容。

回答“什么是乳胶？”我们想提及它的一些功能。

乳胶最令人印象深刻的功能之一是新的字体选择方案(NFSS)。这是宏观子系统，您可以更改当前字体的各个属性，而不是将新字体定义为整体，因为它在原始的Tex中起作用(Pline Tex也不为此提供太多)。例如，您具有当前的字体，该字体是计算机现代罗马斜体，并且要切换到与位于其他字体文件中的物理状态相同类型的粗体字体。在原始TEX中，您需要控制映射到字体文件名的序列，因此要切换，您只需要调用另一个命令即可。但是价格太多了。在乳胶中，您只需要要求引擎更改字体即可。它将为您选择适当的当前字体。

另一个功能是许多所谓的文档类。这些是辅助输入文件，其中包含与特定文档类型相对应的Tex内部参数的值，例如书，文章，信件或其他任何内容。

乳胶还包括对文档作者可能方便的各种功能的支持。这些功能通常集中在称为软件包的辅助输入文件中。在包装中，您可以找到用于数学排版，绘制图形的高级工具，对不属于乳胶分布的字体的支持等。

这是相对较小的例子：


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

本文档是使用您常用的 \LaTeX 编译器编译“sample.tex”文件后的输出。该文件可以很好地展示“.tex”文件的基本结构，以及排版涉及数学符号和表达式的文档所需的许多最基本命令。有关每个命令工作原理的更多说明，请参阅我们课程网页上的链接。

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

这是输出的两页：

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Example Page 1">![示例第1页](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Example Page 2">![示例第2页](/tex/images/net/tutorial/example-page-2.png)</a>


自然，我们不会假装对“什么是乳胶？”这个问题有任何完整的答案，因为这是大量信息。由于编写乳胶文件仍在编程中，因此，如果您想更好地了解它，则必须花一些时间。你想要还是不想要。

**您还可以查看基于[Aspose.TeX for .NET api](https://products.aspose.com/tex/net/)的免费[Web App](https://products.aspose.app/tex/conversion/latex/)。**