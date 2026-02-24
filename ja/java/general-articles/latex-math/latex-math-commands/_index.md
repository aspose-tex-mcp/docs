---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX コマンド
title: 3. LaTeX コマンド | LaTeX マニュアル
weight: 30
url: /java/latex-math-commands/
keywords: latex、latex 数式、latex 数式、latex 数式コマンド、latex 平方根、latex 数式下線、latex 数式上線
description: この記事では、LaTeX が提供するマクロコマンドを使用して数式を作成する別の方法について説明します。
lastmod: "2026-02-24"
---

{{<section overview>}}

単純な数式から複雑な数式を構築する別の方法は、コマンド `\sqrt`、`\underline`、`\overline` を使用することです。これらは後に続く文字や部分式にも適用されます。

![LaTeX コマンドの最も簡単な適用例](/tex/images/java/tutorial/latex-math-3-1.png)
![Simplest application of LaTeX commands](/tex/images/java/tutorial/latex-math-3-1.png)

立方根や同様のものも取得できます。

![任意次数の根](/tex/images/java/tutorial/latex-math-3-2.png)
![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-2.png)

これら3つのコマンドは、サイズや形状に関係なく部分式の上部や下部に線を付けます。バーの長さと位置は自動的に調整され、部分式を十分に覆うように長くなり、重ならないように上下に配置されます。特に、平方根記号は `\sqrt` される対象の高さと深さに応じてさまざまな位置に表示されます: ![任意次数の根](/tex/images/java/tutorial/latex-math-3-3.png) そのような場合、すべての平方根を統一した形で組版したくなることがあります。例えば次のようにします: ![任意次数の根](/tex/images/java/tutorial/latex-math-3-4.png) これを簡単に実現する方法は、コマンド `\mathstrut` を使用することです:
これら3つのコマンドは、サイズや形状に関係なく部分式の上部や下部に線を付けます。バーの長さと位置は自動的に調整され、部分式を十分に覆うように長くなり、重ならないように上下に配置されます。特に、平方根記号は `\sqrt` される対象の高さと深さに応じてさまざまな位置に表示されます: ![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-3.png) そのような場合、すべての平方根を統一した形で組版したくなることがあります。例えば次のようにします: ![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-4.png) これを簡単に実現する方法は、コマンド `\mathstrut` を使用することです:

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.


`\mathstrut` は目に見えない幅0のボックスです。その高さと深さは左括弧 '(' の高さと深さと同じです。したがって、`\mathstrut` を含む部分式は、添字や上付き文字のようなより複雑な構造を含まない限り、常に同じ高さと深さを持ちます。
