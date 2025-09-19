---
translation: true
template: /templates/_template-java.md
linktitle: Fórmulas simples
title: 1. Fórmulas simples
weight: 10
url: /java/latex-math-simple-formulas/
keywords: LATEX, fórmulas de matemática de LaTeX, matemática de LaTeX, cartas de matemática de LaTeX, cartas gregas de LaTeX, números de LaTeX
description: Este artigo discute como criar expressões simples de matemática atômica para fórmulas mais complexas com Tex e LaTeX.
lastmod: "2025-06-16"
---

{{<section overview>}}

A fórmula mais simples é uma única letra '*x*' ou um único dígito '4'. Para inserir essa fórmula em um texto de LaTeX, você digita `$ x $` ou `$ 4 $`, respectivamente. Todas as fórmulas de matemática são fechadas em suportes matemáticos especiais (`$`).

Quando você digita `$ x $` the '*x*' sai em itálico, mas `$ 2 $` produz '2' no tipo romano. Em geral, todos os personagens do seu teclado têm uma interpretação especial nas fórmulas de matemática, de acordo com as convenções normais da impressão matemática. As cartas denotam cartas itálicas, enquanto dígitos e pontuações denotam dígitos romanos e pontuação. Um hífen (-) indica um sinal menos. O esquerdo `$` coloca Tex em "Modo de Matemática" e o certo o retira. Portanto, se você esquecer um `$` ou digite um extra `$`, provavelmente receberá uma mensagem de erro porque a TEX ficará confusa.

TeX does most of its own spacing in math formulas. At the same time, it ignores any spaces that you put between `$`'s. You can type `$(x + y)/(x - y)$` or `$(x+y) / (x-y)$`, but both will result in a formula ![Subscritos e superscritos de caracteres únicos](/tex/images/java/tutorial/latex-math-1-1.png) in which there is a bit extra space surrounding the '+' and '-' signs but none around the '/' sign. So, you don't have to remember the complicated rule of math spacing, and you're free to use spaces in any way you like. When it is necessary to mark the end of control sequences (commands), spaces are still used in the normal way. In most cases TeX's spacing will meet a mathematician's expectations; but if you want to override TeX's spacing rules, you can do so with control sequences, which we will discuss later.

One of the common things you may find in math formulas is the use of Greek letters. In LaTeX you can type `$\alpha, \beta, \gamma, \delta$` to get the first four Greek letters. And `$\Gamma$`, for example, produces a capital gamma letter. Don't confuse the Greek letters `\kappa`and `\nu` with the italic letters *v* and *x*; the Greek `\phi` is different from the slashed zero called `\emptyset`. A lowercase `\epsilon` is different from the symbol denoting membership in a set. Some of lowercase Greek letters have variant forms in LaTeX italic fonts: `$\phi, \theta, \epsilon, \rho$` yields ![Subscritos e superscritos de caracteres únicos](/tex/images/java/tutorial/latex-math-1-2.png) while `$\varphi, \vartheta, \varepsilon, \varrho$` yields ![Subscritos e superscritos de caracteres únicos](/tex/images/java/tutorial/latex-math-1-3.png)

Além de cartas gregas, existem muitos símbolos de matemática como "aproximadamente iguais" (`$ \ aprox $`) e "mapas para" (`$ \ mapsto $`). Você pode encontrar uma lista completa dessas seqüências de controle e seus símbolos correspondentes [aqui](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).