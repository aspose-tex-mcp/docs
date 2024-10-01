---
translation: true
template: /templates/_template-java.md
linktitle: 2. Indice et indice
title: Indice et indice en LaTeX | Manuel LaTeX
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: latex, formules mathématiques au latex, mathématiques au latex, indices mathématiques au latex, exposants mathématiques au latex
description: Cet article explique comment créer des formules mathématiques contenant des indices et des exposants avec TeX et LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}


## Introduction à l'exposant et aux indices LaTeX

**L'exposant** est un petit caractère ou un symbole positionné légèrement au-dessus de la ligne de base du texte.  Par exemple, dans l'expression « x² », le « 2 » est un exposant.

**L'indice** est un petit caractère ou un symbole positionné légèrement en dessous de la ligne de base du texte. Par exemple, dans la formule chimique de l'eau, « H₂O », le « 2 » est un indice.

## Comment écrire un indice/exposant dans LaTeX

Essayons maintenant de créer des formules plus complexes à partir de formules simples. Tout d'abord, vous pouvez obtenir les exposants et les indices en utilisant `^` et `_`, comme le montre l'exemple suivant :

![Indices et exposants à un seul caractère](/tex/images/java/tutorial/latex-math-2-1.png)

Notez que `^` et `_` s'appliquent uniquement au caractère suivant. Si vous souhaitez un indice ou un exposant plus complexe, placez-le simplement entre accolades :

![Indices et exposants multi-caractères](/tex/images/java/tutorial/latex-math-2-2.png)

Les accolades dans ces exemples spécifient des « sous-formules » – des parties plus simples d'une formule plus grande. TeX crée une boîte pour chaque sous-formule et traite cette boîte comme s'il s'agissait d'un seul symbole. Les accolades remplissent également leur fonction habituelle de regroupement.

Il est illégal de taper `$x^y^z$` ou `$x_y_z$`. TeX se plaindra d'un "double indice" ou d'un "double exposant". Vous devez indiquer plus clairement ce que vous voulez en tapant soit `$x^{y^z}$`, ou `$x^{yz}$`, ou `$x_{y_z}$`, ou `$x_{yz} $`.

Un exposant ou un indice suivant un caractère s'applique uniquement à ce caractère ; mais lorsque vous suivez une sous-formule, cela s'applique à cette sous-formule entière, et elle sera augmentée ou diminuée en conséquence.

![Indices et exposants sur un seul symbole et sur une sous-formule](/tex/images/java/tutorial/latex-math-2-3.png)

Dans la première formule, les « ^3 » et « ^4 » sont des exposants sur les parenthèses droites qui les précèdent immédiatement, mais dans la deuxième formule, ce sont des exposants sur les sous-formules qui sont entourées d'accolades. La première version est préférable, car elle est plus facile à taper et tout aussi facile à lire.

## Écrire un indice ou un exposant sur une sous-formule vide

Parfois, vous devrez peut-être créer un indice ou un exposant sur une sous-formule vide pour produire une notation plutôt rare comme *<sub>2</sub>F<sub>3</sub>*. La meilleure façon de le faire est de taper `${}_2F_3$` ou `${_2}F_3$` ou `${_2F_3}$`.

Vous pouvez également avoir des « indices supérieurs » simultanés, et vous pouvez les spécifier dans n'importe quel ordre :

![Indices simultanés](/tex/images/java/tutorial/latex-math-2-4.png)

Ces « indices » simultanés sont positionnés les uns sur les autres. Cependant, pour certaines lettres, un indice sera décalé vers la gauche ; et pour certaines de ces lettres, c'est assez visible. Comparez les deux formules suivantes :

![Alignement simultané des indices](/tex/images/java/tutorial/latex-math-2-5.png)

Donc, si vous souhaitez que l'indice et l'exposant soient alignés, vous pouvez utiliser l'astuce présentée dans la deuxième version. Encore une fois, il profite d’une sous-formule vide.

## Écrire en prime dans LaTeX

La prochaine chose qui apparaît fréquemment dans les formules mathématiques est le symbole premier. LaTeX fournit la commande `\prime`, qui produit elle-même un symbole prime de la taille d'une lettre normale. Ainsi, vous ne voudriez jamais l’utiliser sauf en exposant ou en indice. Mais vous pouvez simplement taper `'` au lieu de `^\prime`, et `''` au lieu de `^\prime\prime`, et ainsi de suite.

![Premiers](/tex/images/java/tutorial/latex-math-2-6.png)

## Double exposant LaTeX

Dans LaTeX, vous pouvez écrire des exposants doubles en plaçant l'expression entière en exposant entre accolades {}. Voici un exemple : `x^{a^b}`

## Double indice LaTeX

Dans LaTeX, vous pouvez écrire des indices doubles de la même manière en plaçant l'expression d'indice entière entre accolades {}. Voici un exemple : `X_{i_{j}}`