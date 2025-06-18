---
translation: true
template: /templates/_template-java.md
linktitle: 3. Comandos de LaTeX
title: Comandos de LaTeX | Manual de LaTeX | Aspose.TeX para java
weight: 30
url: /java/latex-math-commands/
keywords: Latex, fórmulas de matemática de LaTeX, matemática de LaTeX, comandos de matemática de LaTeX, raiz da praça de LaTeX, sublinhamento de matemática de LaTeX, latex matemática Overline
description: Este artigo discute outra maneira de compor fórmulas matemáticas que envolvem comandos de macro fornecidos pelo LATEX.
lastmod: "2025-06-16"
---

{{<section overview>}}

Outra maneira de construir fórmulas complexas a partir de simples é usar os comandos `\sqrt`, `\sublline` ou `\overline`. Eles também se aplicam ao personagem ou subformula que os segue:

![Aplicação mais simples de comandos de LaTeX](/tex/images/java/tutorial/latex-math-3-1.png)

Você também pode obter raízes de cubo e coisas semelhantes:

![Raízes de grau arbitrário](/tex/images/java/tutorial/latex-math-3-2.png)

These three commands place lines above and below subformulas of any size and shape; the bar lines change their size and position, so that they are long enough to cover the subformula, and high enough or low enough not to overlap with it. In particular, square root signs appear in a variety of positions depending on the height and depth of what's being `\sqrt`'ed: ![Raízes de grau arbitrário](/tex/images/java/tutorial/latex-math-3-3.png) In such a case, you may want to typeset all square roots uniformly, like this: ![Raízes de grau arbitrário](/tex/images/java/tutorial/latex-math-3-4.png) The easy way to do this is to use the command `\mathstrut`:

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

A `\mathStrut` é uma caixa invisível de largura zero. Sua altura e profundidade são a altura e a profundidade de um parêntese '('. Segue -se que as subformulas que contêm `\mathstrut` sempre terão a mesma altura e profundidade, a menos que envolvam construções mais complicadas, como subscritos e superestritos.