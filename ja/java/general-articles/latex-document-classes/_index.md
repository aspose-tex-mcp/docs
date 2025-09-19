---
translation: true
template: /templates/_template-java.md
linktitle: ラテックスドキュメントクラス
title: ラテックスドキュメントクラス
weight: 20
url: /java/latex-document-classes/
keywords: ラテックスの記事クラス、ラテックスドキュメントクラス、ラテックスドキュメントテンプレート、ラテックス記事、ラテックスブック、ラテックススライド、ラテックスレポート、ラテックスレター、ドキュメントクラスのラテックス
description: この記事は、LaTexドキュメントクラスとそのオプションの簡潔なダイジェストです。また、いくつかの例を提供します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ラテックスのドキュメントクラスとは何ですか？

LaTeXは、すべての文書作成者が従わなければならないいくつかの規則を定義しています。また、本質的には組版プログラムであるソースファイルの構造も定義しています。この構造によれば、文書のソースコードには、文書の内容そのものを記述する部分（*本体*）が必ず含まれます。*本体*は、`\begin{document}`と`\end{document}`という2つのコマンドで囲まれています。LaTeXは、本体の末尾以降の内容を無視します。`\begin{document}`より前のソースコードの部分は、*プリアンブル*と呼ばれます。

通常、プリアンブルの最初のコマンドは「\ documentClass」でなければなりません。これは、**documentクラス**の名前である単一の必要な引数を取得します。ドキュメントクラス自体は、特定のタイプのドキュメントの開発に適しており、単一名で収集されたフォーマットパラメーター、レイアウトメトリック、マクロなどのセットです。この記事では、ラテックスが組み込まれたLaTex **Precedined**ドキュメントクラスについて説明し、それらの用途、違い、および類似性を示します。また、「documentclass`コマンドが取得できるというオプションの引数がいくつかあり、ドキュメントの外観をカスタマイズすることについても言及します。

## 事前に定義されたラテックスドキュメントクラス

標準のラテックスには、次のドキュメントクラスが含まれています。

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | LaTeX の article クラスは、科学雑誌の記事、短いレポート、プログラムドキュメントなど、章やパートへの複雑な分割を必要としない短い文書全般を作成するために使用されます。 |
| **report** | LaTeX の report クラスは、複数の章を含む長い記事 (小冊子や論文など) に使用されます。 |
| **book** | これは実際の書籍の組版に使用されます。章とパート、2 種類のページ、前付、後付など、印刷された書籍に適したあらゆる種類の組版標準が含まれています。 |
| **slides** | スライドの作成に使用できますが、この目的にはより強力な外部パッケージ [beamer](https://ctan.org/pkg/beamer) があります。 |
| **letter** | このドキュメント クラスは手紙を書くために使用されます。 |

最初の2つのドキュメントクラスは基本です。したがって、**記事**から始めてください。必要なクラスがわからないときはいつでも。

**レポート**クラスは非常に似ています。 **記事**との主な違いは、`\ Chapter`コマンドに章を挿入できることですが、**記事**ドキュメントクラスはそのようなセクションユニットを定義しないことです。

## ラテックス**book**クラス

書籍は、誤植的な基準では、本とたとえば報告書や記事の主な違いである最前線と背面の問題があります。本の最前線は、通常、ハーフタイトルページ、メインタイトルページ、著作権ページ、序文または序文、およびテーブルコンテンツで構成されています。義務の少ない部分は、謝辞、献身、数字のリスト、テーブルのリスト、同じシリーズの他の本のリスト、およびその他の編集およびプロモーションコンテンツです。バックマターには通常、インデックスが含まれており、後語、謝辞、書誌、コロフォンなどが含まれる場合があります。

Book Documentクラスでは、前述の論理構造を作成するコマンドを提供しますが、他のドキュメントクラスはそのようなツールを提供できません。ただし、異なる出版社は通常、独自のスタイルに応じて構造をレイアウトするための追加のコマンドを備えた独自のパッケージを持っています。

## 前部、主物質、および背面コマンド

主な問題は、最初の章または部分から始まり、付録で終わる本の本文を含むものです。フロント、メイン、バックの問題は、それぞれ「\ frontmatter」、 `\ mainmatter`、および` \ backmatter`コマンドから始まります。

> 標準的な書籍クラスでは、前付ページはローマ数字で番号付けされ、本付ページと後付ページはアラビア数字で番号付けされます。

> `\chapter` コマンドは、前付と後付に章番号を生成しませんが、目次にはエントリを作成します。これは通常、序文や謝辞のセクションを作成するために使用されます。このような章では、他のセクション作成コマンド（`\section*` や `\subsection` など）の星印バージョンのみを使用する必要があります。

## ラテックスブッククラスを使用する例

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

以下は、このラテックスコードによって生成されたドキュメント構造です。

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![出力の例](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![出力の例](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

そして、ここに内容の表が詳細にあります。

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![目次](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **奇妙な**および**偶数**本のページ

本では、**奇妙な**と**偶数**ページは同じように見えません。マージン、および通常はヘッダーとフッターは、本をバインドすると読みやすくするために異なります。 LaTex Documentクラスはこれを処理します、そして、あなたはそれを見つけるかもしれません：
- **左(偶数)**ページの左マージンが大きく、ページ番号はページの右上にあり、現在の章のタイトルは右側にあります。
- **右(奇数)**ページには右マージンが大きく、ページの右上にページ番号のみがあります。

新しい章は常に正しいページから始まります。ページヘッドが空で、足の中央にページ番号のみが残ることに注意してください。

## **要約**セクションがありません

記事やレポートなどのアカデミックペーパーには、通常、**"abstract"**という紹介セクションが含まれています。その目的は、ドキュメントで説明されているトピックの概要を簡単に説明することです。タイトルの直後と目次の前に印刷されている場合があります。ラテックスでは、そのような構造が「抽象」環境として実装されています。

**要約**環境は、本のドキュメントクラスによって提供されていません。これは、記事やレポートクラスとのもう1つの違いです。

## ラテックス**レター**クラス

現在、文字文書のクラスはやや昔ながらのように見えます(実際にはスライドドキュメントクラスもそうです)。伝統的な手紙を作成し、封筒に入れて郵便で送信する必要がある場合は、このドキュメントクラスがおそらく役立つでしょう。これは一種の時代遅れのコミュニケーション方法ですが、文字のような文書を準備する必要がある場合がある場合もあります。たとえば、推薦状またはプレゼンテーションの手紙。

したがって、ここにクラスの簡単な概要があります。

単一の入力ファイルから、任意の数の手紙を作成できます。氏名と住所は通常、すべての手紙に共通で、文書のプリアンブルで指定します。差出人住所は`\address`コマンドで宣言します。このコマンドは、`\\`（LaTeXの改行コマンド）で区切られた複数行を引数として受け入れます。同様に、`\signature`コマンドは、氏名、役職などを含む複数行を受け入れます。ただし、差出人住所と署名はいつでも変更できます。

各手紙は、受取人の氏名と住所を引数として必要とする個別の`letter`環境によって生成されます。手紙は`\opening`コマンドで始まり、挨拶文を生成します。`\closing`コマンドで終わり、結びの言葉と署名を生成します。手紙の本文は通常のLaTeX入力です。

これらのコマンドはすべて使いやすく、ラテックスが自動的に文字のフォーマットを処理するため、非常に強力です。だから、コマンドの数を怖がらせたり混乱させたりしないでください。

以下の例は、これがすべて機能する方法を示しています。

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

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![文書のクラスの例](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

現在の日付も自動的に生成されることに注意してください。ただし、「\ todany」コマンドを再定義して、手紙の日付を変更できます。これがあなたのやり方です：

```tex
\renewcommand{\today}{01th of March of 2492}
```

この宣言を特定の「文字」環境に挿入すると、その文字のみの日付が変更されます。それ以外の場合は、プリアンブルに挿入すると、入力ファイルによって生成されるすべての文字に対して有効になります(特定の「文字」環境に挿入されていない限り)。

## ラテックスドキュメントクラスオプション

次に、記事の冒頭で言及されている`documentClass`コマンドオプションを見てみましょう。

### フォントサイズ

フォントサイズは、10pt、11pt、12ptの3つのオプションによって制御されます。デフォルトでは、10ptが有効です。これらのオプションは、ある時点で変更されない限り、ドキュメント全体で使用されるベースフォントサイズを決定します。また、いくつかのフォーマット寸法のスケール因子にも影響します。

```tex
\documentclass[12pt]{article}
```

> これらのオプションは `slides` クラスでは認識されません。

### 紙のサイズ

ここでの「用紙サイズ」とは、文書を**印刷する予定**の用紙のサイズを指します。**PDF TeX**などの組版システムの出力におけるページ表現のサイズには影響しません。用紙サイズは6つのオプションで制御されます: `letterpaper` (8.5in x 11in)、`legalpaper` (8.5in x 14in)、`executive paper` (7.25in x 10.5in)、`a4paper` (210mm x 297mm)、`a5paper` (148mm x 210mm)、`b5paper` (176mm x 250mm)。デフォルトは`letterpaper`です。

```tex
\documentclass[a4paper]{article}
```

### ページオリエンテーション

`Landscape`オプションにより、選択した用紙サイズのランドスケープ印刷の出力がフォーマットされます。事実上、ラテックスは、型刻印プロセスに沿って使用されているところならどこでも幅と高さの寸法を交換します。 「ポートレート」オプションにはそのような効果がなく、デフォルトで使用されます。

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### ドラフトモード

TeXは段落構築の過程で適切な改行ができない場合（「良さ」評価アルゴリズムを搭載）、テキストエリアの右端からはみ出す行を生成します。また、このような状況はトランスクリプトファイル（および端末）に「overfull box」警告とともに報告されます。`draft`オプションを指定すると、LaTeXは出力においてこのような行を黒枠で囲みます。`final`オプションを指定すると黒枠は生成されず、デフォルトで使用されます。

### 2つのサイド印刷

`openany` オプションを指定すると、章を任意のページから開始できます。一方、`openright` オプションを指定すると、すべての章が右ページから開始されます。`report` クラスではデフォルトは `openany`、`book` クラスでは `openright` です。どちらのオプションも、他の文書クラスでは認識されません。

### タイトルのページ

`titlepage` オプションを指定すると、LaTeX は `\maketitle` コマンドで生成されたタイトル用に別のページを作成します。また、`abstract` 環境は新しいページで要約を開始し、その後で改ページを行います。`article` クラスを除くすべてのクラスではデフォルトは `titlepage` です。`article` クラスではデフォルトは `notitlepage` です。

> これらのオプションは `letter` クラスでは認識されません。

### 番号付きの表示式

`leqno`オプションは、デフォルトの動作である右側の代わりに、左側のラテックスプット方程式(表示数学式)数値またはタグを作成します。

### 表示された式アライメント

`fleqn` オプションは、表示される数式を左揃えにします。それ以外の場合は、デフォルトで中央揃えになります。
