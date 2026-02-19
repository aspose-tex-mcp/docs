---
translation: true
template: /templates/_template-java.md
linktitle: Extensible and adjustable symbols
title: 5. 拡張可能で調整可能な記号
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, latex math operators, latex math delimiters, latex math brackets, latex math braces, latex math accents
description: この記事では、拡張可能で調整可能な数式記号を扱うための LaTeX の機能について解説します。
lastmod: "2026-02-19"
---

{{<section overview>}}

LaTeX には、任意のサイズに伸縮できる構造を生成する機能がいくつかあります。数式組版ではこのような可変性が非常に重要です。本記事ではそれらの側面をいくつか取り上げます。このセクションで取り上げるすべてのコマンド（特に別記がない限り）は標準 LaTeX が提供するものです。

## 5.1. 省略記号...

`amsmath` パッケージは（ほぼすべての場合で）標準 LaTeX の `\ldots`、`cdots` などを単一の `\dots` コマンドに置き換えます。省略記号の縦位置とその周囲の空白は、` \dots` の後に続く記号の種類に応じて自動的に選択されます。たとえば次の記号がプラス記号であればドットは中心に配置され、コンマであればベースライン上に配置されます。ドットは常に３つですが、間隔は可変です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Ellipsis with automatically determined spacing](/tex/images/java/tutorial/latex-ams-math-5-1.png)

ただし、ドットが式の末尾に現れる場合、次に来るオブジェクトは `\end` や `\)`、あるいはユーザーのリクエストに含まれるように `\)` などで、LaTeX はドットの位置について手がかりを持ちません。そのようなケースでは、コンマの後に続くドットには `\dotsc`、*二項演算子* または *関係記号* の後には `\dotsb`、乗算記号の後には `\dotsm`、積分記号の後には `\dotsi`、それ以外のケースには `\dotso` を使用して明示的に指定する必要があります。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Ellipsis at the end of a formula](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. 水平に拡張可能な記号

基本的に LaTeX は、利用可能なフォントが提供する幅の範囲に応じて適切な字形を生成する任意の数式アクセントコマンドを設定できます。ただし、標準 LaTeX では `\widehat` と `\widetilde` の 2 つだけが利用可能です。

次の例では、前述の拡張アクセントに類似した構成を生成するいくつかのコマンドの使用例を示します。これらはすべて数式クラス *Ordinary* の複合記号を生成します。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Extensible accents](/tex/images/java/tutorial/latex-ams-math-5-3.png)

ここで「スタイルを変更しない」とは、シンボルが使用中の数式スタイルの影響を受け、たとえば分数や上下付き文字で正しく表示されることを意味します。スタイルを変更しないものは、表示数式の最上位レベルでのみ正しく表示されます。

## 5.3. 垂直に拡張可能な記号

垂直方向の拡張性ははるかに広範です。以下の表は、垂直に拡張可能なすべての記号を一覧にしたものです。

*Vertically extensible symbols*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Parentheses"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Curly Braces Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Double Vertical Bars"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Angle Brackets"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Curly Braces Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Single Vertical Bars"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup and Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Square Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Moustaches"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Square Brackets Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Ceiling Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Arrow Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Up Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Floor Brackets Close"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Brace Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Up Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Double Brackets Open"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Double Arrow Vertical Bar"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Single Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Slash"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Double Vertical Line"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Single Up Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Back Slash"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Double Vertical Line"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Single Up Down Arrow"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Square Root Sign"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *斜体で示された記号は `amsmath` パッケージが必要です。また、太字で記述されたものは `stmaryrd` パッケージも必要になります。ピリオド (.) は拡張可能な記号そのものではありませんが、「見えない」区切り記号として使用できます。`\sqrtsign` 記号は `\left`、`\right`、`\middle` と一緒に使用できません。*

> *同義語: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

これらの記号は特定の使用法でのみ拡張可能になります。拡張は次の構文に基づいて行われます。

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> LaTeX が eTeX プログラムを使用している場合、`\middle` と組み合わせてこれらの拡張記号を使用することもできます。

`<ext-Open>` と `<ext-Close>` には、上表にある（`\sqrtsign` を除く）任意の記号を使用できます。これらは [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf) に記載された方法で拡張可能に設定された記号でなければなりません。したがって、実際の字形が存在しない「ヌル区切り記号」としてピリオド (.) が利用されることがあります。拡張記号の実際の字形サイズは、間に挿入されたサブフォーミュラの高さと深さに合わせて選択されます。

ラジカル記号 `\sqrtsign` は、引数のサイズに合わせて垂直方向と水平方向の両方に伸びます。LaTeX では通常 `\sqrt` コマンドを使用してこの記号を得ます。

```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Extending radicals](/tex/images/java/tutorial/latex-ams-math-5-24.png)
