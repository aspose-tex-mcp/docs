---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX テーブル
title: LaTeX の表
weight: 50
url: /java/latex-tables/
keywords: LaTeX 表、表形式環境、LaTeX 表のデザイン、LaTeX での表の書式設定、LaTeX 表の組版、LaTeX 表のレイアウト、LaTeX 表の間隔、LaTeX 表のカスタマイズ、LaTeX 表の配置、LaTeX 表における複数行と複数列
description: この記事は、LaTeX で機能的で読みやすく、視覚的に魅力的かつプロフェッショナルな表を作成するための簡易ガイドです。
lastmod: "2024-09-20"
---

{{<section overview>}}

## 1. はじめに

表は、学術・ビジネス文書の明瞭さ、構成、視覚的魅力を高める重要な役割を果たします。複雑なデータや比較、関係性を構造化された、わかりやすい形式で提示する強力な手段です。その重要性を簡単にまとめると次の通りです。

1. **データ要約**: 表は、複数の段落で説明しなければならない情報を凝縮して示します。大量のデータを簡潔に提示でき、読者が要点を把握しやすくなります。

2. **明快な可視化**: 統計数値、調査結果、実験結果などの複雑なデータも、表を使うと効果的に提示できます。列と行の配置により、トレンドやパターン、外れ値を容易に見つけられます。

3. **比較分析**: 表は、異なるデータ集合を横に並べて比較できるようにします。製品仕様、財務実績、研究変数などを比較する際に、読者は一目で有意義な結論を導き出せます。

4. **論理的な構成**: 行と列にデータを分けることで、カテゴリ別に情報を整理できます。これにより読者は目的の情報をすぐに見つけられます。

5. **データの完全性**: 学術・ビジネスの場では、データの正確性が最重要です。表は、生データを直接示すことで、文章での説明による誤解のリスクを減らします。

6. **参照と引用**: ラベル付けされた表は、文中で特定の表を指し示す参照ポイントになります。読者は議論に沿って該当表をすぐに確認できます。

7. **視覚的エンゲージメント**: デザインの良い表は、テキストの単調さを和らげ、読者の興味を引きつけます。文書全体の美観とプロフェッショナリズムを向上させます。

8. **効率的な情報取得**: 忙しい研究者や実務家は、素早く情報を抜き出す必要があります。表は、段落を読むことなく目的のデータや詳細をすぐに見つけられます。

9. **標準化**: 学術研究では、実験手法、結果、統計解析などを示す標準化された表が頻繁に使用されます。これにより出版物間の一貫性が保たれ、再現性が向上します。

要するに、表は情報ハブとして機能し、データ主導の洞察を構造化かつ読者フレンドリーに提示します。その情報伝達力とアクセシビリティの高さは、学術・ビジネスコミュニケーションに不可欠です。

次に、LaTeX という強力な組版システムに目を向けましょう。LaTeX は従来のワードプロセッサの限界を超え、特に表組みの処理において高精度・エレガンス・汎用性を提供します。

LaTeX は単なる文書作成ツールではなく、タイポグラフィとテクノロジーが融合した芸術です。学術論文、レポート、プレゼンテーション、書籍の作成において、見た目の美しさと情報の明瞭さを両立させます。特に、複雑な表構造はデータ表現の基盤となります。

LaTeX では、表内情報の配置は単なる格子以上のものです。配置・間隔・スタイルが調和した「交響曲」のようにデータを洗練して提示します。表は視覚的ナラティブとなり、複雑なデータセットや関係性を優雅かつ正確に伝えます。

列幅の制御、セルの罫線・シェーディング、数式や記号の直接埋め込みなど、豊富なツールとパッケージが用意されており、あらゆる目的に合わせた表を作成できます。

美しさだけでなく、LaTeX はクロスリファレンス機構により表を文書内のナビゲーションポイントにし、マルチロウ／マルチカラムレイアウトで高度なデータ提示も可能にします。

このように、LaTeX は科学者・専門家・研究者にとって欠かせないツールです。注目を集め、情報を説得的に提示し、文書全体のインパクトを高める表作成技術を身につけましょう。

## 2. LaTeX の表の基本

LaTeX における表の根幹は `tabular` 環境です。ここで列・行・セルの内容を定義し、構造化された視覚的に整った表を作ります。

基本的な構成要素は次のとおりです。

1. **`tabular` 環境の開始**: 表は `tabular` 環境で囲みます。この環境で表のレイアウトを指定します。

2. **列の指定**: `tabular` 環境内で列数と配置を指定します。`l`（左揃え）、`c`（中央揃え）、`r`（右揃え）が基本です。また、縦線で区切る列や外枠線も指定できます。

3. **行の内容**: 各行はセルの内容を `&` で区切り、行末は `\\` で終えます。

4. **水平線**: `\hline` コマンドで行間や外枠に水平線を挿入できます。

