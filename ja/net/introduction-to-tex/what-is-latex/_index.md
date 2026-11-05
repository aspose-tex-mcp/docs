---
translation: true
template: /templates/_template-net.md
title: LaTeXとは何ですか？ | Aspose.TeX チュートリアル
linktitle: LaTeXとは何ですか？
weight: 16
url: /net/what-is-latex/
keywords: LaTeXとは何か, LaTeXとは, LaTeXについて
description: 「LaTeXとは何か？」という質問に答えるには、その最も印象的な機能のひとつである New Font Selection Scheme (NFSS) に言及する価値があります。
lastmod: "2026-11-04"
---

{{<section overview>}}

では、LaTeXとは何でしょうか？

LaTeXは[TeX](/tex/{{lang.url-fragment}}net/what-is-tex/)フォーマットです、要するに。

LaTeX（*LAH‑tek または LAY‑tek*、しばしば LATEX と表記されます）は、1980年代初頭に <a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> が <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a> で作成した文書作成用ソフトウェアシステムです。これは <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a> が説明している内容です。

「LaTeXとは何か？」という質問に答えるにあたり、まずその特徴のいくつかを挙げておきます。

LaTeXの最も印象的な機能のひとつは New Font Selection Scheme (NFSS) です。これはマクロサブシステムで、現在のフォントの個々の属性を変更できるようにします。従来の TeX では新しいフォント全体を定義する必要があり（Plain TeX でも同様でした）、たとえば現在のフォントが Computer Modern Roman のイタリック体で、同じ種類の太字フォントが別のフォントファイルに存在する場合、元の TeX ではフォントファイル名に対応する制御シーケンスを呼び出す必要がありました。価格は制御シーケンスが多数必要になることです。LaTeX ではエンジンにフォントの切り替えを指示するだけで済み、適切なフォントが自動的に選択されます。

別の特徴として、いわゆる文書クラスがあります。これは特定の文書タイプ（書籍、記事、レターなど）に対応した TeX の内部パラメータの値を含む補助入力ファイルです。

LaTeX には、文書執筆者にとって便利なさまざまな機能がパッケージという形で提供されています。これらのパッケージには、数式組版、グラフィック描画、配布に含まれないフォントのサポートなどの高度なツールが含まれます。2D 化学構造式の描画にも対応しています。

以下は比較的小規模な例です。

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

このドキュメントは、`sample.tex`ファイルをお好みの\LaTeX コンパイラでコンパイルした出力です。このファイルは、`.tex`ファイルの基本構造を示す良い例となるだけでなく、数学記号や数式を含む文書の組版に必要な基本的なコマンドの多くも網羅しています。各コマンドの動作に関する詳しい説明については、コースのウェブページにあるリンクをご覧ください。

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
\put(40,40){\line(1,2){10}} \put(60,40){\line(-1,2){10}} \put(40,0){\line(1,0){20}} % nose
\put(50,20){\oval(80,10)[b]} % mouth
\multiput(0,90)(4,0){10}{\line(1,3){4}}  % left eyebrow
\multiput(100,90)(-4,0){10}{\line(-1,3){4}}  % right eyebrow
\end{picture}
\end{center}
\end{document}
```

そして、以下の2ページの出力例です:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Example Page 1">![Example Page 1](/tex/images/net/tutorial/example-page-1.png)</a>
<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Example Page 2">![Example Page 2](/tex/images/net/tutorial/example-page-2.png)</a>


当然ながら「LaTeXとは何か？」という質問に対して完全な答えを用意できるわけではありません。情報量が多く、LaTeX ファイルを書くことはプログラミングに近い作業ですので、習熟するにはある程度の時間が必要です。必要かどうかはご自身で判断してください。

**また、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) を基に構築された無料の[ウェブアプリ](https://products.aspose.app/tex/conversion/latex/)もご確認ください。**

## 論理マークアップと直接的な書式設定

コンテンツの作成と視覚的なスタイル設定を同時に行う従来のWYSIWYG（見たままが得られる）型デスクトップパブリッシングツールとは異なり、LaTeXでは、コンテンツ（内容）とプレゼンテーション（見た目）を明確に分離することが求められます。

LaTeXで執筆する際、作成者は「見た目」を気にするのではなく、セマンティック（意味論的）なマークアップを使用して、各要素が何であるか（例: `\section{Introduction}`、`\begin{equation}`）を定義します。基盤となる組版エンジンが、複雑なレイアウト規則、カーニング（文字間隔の調整）、改行、ページ番号の付与、数式の配置などを自動的に処理します。これにより、大規模で複雑な技術文書や科学論文全体にわたって、タイポグラフィの一貫性が完全に保証され、開発者や研究者は、煩雑な手作業による書式設定から解放されます。

## 主な機能

以下は、標準的なLaTeXの機能がAspose.TeX内でどのようにプログラム的に処理されるかを示した比較表です。

| **機能/システム** | **標準的なTeXディストリビューション (CLI)** | **Aspose.TeX for .NET エンジン** |
| :- | :- | :- |
| **数式の組版** | `amsmath` / `amssymb` を使用して処理 | ネイティブに解析され、ベクター形式やラスター形式で出力 |
| **ドキュメントクラス** | ディスク上のローカルな `.cls` ファイルが必要 | カスタムまたは仮想の `IInputWorkingDirectory` を介して読み込み |
| **相互参照および目次 (TOC)** | コマンドラインで複数回の実行（パス）が必要 | 2 回目のパスは `TeXOptions.Repeat` オプションで有効化 |
| **出力形式** | 別のツールを介して DVI、PS、または PDF を生成 | PDF、XPS、SVG、PNG、JPEG、BMP、TIFF への直接的な単一ステップ変換 |

**詳細はこちら:**

- [TeX 入出力 (tex-io)](/tex/{{lang.url-fragment}}net/tex-io/): `IInputWorkingDirectory` および `IOutputWorkingDirectory` が、どのようにストリームやディスクリソースを扱うかについて解説しています。
- [LaTeX グラフィックス (latex-graphics)](/tex/{{lang.url-fragment}}net/latex-graphics/): `graphicx` パッケージを使用して、`\includegraphics` で外部画像を取り込む方法について解説しています。 - [Aspose.TeX と Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/): 基盤となるマネージド・オブジェクト・モデルを理解する。