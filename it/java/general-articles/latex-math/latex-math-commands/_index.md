---
translation: true
template: /templates/_template-java.md
linktitle: 3. Comandi in LaTeX
title: Comandi in LaTeX | Manuale in LaTeX | Aspose.TeX per java
weight: 30
url: /java/latex-math-commands/
keywords: Latex, formule di matematica in LaTeX, matematica in LaTeX, comandi matematica in LaTeX, radice quadrata in LaTeX, sottolineatura di matematica in LaTeX, matematica in LaTeX
description: Questo articolo discute un altro modo per comporre formule matematiche che coinvolgono comandi macro forniti dal LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}

Un altro modo per costruire formule complesse da quelle semplici è usare i comandi `\sqrt`,`\sottoline` o `\overline`. Si applicano anche al carattere o alla sottomissione che li segue:

![Applicazione più semplice dei comandi in LaTeX](/tex/images/java/tutorial/latex-math-3-1.png)

Puoi anche ottenere radici del cubo e cose simili:

![Radici di grado arbitrario](/tex/images/java/tutorial/latex-math-3-2.png)

These three commands place lines above and below subformulas of any size and shape; the bar lines change their size and position, so that they are long enough to cover the subformula, and high enough or low enough not to overlap with it. In particular, square root signs appear in a variety of positions depending on the height and depth of what's being `\sqrt`'ed: ![Radici di grado arbitrario](/tex/images/java/tutorial/latex-math-3-3.png) In such a case, you may want to typeset all square roots uniformly, like this: ![Radici di grado arbitrario](/tex/images/java/tutorial/latex-math-3-4.png) The easy way to do this is to use the command `\mathstrut`:

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

A `\Mathstrut` è una casella invisibile a larghezza zero. La sua altezza e profondità sono l'altezza e la profondità di una parentesi `(`. Ne consegue che le subformule che contengono `\mathstrut` avranno sempre la stessa altezza e profondità, a meno che non coinvolgano costruzioni più complicate come abbonamenti e sospetti.