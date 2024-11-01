---
translation: true
template: /templates/_template-java.md
linktitle: 3. LaTeX commands
title: LaTeX commands | LaTeX manual | Aspose.TeX for Java
weight: 30
url: /java/latex-math-commands/
keywords: latex, latex math formulas, latex math, latex math commands, latex square root, latex math underline, latex math overline
description: This article discusses another way to compose math formulas that involves macro commands provided by LaTeX.
lastmod: "2024-09-20"
---

{{<section overview>}}

Another way to build complex formulas from simple ones is to use the commands `\sqrt`, `\underline`, or `\overline`. They also apply to the character or subformula that follows them:

![Simplest application of LaTeX commands](/tex/images/java/tutorial/latex-math-3-1.png)

You can also get cube roots and similar things:

![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-2.png)

These three commands place lines above and below subformulas of any size and shape; the bar lines change their size and position, so that they are long enough to cover the subformula, and high enough or low enough not to overlap with it. In particular, square root signs appear in a variety of positions depending on the height and depth of what's being `\sqrt`'ed: ![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-3.png) In such a case, you may want to typeset all square roots uniformly, like this: ![Roots of arbitrary degree](/tex/images/java/tutorial/latex-math-3-4.png) The easy way to do this is to use the command `\mathstrut`:

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

A `\mathstrut` is an invisible zero-width box. Its height and depth are the height and depth of a parenthesis '('. It follows that subformulas that contain `\mathstrut` will always have the same height and depth, unless they involve more complicated constructions like subscripts and superscripts. 