### 簡単な例

以下は基本的な LaTeX 表の例です。

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}
```

この例では 3 列の中央揃え表を作成しています。出力は次のとおりです。

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

次の例は左寄せ・右寄せ列を混在させた表です。

```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

右外枠は二重線、ヘッダーも二重線で区切られ、列間の縦線はありません。

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

全幅に渡らない水平線も描けます。

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

`\cline{i-j}` は i 列目から j 列目までの線を引くコマンドです。

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![例の出力](latex-tables-3.jpg)</a>

列幅を固定した「段落」列も作れます。`p{幅}` を使います。

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

`\newline` の使用例です。

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

`array` パッケージを読み込むと、固定幅列に `m{幅}`（セル内容を中央揃え）や `b{幅}`（下揃え）も利用できます。

表を段落中にインラインで入れたい場合、ベースライン位置を指定できます。`[t]`, `[c]`, `[b]` オプションで上・中央・下揃えを選択します。

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

ここではベースラインを表の下部に合わせています。

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### 複数列の一括指定

同一揃えの列が多数ある場合は `*{num}{format}` 構文で一括指定できます。

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### `>{\command}` と `<{\command}` を用いた列指定

`array` パッケージがあると、列要素の前後にコマンドを挿入できます。以下は 2 列を中央揃えにし、左列を太字にする例です。

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. 表レイアウトのカスタマイズ

LaTeX の表では、間隔調整が重要です。適切な余白は可読性を高め、内容が詰まりすぎるのを防ぎます。主な調整項目は次のとおりです。

### 列間の間隔

列間の余白はデフォルトで `\setlength{\tabcolsep}{value}` で変更できます。値を大きくすれば列間が広がります。デフォルトは `6pt`。

### 行間の間隔

行間は `\renewcommand{\arraystretch}{value}` で調整します。値を大きくすると行が伸び、垂直方向の余白が増えます。デフォルトは `1.0`。

行末に `\\[skip]` と書くことで、特定の行だけスキップ幅を指定することもできます。

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### `@` と `!` を用いた表現

`array` パッケージが読み込まれていると、`@{...}` または `!{...}` で列区切り文字をカスタマイズできます。`@{...}` は列間のスペースを置き換え、空にすれば間隔を消せます。

次の基本的な表を例にします。

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

列記述を変えると次のようになります。

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

元の間隔を保ちつつ変えたい場合は `!{...}` を使います。

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

小数点で揃える例:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### `dcolumn` パッケージの使用

`dcolumn` パッケージは小数点で揃える新しい列指定子 `d` を提供します。以下は基本的な使用例です。

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } % #1 は小数点以下の最大桁数
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

小数点揃え列は数式モードで組版されるため、ヘッダーには `\mathrm` を使っています。ヘッダーがテキストの場合は、`\multicolumn{1}{c}{Decimal}` のように `\multicolumn` で中央揃えにすると見た目が良くなります。

## 4. セルの結合

水平・垂直にセルを結合したやや複雑な表を作成できます。

### 複数列にまたがるセル

セルを複数列に跨げる基本構文は `\multicolumn{num_cols}{alignment}{contents}` です。`num_cols` は結合列数、`alignment` は `l`, `c`, `r` または `p{幅}`、`contents` がセルの内容です。

例:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### 複数行にまたがるセル

`multirow` パッケージを使用します。構文は `\multirow{num_rows}{width}{contents}` です。

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

`multirow` を使う場合、結合対象の下の行では空セルを入れる必要があります。

### 両方向に跨ぐセル

以下は横方向・縦方向に同時に跨がるセルの例です。

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

`\multicolumn{1}{` は左右両端の罫線を描くために使用します。`multirow` と組み合わせても、最初の行だけ垂直罫線が描かれるので、続く行でも `\multicolumn{1}{` を付けて補完します。

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. 表のサイズ調整

`graphicx` パッケージの `\resizebox{width}{height}{object}` を使うと、`tabular` 環境を指定した幅・高さに伸縮できます。以下は幅 12 cm にリサイズし、アスペクト比は保つ例です。

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

同様に `\scalebox{ratio}{object}` で比率指定も可能です。

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. 表の配置

`table` 環境に入れるとページ上の配置が簡単に制御できます。

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

利用できる配置オプションは次のとおりです。

- `h` – **ここ** におおよそ配置
- `t` – ページ **上部** に配置
- `b` – ページ **下部** に配置
- `p` – 表専用の別ページに配置
- `!` – LaTeX の内部パラメータを上書き
- `H` – **正確にこの場所** に配置（`h!` に相当）

`table` 環境内で `\centering` を付けると横方向の中央揃えができます。

## 7. キャプション・ラベル・参照

`\caption` で表にキャプションを付けられます。出力では「Table N.」という接頭辞が自動付与されます。`\label` と `\ref` を使うと、文書中の任意の場所から表を参照できます。

例:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

1 行目の参照は `\label` が付与した番号に自動置換されます。

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. 表の色付け

### 行の色を変える

`xcolor` パッケージに `table` オプションを付けて読み込むと、行ごとに異なる色を付けられます。`\rowcolors{starting_row}{odd_color}{even_color}` を `tabular` 環境の前に置きます。

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

`\hiderowcolors` はその行以降のハイライトを停止し、`\showrowcolors` で再開します。

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### 個別セルの色付け

`xcolor` で特定セルに色を付けることもできます。

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### `colortbl` パッケージの使用

`colortbl` は `\columncolor` コマンドで列全体の色を指定できます。`array` パッケージも同時に読み込む必要があります（`xcolor` も忘れずに）。

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-20.jpg)</a>

行の色は `\rowcolor` で指定し、行の先頭で使用します。構文は `\columncolor` と同じです。

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

縦罫線にも色を付けられます。

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

`\\arrayrulewidth` の設定で罫線の太さを変更できます。

`\hline` や `\cline` に色を付けるのはやや手間がかかりますが、`\arrayrulecolor` を使えば全体または局所的に色を変更できます。

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % すべての罫線を青に
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![例の出力](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. 長い表の作成

`tabular` 環境はページ分割ができません。長い表はページ下部で途切れてしまいます。そこで `longtable` パッケージを使用します。`longtable` は `tabular` と同様の構文ですが、ページ跨ぎが可能です。

以下は `longtable` の主な機能を示す例です。

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % 1 ページ目の上部に表示

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % 2 ページ目以降の上部に表示

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % 最終ページ以外の下部に表示

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % 最終ページの下部に表示

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  …（以下同様に多数の行が続く）…
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  …（省略）…
\end{longtable}
```

このコードは 2 ページにわたる出力を生成します。

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![例の出力](/tex/images/java/tutorial/latex-tables-24.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![例の出力](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

TeX のビルド回数が足りないと期待通りの結果が得られないことがあります。数回のコンパイルが必要です。

## 10. 複合的な表の例

以下は上記機能を多数組み合わせたやや高度な表です。

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % ページ分割のテスト用

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %少し余白を

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

`longtable` の前に `\newcolumntype` で列タイプを定義し、`>{...}` で色・配置・フォント・幅を指定しています。結果は次のとおりです。

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![例の出力](/tex/images/java/tutorial/latex-tables-26.jpg)</a>
<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![例の出力](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. ベストプラクティスとヒント

LaTeX で表を組む際のベストプラクティスと実用的なヒントをまとめました。

1. **意味のある列ヘッダーを付ける**  
   - 読者が内容を理解しやすいよう、明確で説明的なヘッダーを使用します。

2. **数値は小数点で揃える**  
   - 数値データは小数点で揃えると読みやすくなります。`dcolumn` パッケージが便利です。

3. **縦罫線はなるべく使わない**  
   - プロの出版物では縦罫線を避け、水平罫線を最小限に抑えるのが一般的です。

4. **一貫性を保つ**  
   - フォント、サイズ、揃え方など、文書全体で統一したスタイルを維持します。

5. **セルの内容は最小限に**  
   - セルに過剰なテキストを入れないようにし、必要なら行や列を増やします。

6. **キャプションとラベルを付ける**  
   - 表の上下に情報的なキャプションを入れ、`\label` で参照できるようにします。

7. **`multirow` と `multicolumn` は適度に**  
   - 結合は便利ですが使いすぎると表が読みにくくなります。

8. **過度に複雑な表は避ける**  
   - データが多すぎる場合は、複数の小さな表に分割するか、グラフなど別の可視化手段を検討します。

9. **間隔は慎重に調整**  
   - `\setlength{\tabcolsep}{value}` と `\renewcommand{\arraystretch}{value}` で列間・行間の余白を最適化します。

10. **表は入念に校正する**  
    - データの正確性、フォーマット、揃え方をチェックし、誤りがないか確認します。

これらのポイントを守れば、機能的で美しく、プロフェッショナルな表を作成できます。

## 12. 結論

我々は LaTeX の表構造の奥深さを追求し、同システムの柔軟性と精度を実感してきました。`tabular` 環境の基本から `multirow`、`longtable` といった高度なパッケージまで、表作成に必要なツールとテクニックを網羅しました。表は単なるデータの羅列ではなく、情報を効果的に伝えるデザイン要素です。

ベストプラクティス（意味のあるヘッダー、揃え、適切な間隔、一貫性）を実践すれば、機能的かつ視覚的に魅力ある表が実現できます。

LaTeX の表作成スキルを活かして、学術論文やレポート、プレゼンテーションの質をさらに高めてください。実験・分析・報告のすべての場面で、LaTeX が強力なパートナーとなるでしょう。
