---
translation: true
template: /templates/_template-java.md
linktitle: 拡張可能な調整可能なシンボル
title: 5。拡張可能な調整可能なシンボル|ラテックスマニュアル
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: AMS-Latex、AMSMATH、AMSXTRA、ラテックス数学オペレーター、ラテックス数学デリミター、ラテックス数学ブラケット、ラテックス数学ブレース、ラテックス数学アクセント
description: この記事では、拡張可能で調整可能な数学シンボルを使用することに関連するLaTex機能について説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

ラテックスでは、必要なサイズに成長できる構造を生成できる特定の機能があります。数学的なタイプセットは、このような変動性を非常に必要としています。この記事では、いくつかの側面について説明します。このセクションでカバーされているすべてのコマンド(特に明記しない限り)は、標準のラテックスによって提供されます。


## 5.1。 Ellipsis ...

`amsmath`パッケージは(ほぼすべての場合)すべての`\ ldots`、`cdot`など、単一の`\ dots`コマンドを標準のラテックスから置き換えます。楕円の垂直位置とその周りの空間の両方は、`\ dots`に続くシンボルのタイプに応じて自動的に選択されます。次のシンボルがプラス記号である場合、ドットが中心に出てきます。それがコンマの場合、彼らはベースラインに落ちます。常に3つのドットですが、間隔は可変です。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![自動的に決定された間隔を持つ楕円](/tex/images/java/tutorial/latex-ams-math-5-1.png)

ただし、フォーミュラの最後にドットが表示されると、次のオブジェクトは`\end`または `\)`または `$`のようなものになり、ドットの位置付けについてLaTexに手がかりを与えません。そのような場合、ドットには`\dotsc`を使用してコンマ、ドットの`\dotsb`を使用することで支援する必要があります。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![フォーミュラの終わりにある楕円](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2。水平に拡張可能なシンボル

基本的に、LATEXを使用すると、数学アクセントコマンドをセットアップして、利用可能なフォントによって提供されるたびに、さまざまな幅から適切なグリフを生成できます。ただし、標準のラテックスには、このようなコマンドは2つしかありません： `\ widehat`と` \ widetilde`。

次の例では、前述の拡張可能なアクセントと同様の構成要素を生成するいくつかのコマンドの使用を示します。それらはすべて、数学クラス *普通 *の複合記号を生成します。

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

![拡張可能なアクセント](/tex/images/java/tutorial/latex-ams-math-5-3.png)

ここで、「変更スタイル」とは、採用されているシンボルが使用されている数学スタイルの影響を受けることを意味するため、たとえば、分数や添え字/SuperScriptで使用すると正しく見えます。スタイルを変えないものは、表示された式の最上位レベルでのみ正しく出てきます。

## 5.3。垂直に拡張可能なシンボル

垂直の拡張性ははるかに広くなっています。次の表には、垂直に拡張可能なすべての記号を示します。

*垂直に拡張可能なシンボル*

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


> *イタリック体の記号は、`amsmath` パッケージ、または太字で追加入力する場合は `stmaryrd` パッケージが必要です。ピリオド (.) 自体は拡張可能な記号ではありませんが、「目に見えない」区切り文字を生成するために使用できます。`\sqrtsign` 記号は `\left`、`\right`、`\middle` と一緒に使用することはできません。*

> *Synonyms: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

これらの記号は、特定の使用法でのみ拡張可能になります。彼らは次の構造に基づいている必要があります：

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> LaTeX が eTeX プログラムを使用している場合は、`\middle` を使用してこれらの拡張シンボルを使用することもできます。

ここでは、上記の表に記載されている記号(`\sqrtsign`を除く)のいずれかになることができます。 [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf)で説明されているように、拡張可能になるように設定されたシンボルでなければなりません。したがって、実際のグリフの欠如を表すシンボルが利用可能でなければなりません。 *null delimiter *としても知られているこのシンボルは、期間(。)であることが起こりました。拡張可能なシンボルをタイプセットするための実際のグリフのサイズは、それらの間にあるサブフォーミュラの高さと深さに合うように選択されます。

根本的なシンボル`\sqrtsign`は、その引数のサイズに合うように垂直および水平方向に成長します。ラテックスでは、 `\ sqrt`コマンドを使用してこのシンボルを取得します。


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![拡張ラジカル](/tex/images/java/tutorial/latex-ams-math-5-24.png)