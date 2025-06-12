---
translation: true
template: /templates/_template-java.md
linktitle: マトリックスおよび同様の環境
title: 3。マトリックスと同様の環境|ラテックスマニュアル
weight: 30
url: /java/latex-ams-matrix/
keywords: AMS-Latex、AMSMATH、AMSCD、ラテックスマトリックス、ラテックスケース、ラテックスデラレイ、ラテックス通勤図
description: この記事では、AMS-Latexパッケージを使用したタイプセットラテックスマトリックスのような構造の簡単な紹介を提供します。
lastmod: "2025-06-09"
---

{{<section overview>}}

`Amsmath`パッケージで定義されているタイプセットマトリックスのような構造のための多くの環境があります。これらはすべて、構文とレイアウトの標準のラテックス「アレイ」環境に似ています。一般に、多種多様な2次元数学構造と表形式のレイアウトは、アレイとして説明できます。

3つの環境 - 「ケース」、「マトリックス」、`pmatrix` - 標準のラテックスのコマンドを置き換えます。標準コマンドは別の表記を使用するため、ここで説明する環境フォームと一緒に使用することはできません。 `amsmath`パッケージは、古いコマンドのいずれかが使用されている場合、エラーメッセージを作成します。逆に、パッケージをロードせずに`amsmath`環境フォームを使用しようとすると、次のエラーメッセージが表示されます。


## 3.1。 「ケース」環境

「ケース」環境は、単一の方程式にいくつかのバリアントがある構造を処理するために使用されます。このような構造は数学では非常に一般的です。どちらも左アライメントされた2つの列のある配列を生成します。


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

![ケース環境](/tex/images/java/tutorial/latex-ams-math-3-1.png)

テキスト文字列に「\ text」コマンドと「埋め込まれた数学モード」の使用に注意してください。

## 3.2。マトリックス環境

行列環境は、LaTeXの`array`とは異なり、列のフォーマットを指定する引数を受け付けません。代わりに、中央揃えの10列までのデフォルトフォーマットが提供されます。また、間隔も`array`のデフォルトとは若干異なります。以下の例は、`matrix`、`pmatrix`、`bmatrix`、`Bmatrix`、`vmatrix`、`Vmatrix`環境を示しています。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![マトリックス環境](/tex/images/java/tutorial/latex-ams-math-3-2.png)

`maxmatrixcols`カウンターは、マトリックス環境の列の最大数を決定します。 LaTexの標準カウンターコマンドを使用して変更できます。 `\ arraycolsep`の長さパラメーターの値は、列間の空間の量を決定します。標準配列のように同じですが、配列の両側にスペースが追加されていません。より多くの列により、ラテックスがより激しく働き、より多くのリソースが必要になります。ただし、今日の典型的なTexの実装では、このような制限がそれほど重要ではないため、「MaxmatrixCols」を顕著なパフォーマンスヒットなしでは20以上に設定することは可能です。


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

![マトリックス環境のその他の列](/tex/images/java/tutorial/latex-ams-math-3-3.png)

この例では、 `\ hdotsfor`コマンドを使用して、特定の数の列にまたがるマトリックス内のドットの列を生成します。オプションのパラメーター(ここでは2)を使用して、ドット間のデフォルトスペース(3 Mathユニット)の乗数を指定できます。薄いスペースとブレースグループ「\、{}」は、各行の最後に、レイアウトの見た目をより良くするだけです。一緒になって、約6muまたは1/3emの2つの薄いスペースを生成します。

テキストで使用するための小さなインラインマトリックスを作成するには、「SmallMatrix」環境を使用できます。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![SmallMatrix環境](/tex/images/java/tutorial/latex-ams-math-3-4.png)

小さなマトリックスの前のラインには、ディスンダー付きの文字が含まれているにもかかわらず、テキストラインは離れていないことに注意してください。

## 3.3。サブスクリプトと上付き文字の積み重ね

下付き文字または上付き文字の中に複数行を記述する必要がある場合があります。この場合、`\substack` コマンドを使用し、`\\` で行を区切ります。

「Subarray」環境は、中心にするのではなく、線を左または右に並べることができるわずかに一般的な構造です。


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

![サブおよび上着の積み重ね](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> 両方の環境が下付き文字または上付き文字として表示される場合は、中括弧で囲む必要があることに注意してください。

## 3.4。通勤図

`amscd`パッケージは、配列に基づいて単純な通勤図を作成するためのいくつかのコマンドを定義します。装飾された矢印やその他のコネクタを指定するための有用な速記形式がいくつかあります。ただし、制限があります。たとえば、これらのコネクタは水平または垂直にのみである場合があります。

`CD` 環境では、`@>>>`、`@<<<`、`@VVV`、`@AAA` という表記はそれぞれ右矢印、左矢印、下矢印、上矢印を生成します。次の例は、`\DeclareMathOperator` コマンドの使用法も示しています。


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

![単純な通勤図](/tex/images/java/tutorial/latex-ams-math-3-6.png)

装飾の指定方法を見てみましょう。水平矢印の場合、1つ目と2つ目の間の「>」または「<」記号は上付き文字として、2つ目と3つ目の間の「A」または「V」記号は下付き文字として設定されます。同様に、垂直矢印の場合、1つ目と2つ目、または2つ目と3つ目の間の「A」または「V」記号は、左付き文字または右付き文字として設定されます。この形式の使用方法については、次の例で説明します。

表記「@= `および`@|」は、水平および垂直の二重線を与えます。

目に見える矢印の代わりに、「null矢印」(@.`)を使用して、必要に応じて配列に記入できます。


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

![スクリプトを使用した通勤図](/tex/images/java/tutorial/latex-ams-math-3-7.png)

同様のレイアウトを標準のラテックスで生成できます。しかし、それはそれほど良く見えません。


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![標準のラテックスの通勤図](/tex/images/java/tutorial/latex-ams-math-3-8.png)

この例は、`amscd`パッケージが生成する結果を非常に明確に示しています。表記はより簡単で、水平矢印が長く、要素間の間隔が大幅に改善されます。より専門的なパッケージは、さらに美しい結果を達成するのに役立ちます。

## 3.5。配列を取り巻く区切り文字：「Delarray」パッケージ

このセクションでは、「配列」パッケージの有用な一般的な拡張について説明します。この拡張機能を使用して、ユーザーは数学の「配列」環境を囲むために、拡張可能なデリミタを開閉と閉じることを指定できます。例を見てみましょう：


```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![デラレイパッケージの使用](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> `delarray` パッケージは `amsmath` から独立していますが、必要に応じて `array` パッケージを自動的にロードすることに注意してください。

区切り文字は、 `{cc}`の両側に配置されます。

この例は、`delarray` パッケージの最も便利な機能である、`[t]` および `[b]` オプション引数の使用も示しています。これらは `amsmath` の行列環境では許可されていません。これは、`delarray` 構文の使用は、`array` 環境を `\left` および `\right` で囲むことと同じではないことを示しています。なぜなら、配列自体だけでなく区切り文字も展開されるからです。