---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 文書クラス | Aspose.TeX チュートリアル
title: LaTeX 文書クラス
weight: 20
url: /java/latex-document-classes/
keywords: LaTeX 記事クラス、LaTeX 文書クラス、LaTeX 文書テンプレート、LaTeX 記事、LaTeX ブック、LaTeX スライド、LaTeX レポート、LaTeX レター、LaTeX の文書クラス
description: この記事は、LaTeX 文書クラスとそのオプションについて簡潔にまとめたものです。また、いくつかの例も示しています。
lastmod: "2026-02-20"
---

{{<section overview>}}

## LaTeX における documentclass とは何か

LaTeX は、すべての文書作成者が従うべき規則を定義しています。また、ソースファイルの構造も定義しており、これは本質的に組版プログラムです。この構造に従うと、文書の本文（*body*）を担当する部分は `\begin{document}` と `\end{document}` の 2 つのコマンドで囲まれなければなりません。LaTeX は本文の終端以降の内容は無視します。` \begin{document}` の前のソースコードの部分は *preamble*（前文）と呼ばれます。

通常、前文の最初のコマンドは必ず `\documentclass` で、必須引数として **文書クラス** の名前を取ります。文書クラス自体は、特定の種類の文書を作成するために適した書式パラメータ、レイアウト指標、マクロ等の集合です。本稿では、標準 LaTeX に組み込まれている **事前定義済み** の文書クラスとその使い方、違い、類似点を紹介します。また、` \documentclass` コマンドが取れるオプション（外観をカスタマイズできるもの）についても触れます。

## 事前定義済みの LaTeX 文書クラス

