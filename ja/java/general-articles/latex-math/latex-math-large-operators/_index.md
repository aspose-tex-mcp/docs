---
translation: true
template: /templates/_template-java.md
linktitle: 大きな演算子
title: 6. LaTeX 大きな演算子
weight: 60
url: /java/latex-math-large-operators/
keywords: latex、latex 数式、latex 数式、latex 数式、latex 数式 大規模演算子、latex 和、latex 積分
description: この記事では、TeX と LaTeX を使用して総和や積分などの大きな演算子を含む数式を作成する方法について説明します。
lastmod: "2026-02-24"
---

{{<section overview>}}

数学では、例えば「総和」や「積分」操作を表す記号があります。これらは「大きな演算子」と呼ばれ、通常の記号や文字と同じように入力します。違いは、TeX がディスプレイスタイルでは大きな演算子に対してより大きなシンボルを選び、テキストスタイルでは小さなシンボルを使用する点です。

![Summation and integration without super/subscripts](/tex/images/java/tutorial/latex-math-6-1.png)

表示された `\sum` は通常「リミット」（上下に表示される下付き・上付きの式）と共に現れます。リミットは下付き文字・上付き文字として入力します。  
`\$\sum_{n=1}^m\$` または `\$\sum^m_{n=1}\$` のどちらも次のように表示されます。

![Summation with limits](/tex/images/java/tutorial/latex-math-6-2.png)

数学組版の標準的な慣例では、上の式はテキスト中に現れた場合は次のようにリミットなしに変換されると想定されています。

![Summation without limits](/tex/images/java/tutorial/latex-math-6-3.png)

（つまり、テキスト中ではリミットなし）TeX はこの慣例に従います。

積分記号上の上付き・下付き文字は、ディスプレイスタイルであってもリミットとして設定されません。

![Integration in text and in a display](/tex/images/java/tutorial/latex-math-6-4.png)

リミットとして下付き・上付き文字を設定すると、下式が複雑な場合に見栄えが良くなりますが、ページ上のスペースは多く取ります。この方法で式を強制的に処理させるには、`\int`、`\sum`、または他の演算子の直後に `\limits` と入力します（使用されるスタイルに関係なく）。一方、表示される総和記号にリミットを付けたくない場合もあります。その場合は、大きな演算子の直後に `\nolimits` と入力して TeX の慣例を変更できます。

![Forcing limits and no limits for summation and integration](/tex/images/java/tutorial/latex-math-6-5.png)

`\nolimits\limits` と入力した場合（例: `\int` などのマクロが `\nolimits` を指定している場合）、最後のコマンドが優先されます。`\displaylimits` コマンドを使用すると、TeX の標準的な慣例に切り替えることができ、リミットは *D* および *D'* スタイルでのみ表示されます。

複数行のリミットを大きな演算子の下に置く必要がある場合は、`\atop` を使用できます。次の式を正しく入力する方法は以下の通りです。

```tex
$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$.
```

![Multi-row limits under the summation sign](/tex/images/java/tutorial/latex-math-6-6.png)

ここでは `\scriptstyle` コマンドが必要です。さもなければ、リミットの両行が scriptscript サイズになり、非常に小さくなってしまいます。これは TeX のスタイル規則を上書きしなければならない稀なケースの一つです。
