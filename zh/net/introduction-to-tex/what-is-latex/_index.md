---
translation: true
template: /templates/_template-net.md
title: LaTeX 是什么？
linktitle: LaTeX 是什么？
weight: 16
url: /net/what-is-latex/
keywords: 什么是 latex, latex 是什么
description: 要回答“什么是 LaTeX？”这个问题，值得一提的是其最令人印象深刻的特性之一是新字体选择方案（NFSS）。
lastmod: "2026-02-26"
---

{{<section overview>}}

所以，LaTeX 是什么？

LaTeX 是 [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/) 格式，简而言之。

LaTeX（*LAH-tekh 或 LAY-tekh*，通常写作 LATEX）是一个文档准备的软件系统，最初在 1980 年代初由 <a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> 在 <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a> 编写。这是 <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a> 所述。

回答 “什么是 LaTeX？” 时，我们想提及它的一些特性。

LaTeX 最令人印象深刻的特性之一是新字体选择方案（NFSS）。它是一个宏子系统，允许您更改当前字体的单个属性，而不是像原始 TeX 那样一次性定义整套新字体（Plain TeX 对此也几乎没有提供）。例如，您当前使用的是 Computer Modern Roman 斜体，而想切换到同类型的粗体，而该粗体实际存放在另一个字体文件中。在原始 TeX 中，您需要控制映射到字体文件名的控制序列，因此只需调用另一个命令即可切换，但这会产生大量的控制序列。而在 LaTeX 中，您只需请求引擎更改字形，它会为您选择合适的当前字体。

另一个特性是一系列所谓的文档类。这些是辅助输入文件，包含对应特定文档类型（如书籍、文章、信件等）的 TeX 内部参数值。

LaTeX 还包括对各种可能对文档作者便利的特性的支持。这些特性通常收集在称为宏包的辅助输入文件中。在宏包中，您可以找到用于数学排版、绘图、支持不在 LaTeX 发行版中的字体等高级工具，甚至用于绘制二维化学式。

下面是一个相对较小的示例：

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

本文档展示了使用您常用的 LaTeX 编译器编译 `sample.tex` 文件后的输出结果。该文件可以很好地展示 `.tex` 文件的基本结构，以及排版包含数学符号和表达式的文档所需的许多基本命令。有关每个命令的详细说明，请参阅我们课程网页上的相关链接。

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
$(1+x)^n = \sum_{i=0}^n {n \choose i} x^i$
\end{theorem}
\subsection{Taylor Series}
The Taylor series expansion for the function $e^x$ is given by
\begin{equation}
e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + \cdots = \sum_{n\geq 0} \frac{x^n}{n!}
\end{equation}
\subsection{Sets}
\begin{theorem}
For any sets $A$, $B$ and $C$, we have
$ (A\cup B)-(C-A) = A \cup (B-C)$
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

以下是两页输出示例：

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="示例页面 1">![示例页面 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="示例页面 2">![示例页面 2](/tex/images/net/tutorial/example-page-2.png)</a>


自然地，我们并不假装对 “什么是 LaTeX？” 这个问题有完整的答案，因为这涉及的信息量相当大。由于编写 LaTeX 文件仍然是一种编程活动，如果您想更好地熟悉它，需要花一些时间。您想不想了解都由您自行决定。

**您也可以查看基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 构建的免费 [Web 应用](https://products.aspose.app/tex/conversion/latex/)。**
