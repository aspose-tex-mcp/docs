---
translation: true
template: /templates/_template-java.md
linktitle: ラテックスコマンド
title: 3。ラテックスコマンド|ラテックスマニュアル
weight: 30
url: /java/latex-math-commands/
keywords: ラテックス、ラテックス数学式、ラテックス数学、ラテックス数学コマンド、ラテックススクエアルート、ラテックス数学の下線、ラテックス数学オーバーライン
description: この記事では、LaTexが提供するマクロコマンドを含む数学式を作成する別の方法について説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

単純な式から複雑な式を構築する別の方法は、コマンド「\ sqrt」、 `\ underline`、または` \ overline`を使用することです。彼らはまた、それらに続くキャラクターまたはサブフォーミュラにも適用されます。

![ラテックスコマンドの最も単純なアプリケーション](/tex/images/java/tutorial/latex-math-3-1.png)

また、キューブの根などを入手することもできます。

![任意の程度のルーツ](/tex/images/java/tutorial/latex-math-3-2.png)

これら 3 つのコマンドは、任意のサイズと形状の部分式の上または下に線を配置します。小節線は、部分式を覆うのに十分な長さ、および部分式と重ならない程度の高さまたは低さになるように、サイズと位置が変更されます。特に、平方根記号は、`\sqrt` されるものの高さと深さに応じてさまざまな位置に表示されます。 ![任意のルーツ](/tex/images/java/tutorial/latex-math-3-3.png) このような場合、次のようにすべての平方根を均一にタイプセットするとよいかもしれません。 ![任意のルーツ](/tex/images/java/tutorial/latex-math-3-4.png) これを簡単に行うには、コマンド `\mathstrut` を使用します。

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

A `\mathstrut` is an invisible zero-width box. Its height and depth are the height and depth of a parenthesis '('. It follows that subformulas that contain `\mathstrut` will always have the same height and depth, unless they involve more complicated constructions like subscripts and superscripts. 