---
translation: true
template: /templates/_template-java.md
linktitle: Simple formulas
title: 1. Simple formulas 
weight: 10
url: /java/latex-math-simple-formulas/
keywords: latex, latex math formulas, latex math, latex math letters, latex greek letters, latex numbers
description: This article discusses how to create simple atomic math expressions for more complex formulas with TeX and LaTeX.
lastmod: "2024-09-20"
---

{{<section overview>}}

The simplest formula is a single letter '*x*' or a single digit '4'. To insert such a formula into a LaTeX text, you type `$x$` or `$4$`, respectively. All math formulas are enclosed in special math brackets (`$`).

When you type `$x$` the '*x*' comes out in italics, but `$2$` produces '2' in Roman type. In general, all characters on your keyboard have a special interpretation in math formulas, according to the normal conventions of math printing. Letters denote italic letters, while digits and punctuations denote roman digits and punctuation. A hyphen (-) denotes a minus sign. The left `$` puts TeX into "math mode" and the right one takes it out. So, if you forget one `$` or type an extra `$`, you will probably get an error message because TeX will get confused.

TeX does most of its own spacing in math formulas. At the same time, it ignores any spaces that you put between `$`'s. You can type `$(x + y)/(x - y)$` or `$(x+y) / (x-y)$`, but both will result in a formula ![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-1.png) in which there is a bit extra space surrounding the '+' and '-' signs but none around the '/' sign. So, you don't have to remember the complicated rule of math spacing, and you're free to use spaces in any way you like. When it is necessary to mark the end of control sequences (commands), spaces are still used in the normal way. In most cases TeX's spacing will meet a mathematician's expectations; but if you want to override TeX's spacing rules, you can do so with control sequences, which we will discuss later.

One of the common things you may find in math formulas is the use of Greek letters. In LaTeX you can type `$\alpha, \beta, \gamma, \delta$` to get the first four Greek letters. And `$\Gamma$`, for example, produces a capital gamma letter. Don't confuse the Greek letters `\kappa` and `\nu` with the italic letters *v* and *x*; the Greek `\phi` is different from the slashed zero called `\emptyset`. A lowercase `\epsilon` is different from the symbol denoting membership in a set. Some of lowercase Greek letters have variant forms in LaTeX italic fonts: `$\phi, \theta, \epsilon, \rho$` yields ![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-2.png) while `$\varphi, \vartheta, \varepsilon, \varrho$` yields ![Single-character subscripts and superscripts](/tex/images/java/tutorial/latex-math-1-3.png)

Besides Greek letters, there are a lot of math symbols like "approximately equal" (`$\approx$`) and "maps to" (`$\mapsto$`). You can find a complete list of these control sequences and their corresponding symbols [here](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).