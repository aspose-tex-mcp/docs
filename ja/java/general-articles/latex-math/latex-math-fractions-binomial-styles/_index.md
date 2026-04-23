---
translation: true
template: /templates/_template-java.md
linktitle: 分数、二項係数、そして数式スタイル
title: 5. 分数、二項係数、そして数式スタイル
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: latex、latex 数式、latex 数式、latex 数式、latex 数式分数、latex 数式二項係数、latex 数式スタイル
description: 分数、二項係数などの数式構造の組版と、TeX が数式を組版する際に使用する数式スタイルについて学びます。
lastmod: "2026-04-21"
---

{{<section overview>}}

数式でよく見られるもう一つの要素は、分子が分母の上に配置されるような分数やその他の構造です。その一例が二項係数です。

![分数のような数式オブジェクト](/tex/images/java/tutorial/latex-math-5-1.png)

以下の 3 つの式は、`$1\over2$`、`$n+1\over3$`、`$\n+1\choose3$` と入力することで、ディスプレイ数式として得られます。

`\over` コマンドは、ブレースで囲んだ特定のサブ数式を除き、数式全体に適用されます。

![分数](/tex/images/java/tutorial/latex-math-5-2.png)

同じサブ数式内で `\over` を二回使うことはできません。たとえば `a\over b\over 2` のように書くことはできません。代わりに、何が何の上に来るかを明示的に指定する必要があります。

![入れ子の分数](/tex/images/java/tutorial/latex-math-5-3.png)

両方の式とも見た目があまり良くありません。このような場合、分数を「斜線形式」に変換するのが一般的です。たとえば、最後の二つの式は次のように入力すべきです。

![斜線形式の分数](/tex/images/java/tutorial/latex-math-5-4.png)

さらに複雑な例を示します。

![斜線形式の分数](/tex/images/java/tutorial/latex-math-5-5.png)

上の例を見てわかるように、文字や記号は分数中に現れるとき、添字や上付き文字のときと同様に小さくなります。ここからは、TeX が記号のサイズをどのように決めるかを説明します。TeX には数式を扱うための 8 種類のスタイルがあります。

* display style（式が単独で行に表示されるとき）
* text style（本文中に埋め込まれる式）
* script style（上付き・下付き文字として使われるサブ式）
* scriptscript style（二重上付き・下付き文字）

さらに、上付き・下付き文字の高さがそれほど上がらない「cramped」スタイルが 4 種類あります。これら 8 種類のスタイルを *D*, *D'*, *T*, *T'*, *S*, *S'*, *SS*, *SS'* と表記し、*D* が display style、*D'* が cramped display style、*T* が text style です。TeX はまた、本文サイズ、スクリプトサイズ、スクリプトスクリプトサイズの 3 種類のフォントサイズを使って数式を組版します。

Running text の中で式を組むには、式全体を `$...` で囲みます（この後に続く説明を参照）。あるいは `$...$` と囲んでディスプレイ数式にすれば、式は *D* スタイルで表示されます。式のサブ式はそれぞれ異なるスタイルになることがあります。スタイルが分かれば、TeX が使用するフォントサイズを決定できます。

![スタイルとサイズの対応](/tex/images/java/tutorial/latex-math-5-6.png)

*SSS* スタイルは存在しません。あまりにも小さくなるため、スクリプトスクリプトスタイルよりも可読性が低くなります。

![式のスタイルに応じた添字と上付き文字のサイズ](/tex/images/java/tutorial/latex-math-5-7.png)

たとえば `x^{a_b}` を *D* スタイルで組むと、`a_b` は *S* スタイル、`b` は *SS* スタイルで設定され、結果は次のようになります。  
![任意次数の根](/tex/images/java/tutorial/latex-math-5-8.png)

まだ *D* と *T* の違いは見えていませんが、指数の位置に若干の差があります（どちらもスクリプトサイズが使用されます）。しかし分数に関しては *D* と *T* の違いは大きくなります。

![分母と分子のスタイルの違い](/tex/images/java/tutorial/latex-math-5-9.png)

したがってテキスト中で `$1\over2` と入力するとスタイルは *S* の上に *S'* が置かれますが、ディスプレイ数式で `$1\over2$` と入力するとスタイルは *T* の上に *T'* が置かれます。

最後に、`\underline` はスタイルを変更しません。数式アクセントや `\sqrt`、`\overline` は、非クランプドスタイルをクランプドスタイルに変換しますが、クランプドスタイルはそのまま保持されます。

TeX が自動的に選択したスタイルが好みでない場合は、`\displaystyle`、`\textstyle`、`\scriptstyle`、`\scriptscriptstyle` のいずれかを入力してスタイルを明示的に指定できます。指定したスタイルは式またはサブ式の終端まで、または別のスタイルを指定するまで有効です。例として `$n+\scriptstyle n+\scriptscriptstyle n.$` を入力すると、次のように表示されます。

![手動によるスタイル制御](/tex/images/java/tutorial/latex-math-5-10.png)

この図は、スタイルが変わるとプラス記号も小さくなり、スクリプトスタイルでは `+` の前後にスペースが入らないことを示しています。

続いて、連分数の例を見てみましょう。

![連分数](/tex/images/java/tutorial/latex-math-5-11.png)

次のように入力すると得られます。

```tex
$a_0+{1\over\displaystyle a_1+
        {\strut 1\over\displaystyle a_2+
          {\strut 1\over\displaystyle a_3+
            {\strut 1\over a_4}}}}$
```

この式から `\strut` と `\displaystyle` を除くと、結果は別のものになります。

![装飾トリックなしの連分数](/tex/images/java/tutorial/latex-math-5-12.png)

LaTeX には `\frac` というマクロが定義されており、別の構文で分数を指定できます。`\frac{a}{b}` は `a\over b` と同等で、`\frac12` は `1\over2` と同等です。

`\atop` という別の操作も TeX にはあり、`\over` と似ていますが、分数線を描きません。

![\atop コマンド](/tex/images/java/tutorial/latex-math-5-13.png)

LaTeX 形式では `\choose` も定義されており、`\atop` と同様ですが結果を丸括弧で囲みます。

![\choose マクロ](/tex/images/java/tutorial/latex-math-5-14.png)

`\choose` という名称は、二項係数の一般的な表記で、*n* 個から *k* 個を選ぶ組み合わせの数を示すために使われます。

`\over`、`\atop`、`\choose` のコマンドは互いに混在させることはできません。たとえば `$n\choose k\over 2$` は不正です。`${n\choose k}\over2$` または `$n\choose{k\over2}$` のようにグルーピングして使用してください。

TeX には `\above` コマンドもあり、`\over` と `\atop` の一般化バージョンです。このコマンドでは `\above<dimen>` と入力して線の太さを正確に指定します。例として

```tex
$\displaystyle{\frac{a}{b}\above1pt\displaystyle{\frac{c}{d}}$
```

と書くと、分子と分母の間に 1pt の太さの線を持つ複合分数が生成されます。

![\above マクロ](/tex/images/java/tutorial/latex-math-5-15.png)
