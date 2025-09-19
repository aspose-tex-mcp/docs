---
translation: true
template: /templates/_template-net.md
title: ラテックスとは何ですか？ 
linktitle: ラテックスとは何ですか？
weight: 16
url: /net/what-is-latex/
keywords: ラテックスとは、ラテックスそれは何ですか
description: 「ラテックスとは？」という質問に答えるために最も印象的な機能の1つは、新しいフォント選択スキーム(NFSS)であることに言及する価値があります。
lastmod: "2025-06-09"
---

{{<section overview>}}

それで、ラテックスとは何ですか？

ラテックスは、要するに[Tex](/tex/{{lang.url-fragment}}net/what-is-tex/)形式です。

LaTeX（*LAH-tekh または LAY-tekh*、しばしばLATEXと表記されます）は、文書作成用のソフトウェアシステムで、1980年代初頭に<a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a>の<a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a>によって開発されました。これは<a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a>で説明されている内容です。

「ラテックスとは？」という質問に答えるその機能のいくつかについて言及したいと思います。

ラテックスの最も印象的な機能の1つは、新しいフォント選択スキーム(NFSS)です。これは、元のTexで機能したため、新しいフォント全体を定義するのではなく、現在のフォントの個々のプロパティを変更できるマクロサブシステムです(プレーンテックスもこれにはあまり提供しませんでした)。たとえば、コンピューターモダンローマイタリックである現在のフォントがあり、別のフォントファイルにある物理的な同じタイプの太字に切り替えたいと考えています。元のTexでは、フォントファイル名にマッピングされたシーケンスを制御する必要があるため、切り替えるには別のコマンドを呼び出すだけです。しかし、価格はあまりにも多くの制御シーケンスです。ラテックスでは、エンジンに書体を変更するように依頼する必要があります。適切な現在のフォントを選択します。

別の機能は、いわゆるドキュメントクラスの多数です。これらは、本、記事、文字、その他など、特定のドキュメントタイプに対応するTEXの内部パラメーターの値を含む補助入力ファイルです。

ラテックスには、ドキュメント著者にとって便利なさまざまな機能のサポートも含まれています。これらの機能は通常、パッケージと呼ばれる補助入力ファイルで収集されます。パッケージでは、数学タイプセット、グラフィックの描画、ラテックス分布の一部ではないフォントのサポートなどの高度なツールを見つけることができます。2D化学式の描画でも。

これが比較的小さな例です：


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

このドキュメントは、お好みの \LaTeX コンパイラを使用してコンパイルされたファイル ``sample.tex'' の出力を表しています。このファイルは、 ``.tex'' ファイルの基本構造を示す良い例となるだけでなく、数学記号や数式を含むドキュメントの組版に必要な基本的なコマンドの多くも網羅しています。各コマンドの動作に関する詳しい説明については、コースのウェブページにあるリンクを参照してください。

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

そして、ここに出力の2ページがあります：

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Example Page 1">![例1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Example Page 2">![例2](/tex/images/net/tutorial/example-page-2.png)</a>


当然のことながら、「ラテックスとは何ですか？」という質問に対する完全な答えがあるふりをしていません。これは非常に多くの情報だからです。 LaTexファイルは引き続きプログラミングされているため、それをよく知りたい場合は、時間を費やす必要があります。あなたはそれが欲しいかどうか。

**[.NET APIのAspose.TeX](https://products.aspose.com/tex/net/)に基づいて構築された無料の[Webアプリ](https://products.aspose.app/tex/conversion/latex/)をチェックアウトすることもできます。**