標準 LaTeX には以下の文書クラスが含まれています。

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | LaTeX の article クラスは、学術誌の記事、短いレポート、プログラムのドキュメント、そして一般に章や部に分割する必要がない短い文書を作成するために使用されます。 |
| **report** | LaTeX の report クラスは、いくつかの章を含む長めの記事（小冊子や学位論文など）に適しています。 |
| **book** | 本格的な書籍を組版するためのクラスです。印刷書籍に適したすべての組版標準を備えており、章・部、異なるページ様式、前付け・後付けなどが含まれます。 |
| **slides** | スライドを作成することもできますが、より強力な外部パッケージ [beamer](https://ctan.org/pkg/beamer) の方が一般的に推奨されます。 |
| **letter** | 手紙を書くための文書クラスです。 |

最初の 2 つのクラスは基本的なものです。どのクラスを使うべきか分からない場合は、まず **article** から始めてください。

**report** クラスは非常に似ていますが、**article** との主な違いは `\chapter` コマンドが使用できる点です。一方、article クラスはそのような章単位を定義していません。

## LaTeX の **book** クラス

活版印刷の標準では、書籍は前付け（front matter）と後付け（back matter）を持ちます。これが書籍とレポートや記事との大きな違いです。書籍の前付けには、通常、半タイトルページ、メインタイトルページ、著作権ページ、序文や前書き、目次などが含まれます。必須ではない項目として、謝辞、献辞、図目録、表目録、同シリーズの他の書籍一覧、その他の編集・宣伝用コンテンツがあります。後付けには索引やあとがき、謝辞、参考文献、綴じ代（colophon）などが含まれます。

book クラスは、上記のような論理構造を生成するためのコマンドを提供しますが、他の文書クラスにはそのようなツールはありません。出版社ごとに独自のパッケージや追加コマンドが用意されていることもあります。

## 前付け、本文、後付けのコマンド

本文（body）は書籍の本体部分で、最初の章または部から付録までを含みます。前付け・本体・後付けはそれぞれ `\frontmatter`、`\mainmatter`、`\backmatter` コマンドで開始します。

> 標準の book クラスでは、前付けのページ番号はローマ数字で付けられ、本体と後付けのページ番号はアラビア数字で付けられます。

> `\chapter` コマンドは前付け・後付けでは章番号を付けませんが、目次にはエントリが作成されます。これは序文や謝辞セクションを作る際に通常使用されます。そのような章の中では、他のセクショニングコマンド（例：`\section*`、`\subsection`）は星付きバージョンのみを使用すべきです。

## LaTeX book クラスの使用例

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

以下の画像は、上記 LaTeX コードから生成された文書構造です。

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Example output](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

そして、目次の詳細は以下の通りです。

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Table of contents](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## 書籍における **奇数** ページと **偶数** ページ

書籍では、**奇数** ページと **偶数** ページでレイアウトが異なります。余白やヘッダー・フッターも左右で変わり、製本後の見やすさが向上します。LaTeX の文書クラスはこの違いを自動で処理します。具体的には：

- **左（偶数）** ページは左余白が大きく、ページ番号はページ上部右側に配置され、現在の章タイトルは右側に表示されます。
- **右（奇数）** ページは右余白が大きく、ページ番号はページ上部右側にのみ表示されます。

新しい章は常に右ページ（見開きの右側）から開始され、ページヘッダーは空白で、フッターの中央にページ番号が入ります。

## **Abstract** セクションがない

学術論文（記事やレポート）には、通常「**Abstract**」と呼ばれる導入部が含まれます。これは文書のテーマを簡潔に概観するためのものです。LaTeX ではこの構造は `abstract` 環境で実装されます。

book クラスには `abstract` 環境が用意されていないため、article や report クラスとはこの点で異なります。

## LaTeX **letter** クラス

現在、letter クラスはやや時代遅れと見なされています（slides クラスも同様です）。しかし、封筒に入れて郵送するような伝統的な手紙を作成する必要がある場合には便利です。たとえば、推薦状や紹介状などです。

以下に概要を示します。

1 つの入力ファイルで複数の手紙を生成できます。差出人名と住所は通常、前文で共通指定します。差出人住所は `\address` コマンドで宣言し、`\\` で区切った複数行を引数に取ります。同様に `\signature` コマンドで差出人の署名（名前、役職など）を複数行で指定できます。差出人住所や署名は任意の場所で変更可能です。

各手紙は `letter` 環境で生成され、受取人の名前と住所を引数として取ります。`\opening` コマンドで挨拶文を、`\closing` コマンドで結びの言葉と署名を生成します。手紙本文は通常の LaTeX 入力です。

これらのコマンドは直感的で強力です。コマンドの数に圧倒されないでください。

以下は実際の使用例です。

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![A letter document class example](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

現在の日付も自動的に生成されますが、`\today` コマンドを再定義すれば日付を変更できます。例：

```tex
\renewcommand{\today}{01th of March of 2492}
```

この宣言を特定の `letter` 環境内に入れれば、その手紙だけの日付が変わります。前文に入れれば、同一入力ファイルで生成されるすべての手紙に適用されます（ただし、特定の `letter` 環境内で上書きすればそちらが優先されます）。

## LaTeX 文書クラスのオプション

ここからは、冒頭で触れた `\documentclass` コマンドのオプションを見ていきます。

### フォントサイズ

フォントサイズは 10pt、11pt、12pt の 3 つのオプションで制御され、デフォルトは 10pt です。これらは文書全体の基準フォントサイズを決定し、その他の書式寸法のスケールにも影響します。

```tex
\documentclass[12pt]{article}
```

> これらのオプションは `slides` クラスでは認識されません。

### 用紙サイズ

「用紙サイズ」は、文書を **印刷** する際に使用する紙のサイズを指します。PDFTeX などの出力形式のページサイズ自体には影響しません。6 つのオプションがあります：`letterpaper`（8.5in × 11in）、`legalpaper`（8.5in × 14in）、`executivepaper`（7.25in × 10.5in）、`a4paper`（210mm × 297mm）、`a5paper`（148mm × 210mm）、`b5paper`（176mm × 250mm）。デフォルトは `letterpaper` です。

```tex
\documentclass[a4paper]{article}
```

### ページ向き

`landscape` オプションは、選択した用紙サイズ上で横向き印刷用に出力をフォーマットします。実質的に幅と高さが入れ替わります。`portrait` オプションはそのような効果がなく、デフォルトで使用されます。

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### 下書きモード

TeX が十分に良好な改行を見つけられない場合（「良さ」推定アルゴリズムに基づく）、テキスト領域の右端をはみ出す行が生成されます。これらはトランスクリプトや端末に「overfull box」警告として報告されます。`draft` オプションを付けると、LaTeX はそのような行を黒枠でマークします。`final` オプションは黒枠を出さず、デフォルトで使用されます。

### 両面印刷

`openany` オプションは章を任意のページで開始できるようにし、`openright` オプションはすべての章を右側のページから開始させます。`report` クラスのデフォルトは `openany`、`book` クラスは `openright` です。他の文書クラスではこれらのオプションは認識されません。

### タイトルページ

`titlepage` オプションを付けると、`\maketitle` コマンドで生成されるタイトルが別ページになります。また、`abstract` 環境は新しいページから始まり、終了後に改ページが入ります。デフォルトは `titlepage`（`article` クラスは `notitlepage`）です。

> これらのオプションは `letter` クラスでは認識されません。

### 表示数式の番号位置

`leqno` オプションは、表示数式（数式環境）の番号（タグ）を左側に配置します。デフォルトは右側です。

### 表示数式の配置

`fleqn` オプションは表示数式を左揃えにします。デフォルトでは中央揃えです。
