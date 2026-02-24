---
translation: true
template: /templates/_template-java.md
linktitle: 簡単な数式
title: 1. 簡単な数式
weight: 10
url: /java/latex-math-simple-formulas/
keywords: LaTeX、LaTeX 数式、LaTeX 数式、LaTeX 数式文字、LaTeX ギリシャ文字、LaTeX 数値
description: この記事では、TeX と LaTeX を使用して、より複雑な数式をシンプルなアトミック数式で表す方法について説明します。
lastmod: "2026-02-24"
---

{{<section overview>}}

最も簡単な数式は、単一の文字 `*x*` または単一の数字 `4` です。このような数式を LaTeX テキストに挿入するには、`$x` または `$4` と入力します。

すべての数式は特殊な数式括弧（``）で囲みます。

`\$x` と入力すると `*x*` がイタリック体で表示され、`\$2` と入力するとローマン体の `2` が表示されます。

一般に、キーボード上のすべての文字は数式内で特別な解釈を持ち、数学印刷の通常の慣例に従います。文字はイタリック体の文字を示し、数字や句読点はローマン体の数字や句読点を示します。ハイフン（-）はマイナス記号を表します。左側の ```` は TeX を「数式モード」へ入り、右側の ```` はそれを抜けます。したがって、どちらかを忘れると TeX が混乱し、エラーメッセージが出ることがあります。

TeX は数式内のスペースの大部分を自動で調整します。同時に、` `（スペース）を数式内に入れても無視されます。

`$(x + y)/(x - y)` または `$(x+y) / (x-y)` と入力できますが、どちらも次のような式を生成します。  
![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-1.png)  
この式では `+` と `-` の周囲に余分なスペースが入り、`/` の周囲にはスペースが入りません。したがって、複雑な数式間隔の規則を覚える必要はなく、好きなようにスペースを入れることができます。制御シーケンス（コマンド）の終了を示す必要があるときは、通常どおりスペースが使われます。ほとんどの場合、TeX の間隔は数学者の期待に合致しますが、間隔規則を上書きしたい場合は後述する制御シーケンスで行うことができます。

数式でよく見られる要素のひとつにギリシャ文字があります。LaTeX では `$\alpha, \beta, \gamma, \delta` と入力すると最初の 4 つのギリシャ文字が得られます。さらに `$\Gamma` と入力すると大文字のガンマが得られます。

たとえば、`\kappa` と `\nu` はイタリック体の文字 *v* と *x* と混同しないでください。ギリシャ文字 `\phi` は斜線付きのゼロ `\emptyset` とは異なります。小文字の `\epsilon` は集合の所属記号とは異なります。いくつかの小文字ギリシャ文字には LaTeX のイタリックフォントで別形が用意されています：`\phi, \theta, \epsilon, \rho` …  
![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-2.png)  
`\varphi, \vartheta, \varepsilon, \varrho` …  
![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-3.png)

ギリシャ文字以外にも、"approximately equal"（`\approx`）や "maps to"（`\mapsto`）といった多くの数学記号があります。これらの制御シーケンスと対応する記号の完全なリストは、[here](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/) にあります。
