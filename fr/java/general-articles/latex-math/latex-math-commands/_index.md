---
translation: true
template: /templates/_template-java.md
linktitle: Commandes LaTeX
title: 3. Commandes LaTeX
weight: 30
url: /java/latex-math-commands/
keywords: latex, formules mathématiques au latex, mathématiques au latex, commandes mathématiques au latex, racine carrée du latex, soulignement mathématique au latex, surlignement mathématique au latex
description: Cet article traite d'une autre façon de composer des formules mathématiques impliquant des commandes macro fournies par LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

Une autre façon de créer des formules complexes à partir de formules simples consiste à utiliser les commandes `\sqrt`, `\underline` ou `\overline`. Ils s'appliquent également au caractère ou à la sous-formule qui les suit :

![Application la plus simple des commandes LaTeX](/tex/images/java/tutorial/latex-math-3-1.png)

Vous pouvez également obtenir des racines cubiques et des éléments similaires :

![Racines de degré arbitraire](/tex/images/java/tutorial/latex-math-3-2.png)

Ces trois commandes placent des lignes au-dessus et au-dessous des sous-formules de n'importe quelle taille et forme ; les lignes de mesure changent de taille et de position, de sorte qu'elles soient suffisamment longues pour couvrir la sous-formule et suffisamment hautes ou suffisamment basses pour ne pas la chevaucher. En particulier, les signes de racine carrée apparaissent dans une variété de positions en fonction de la hauteur et de la profondeur de ce qui est `\sqrt`' : ![Racines de degré arbitraire](/tex/images/java/tutorial/latex-math-3-3.png) Dans un tel cas, vous souhaiterez peut-être composer tous les signes carrés racines uniformément, comme ceci : ![Racines de degré arbitraire](/tex/images/java/tutorial/latex-math-3-4.png) Le moyen le plus simple de le faire est d'utiliser la commande `\mathstrut` :

```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

Un `\mathstrut` est une boîte invisible de largeur nulle. Sa hauteur et sa profondeur sont la hauteur et la profondeur d'une parenthèse '('. Il s'ensuit que les sous-formules qui contiennent `\mathstrut` auront toujours la même hauteur et la même profondeur, à moins qu'elles n'impliquent des constructions plus compliquées comme des indices et des exposants.