---
translation: true
template: /templates/_template-java.md
linktitle: 1。単純な式
title: 単純な式|ラテックスマニュアル
weight: 10
url: /java/latex-math-simple-formulas/
keywords: ラテックス、ラテックス数学式、ラテックス数学、ラテックス数学文字、ラテックスギリシャ文字、ラテックス番号
description: この記事では、TexとLaTexを使用したより複雑な式のための単純な原子数学式を作成する方法について説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

最も単純な式は、単一の文字「*x*」または単一の数字「4」です。このような式をラテックステキストに挿入するには、それぞれ `$ x $`または `$ 4 $`を入力します。すべての数式は、特別な数学ブラケット( `$`)に囲まれています。

`$ x $` the '*x*'を入力すると、イタリック体で登場しますが、 `$ 2 $`は '2を生成します。一般に、キーボード上のすべての文字は、数学印刷の通常の慣習に従って、数学の式で特別な解釈を持っています。文字は斜体の文字を示しますが、数字と句読点はローマの数字と句読点を示します。ハイフン( - )はマイナス記号を示します。左 `$`はテックスを「数学モード」に入れ、右のものを取り出します。したがって、1つの `$`を忘れたり、余分な `$`を入力したりすると、Texが混乱するため、おそらくエラーメッセージが表示されます。

TeX does most of its own spacing in math formulas. At the same time, it ignores any spaces that you put between `$`'s. You can type `$(x + y)/(x - y)$` or `$(x+y) / (x-y)$`, but both will result in a formula ![シングルキャラクターのサブスクリプトと上付き文字](/tex/images/java/tutorial/latex-math-1-1.png) in which there is a bit extra space surrounding the '+' and '-' signs but none around the '/' sign. So, you don't have to remember the complicated rule of math spacing, and you're free to use spaces in any way you like. When it is necessary to mark the end of control sequences (commands), spaces are still used in the normal way. In most cases TeX's spacing will meet a mathematician's expectations; but if you want to override TeX's spacing rules, you can do so with control sequences, which we will discuss later.

One of the common things you may find in math formulas is the use of Greek letters. In LaTeX you can type `$\alpha, \beta, \gamma, \delta$` to get the first four Greek letters. And `$\Gamma$`, for example, produces a capital gamma letter. Don't confuse the Greek letters `\kappa` and `\nu` with the italic letters *v* and *x*; the Greek `\phi` is different from the slashed zero called `\emptyset`. A lowercase `\epsilon` is different from the symbol denoting membership in a set. Some of lowercase Greek letters have variant forms in LaTeX italic fonts: `$\phi, \theta, \epsilon, \rho$` yields ![シングルキャラクターのサブスクリプトと上付き文字](/tex/images/java/tutorial/latex-math-1-2.png) while `$\varphi, \vartheta, \varepsilon, \varrho$` yields ![シングルキャラクターのサブスクリプトと上付き文字](/tex/images/java/tutorial/latex-math-1-3.png)

ギリシャの手紙に加えて、「ほぼ等しい」( `$ \ emar $ $`)や「maps」( `$ \ mapsto $`)などの数学のシンボルがたくさんあります。これらの制御シーケンスの完全なリストとそれらの対応するシンボル[ここ](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/)を見つけることができます。