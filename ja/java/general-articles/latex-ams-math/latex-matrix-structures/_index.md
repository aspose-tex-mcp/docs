---
translation: true
template: /templates/_template-java.md
linktitle: 行列および類似環境
title: 3. 行列および類似環境
weight: 30
url: /java/latex-ams-matrix/
keywords: ams-latex、amsmath、amscd、latex 行列、latex ケース、latex delarray、latex 可換図
description: この記事では、AMS‑LATEX パッケージを使用した LaTeX の行列類似構造の組版について簡単に紹介します。
lastmod: "2026-02-19"
---

{{<section overview>}}

`amsmath` パッケージで定義されている、行列のような構造を組版するための環境がいくつかあります。これらはすべて、標準的な LaTeX の `array` 環境と構文・レイアウトが似ています。一般に、二次元の数学構造や表形式レイアウトはすべて配列として記述できます。

`cases`、`matrix`、`pmatrix` の 3 つの環境は、標準 LaTeX のコマンドの代わりに使用します。標準コマンドは別の表記法を用いるため、ここで紹介する環境形態と一緒に使用することはできません。`amsmath` パッケージは、古いコマンドが使用された場合にエラーメッセージを出します。逆に、パッケージを読み込まずに `amsmath` の環境形態を使用しようとすると、次のようなエラーメッセージが表示されることが most likely です: `"Misplaced alignment tab character &"`。

## 3.1. `cases` 環境

`cases` 環境は、1 つの式にいくつかのバリエーションがあるような構成を処理するために使用します。このような構成は数学で非常に一般的です。2 列の配列を生成し、両列とも左寄せになります。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Cases environment](/tex/images/java/tutorial/latex-ams-math-3-1.png)

`\text` コマンドと、テキスト文字列中の「埋め込み数式モード」の使用に注意してください。

## 3.2. matrix 環境

`array` とは異なり、matrix 系の環境は列の書式を指定する引数を受け取りません。その代わり、デフォルトで最大 10 列のセンタリングされた書式を提供します。間隔も `array` のデフォルトと微妙に異なります。以下の例は `matrix`、`pmatrix`、`bmatrix`、`Bmatrix`、`vmatrix`、`Vmatrix` 環境を示しています。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Matrix environments](/tex/images/java/tutorial/latex-ams-math-3-2.png)

`MaxMatrixCols` カウンタは、matrix 環境で許容される最大列数を決定します。LaTeX の標準カウンタコマンドで変更できます。`\arraycolsep` の長さパラメータは列間のスペース量を決めます。標準配列と同様ですが、配列の両端に余分なスペースは追加されません。列が増えると LaTeX の処理負荷が上がり、リソースも多く必要になります。ただし、`MaxMatrixCols` を 20 以上に設定しても、今日の典型的な TeX 実装では目立った性能低下はありません。

```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![More columns in matrix environments](/tex/images/java/tutorial/latex-ams-math-3-3.png)

この例では `\hdotsfor` コマンドを用いて、指定した列数だけドット列を生成しています。オプション引数 (ここでは 2) は、デフォルトのスペース (3 math units) を何倍にするかを指定できます。行末の `\,{}` は細いスペースと波括弧の組で、レイアウトを見栄え良くするために 2 つの細いスペース (約 6mu または 1/3em) を挿入します。

テキスト中に小さなインライン行列を組む場合は、`smallmatrix` 環境を使用できます。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![The smallmatrix environment](/tex/images/java/tutorial/latex-ams-math-3-4.png)

小行列がある行では、文字のディセンダが含まれていても行間は広がらないことに注意してください。

## 3.3. 添字・上付き文字の中でのスタック

添字や上付き文字の中で複数行を組版したい場合があります。そのときは `\\` で行を区切った `\substack` コマンドを使用できます。

`subarray` 環境は、行を左寄せまたは右寄せに揃えることができる、やや汎用的な構造です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Stacking in sub- and superscripts](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> 注: これらの環境は、添字または上付き文字として使用する際には必ず波括弧 `{}` で囲む必要があります。

## 3.4. 可換図式

`amscd` パッケージは、配列を基にしたシンプルな可換図式を生成するためのコマンドを定義します。装飾付き矢印やその他のコネクタを指定する便利な省略形がありますが、水平または垂直の矢印しか描けないという制限があります。

`CD` 環境では、`@>>>`、`@<<<`、`@VVV`、`@AAA` がそれぞれ右、左、下、上矢印を生成します。以下の例は `\DeclareMathOperator` コマンドの使用例も示しています。

```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\ 
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Simple commutative diagram](/tex/images/java/tutorial/latex-ams-math-3-6.png)

装飾の指定方法を見てみましょう。水平矢印では、最初と二番目の `>`（または `<`）の間の文字列が上付き、二番目と三番目の間が下付きとして組版されます。垂直矢印の場合は、最初と二番目、または二番目と三番目の `A`（`V`）の間の文字列がそれぞれ左側・右側の「サイドスクリプト」として扱われます。この書式は次の例でも使用します。

`@=` と `@|` はそれぞれ水平・垂直の二重線を生成します。

見た目の矢印の代わりに「ヌル矢印」(`@.`) を使って、必要な場所に配列の枠だけを埋めることもできます。

```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]

```

![Commutative diagram with scripts](/tex/images/java/tutorial/latex-ams-math-3-7.png)

同様のレイアウトは標準 LaTeX でも作れますが、見た目はあまり良くありません。

```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Commutative diagram in standard LaTeX](/tex/images/java/tutorial/latex-ams-math-3-8.png)

この例は、`amscd` パッケージがどれだけ優れた結果を出すかを明確に示しています。記法が簡潔で、水平矢印が長く、要素間の間隔も大幅に改善されています。より専門的なパッケージを使用すれば、さらに美しい結果が得られます。

## 3.5. 配列を囲む区切り記号：`delarray` パッケージ

このセクションでは、`array` パッケージへの有用な汎用拡張である `delarray` パッケージを紹介します。この拡張を使うと、数学の `array` 環境を囲む開閉可能な区切り記号を指定できます。例を見てみましょう。

```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![The use of the delarray package](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> 注: `delarray` パッケージは `amsmath` とは独立していますが、必要に応じて自動的に `array` パッケージをロードします。

区切り記号は `{cc}` の両側に配置されます。

この例は `delarray` パッケージの最も便利な機能を示しています。`[t]` と `[b]` のオプション引数は `amsmath` の matrix 環境では使用できません。これにより、`delarray` の構文は `\left` と `\right` で `array` 環境を囲むだけとは異なり、区切り記号自体が上がったり、配列全体と同様に扱われます。
