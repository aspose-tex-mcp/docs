---
translation: true
template: /templates/_template-java.md
linktitle: 装飾された記号と複合構造
title: 4. 装飾記号と複合構造
weight: 40
url: /java/latex-math-decorations/
keywords: ams-latex、amsmath、amsxtra、latex 積分、latex 分数、latex 装飾、latex 矢印、latex 極限、latex モジュラー関係
description: 本記事では、amsmath パッケージを使用してさまざまな中サイズの数式構造を生成するコマンドについて説明します。
lastmod: "2026-02-19"
---

{{<section overview>}}

`amsmath` パッケージは、分数のようなオブジェクトや装飾記号などの構造を生成するコマンドを提供します。ここではそれらのいくつかを取り上げます。

## 4.1. 一般的な分数

`amsmath` パッケージは一般化分数を生成する `\genfrac` コマンドを定義しています。

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

最初の 2 つの引数はそれぞれ左側と右側の区切り記号を定義します。3 番目の引数 *thick* を使用すると、分数線のデフォルトの太さを上書きできます。たとえば、二項係数（下記参照）ではこの引数に `0pt` を指定して線を見えなくしています。デフォルト値（空の場合）は、数式組版用の現在のフォント設定に基づいて決定されます。以下の表は本記事の例で使用されているデフォルトを示しています。

| ***スタイル*** | ***デフォルトの太さ*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

4 番目の引数 *style* は（空でない場合）レイアウトとフォントサイズに使用する数式スタイルを上書きします。値は 0‑3 の範囲でなければなりません: 0 – `\displaystyle`、1 – `\textstyle`、2 – `\scriptstyle`、3 – `\scriptscriptstyle`。この引数が空の場合、スタイルは分数の通常の規則に従って選択されます。最後の 2 つの引数が分子と分母です。

> 旧来の分数コマンド `\over`、`\overwithdelims`、`\atop`、`\atopwithdelims`、`\above`、`\abovewithdelims`（標準 LaTeX が TeX から継承しているもの）は、`amsmath` パッケージと共に使用すると警告が出ます。

### 4.1.1. 単純な分数

`\genfrac` コマンドがあるので、`amsmath` パッケージは便利なショートカットとして `\frac`、`\dfrac`、`\tfrac` の 3 つのコマンドも定義しています。

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

以下の例はこれらのコマンドの使用例です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\frac, \dfrac, and \tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. 二項係数

もう一つの分数のような構造は二項係数です。これを組版するために、`amsmath` パッケージは同様のコマンド `\binom`、`\dbinom`、`\tbinom` を提供しています。

以下のように `\genfrac` コマンドを省略形として定義しています。

```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

そして例は次の通りです。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\binom, \dbinom, and \tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. 連分数

分数配列、すなわち本質的に無限分数である「連分数」を組版したい場合は、`amsmath` パッケージの `\cfrac` コマンドを使用します。オプション引数 `[l]` または `[r]` を付けると、分子を左寄せまたは右寄せにできます（デフォルトは中央揃え）。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![A continued fraction](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. ボックスで囲む数式

`amsmath` パッケージは `\fbox` と同様に数式モードの内容をボックスで囲む `\boxed` コマンドを提供します。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![A boxed formula](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. 限界（limits）の位置付け

積分、総和、積、その他の演算子に対する下付文字と上付文字は、演算子の上・下に配置（「limit 位置」）することも、演算子の右側に下付文字/上付文字として配置することもできます。通常、テキスト中では limits は使用されません（行間が広がってしまうため）。表示数式では、配置は演算子に依存します。以下の例は LaTeX のデフォルト配置を示しています。

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![The default placement of the subscripts/superscripts in LaTeX](/tex/images/java/tutorial/latex-ams-math-4-5.png)

`amsmath` パッケージは配置を制御するオプションを提供します。以下に示すのは、標準の LaTeX 文書クラスで `amsmath` パッケージを使用し、これらのオプションを付けない場合の *default* 動作です。

|||
|:---:|---|
| `intlimits`, `nointlimits` | 積分記号の上・下に上付文字・下付文字を配置（デフォルト）または側面に配置します。表示数式でのみ有効です。 |
| `sumlimits`, `nosumlimits` | 大演算子（総和、積など）の上・下に上付文字・下付文字を配置（デフォルト）または側面に配置します。表示数式でのみ有効です。 |
| `namelimits`, `nonamelimits` | `inf`、`sup`、`lim`、`min`、`max` などの「演算子名」に対して、総和や積と同様の配置を行います。 |

TeX には、記号や演算子名の直後に置くことで上付文字・下付文字の位置を制御する 3 つのプリミティブコマンドがあります：`\limits`、`\nolimits`、`\displaylimits`。`\displaylimits` は、現在の数式スタイルが display スタイルのときに limit 位置に上付文字・下付文字を配置します。これは *Operator* クラスの記号が現れるときや `\mathop` が使われたときのデフォルト動作です。display 以外で limit 位置にしたい場合は、個別に `\limits` を付与する必要があります。

以下の例は前述の例と比較したものです。

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Controlling the placement of the subscripts/superscripts with TeX primitives](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. 複数積分

テキスト・表示のいずれでも、複数の積分記号を適切な間隔で組版したいときは、`\iint`、`\iiint`、`\iiiint` コマンドを使用します。`\idotsint` は 2 つの積分記号の間に省略記号（…）を入れます。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![Multiple integrals](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. モジュラー関係

整数の同値類を表す「mod」表記は、特別な間隔規則に従います。これを扱うために、`amsmath` パッケージは `\mod`、`\bmod`、`\pmod`、`\pod` コマンドを提供しています。以下の例はそれらの使用例です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
The in-text layout: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![Modular relation](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> `amsmath` では、非表示数式中の `\pmod` の間隔が狭くなります。

## 4.5. 点アクセント

`\dot` と `\ddot` に加えて、`amsmath` パッケージは `\dddot` と `\ddddot` を提供し、3 重・4 重の点アクセントを生成できます。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![Dot accents](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. アクセントを上付きにする：`amsxtra` パッケージ

`amsxtra` パッケージは、簡単なコマンドの集合として、アクセントを下付文字の代わりに上付きで配置する便利な機能を提供します。

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![Accents as superscripts](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. その他の装飾

標準 LaTeX には、関係記号の上に上付き文字を置く `\stackrel` コマンドがあります。加えて、`amsmath` パッケージは `\overset` と `\underset` を定義しています。これらは任意の *Ordinary*、*Relation*、*Binary operator* 記号の上または下に素材を配置するために使用できます。

`\sideset` コマンドは、通常の limits に加えて任意の *Operator* 記号（総和、積など）に装飾を付加します。これらは演算子の左側と右側の下付文字・上付文字位置に配置されます。

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![More decoration](/tex/images/java/tutorial/latex-ams-math-4-11.png)
