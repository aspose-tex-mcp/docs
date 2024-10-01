---
translation: true
template: /templates/_template-java.md
linktitle: 7. Délimiteurs
title: Délimiteurs | Manuel LaTeX | Aspose.TeX
weight: 70
url: /java/latex-math-delimiters/
keywords: latex, formules mathématiques en latex, mathématiques en latex, délimiteurs mathématiques en latex, bretelles mathématiques en latex, supports mathématiques en latex, parenthèses mathématiques en latex
description: Cet article explique comment diviser logiquement des formules en sous-formules avec différents types de délimiteurs.
lastmod: "2024-09-27"
---

{{<section overview>}}

Quelle que soit la taille d'une formule mathématique, TeX connaît un moyen de créer des symboles suffisamment grands pour avoir une apparence correcte. Par exemple, le résultat de la saisie

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

montre une variété de signes radicaux ou racines carrées disponibles :

![Radicaux de différentes tailles](/tex/images/java/tutorial/latex-math-7-1.png)

Les trois plus grands signes ici sont les mêmes, à l'exception d'un segment vertical qui est répété autant de fois que nécessaire pour atteindre la taille requise. Dans le même temps, les signes plus petits sont des caractères distincts tirés des polices mathématiques de TeX.

Quelque chose de similaire se produit avec les parenthèses et autres symboles dits « délimiteurs ». De tels symboles sont importants en mathématiques, car ils donnent des indices visuels sur la structure sous-jacente d’expressions complexes. En d’autres termes, ils limitent les limites des sous-formules individuelles. Voici la liste des 22 délimiteurs de base fournis par LaTeX :

![Les 22 délimiteurs de base définis dans LaTeX](/tex/images/java/tutorial/latex-math-7-2.png)

Pour obtenir une version légèrement plus grande de l'un de ces symboles, tapez simplement `\bigl` ou `\bigr` pour ouvrir ou fermer les délimiteurs, respectivement. Cela rend les formules avec des délimiteurs imbriqués plus faciles à lire :

![Les exemples d'utilisation des \big délimiteurs](/tex/images/java/tutorial/latex-math-7-3.png)

Les délimiteurs `\big` sont juste assez grands que les délimiteurs ordinaires pour que la différence puisse être remarquée, et pourtant suffisamment petits pour être utilisés dans le texte d'un paragraphe :

![Les \grands délimiteurs comparés aux délimiteurs normaux](/tex/images/java/tutorial/latex-math-7-4.png)

Vous pouvez obtenir des symboles encore plus grands adaptés aux affichages, si vous tapez `\Bigl` et `\Bigr` au lieu de `\bigl` et `\bigr` :

![Les \Grands délimiteurs](/tex/images/java/tutorial/latex-math-7-5.png)

Celles-ci sont 50 % plus hautes que les versions de l'étape précédente. Les formules affichées utilisent souvent des délimiteurs encore plus grands (deux fois la taille de `\big`). Vous pouvez les obtenir en tapant `\biggl` et `\biggr` :

![Les \bigg délimiteurs](/tex/images/java/tutorial/latex-math-7-6.png)

Enfin, vous pouvez taper les versions `\Biggl` et `\Biggr`, 2,5 fois plus hautes que les délimiteurs `\bigl` et `\bigr` :

![Les délimiteurs \Bigg](/tex/images/java/tutorial/latex-math-7-7.png)

LaTeX fournit également les commandes `\bigm`, `\Bigm`, `\biggm` et `\Biggm` pour produire des délimiteurs pouvant être utilisés au milieu des formules. Un tel délimiteur agit comme une relation, donc TeX met un peu d'espace de chaque côté :

![Délimiteurs au milieu des formules](/tex/images/java/tutorial/latex-math-7-8.png)

Il est également possible de dire simplement `\big`, `\Big`, `\bigg` ou `\Bigg` pour produire un délimiteur qui se comporte comme une variable ordinaire. Ces commandes seraient principalement utilisées avec des barres obliques et des barres obliques inverses :

![Grands symboles ordinaires](/tex/images/java/tutorial/latex-math-7-9.png)

TeX implémente un algorithme qui détermine la hauteur que doit avoir une paire de délimiteurs, afin de contenir une sous-formule donnée. Vous pouvez l'utiliser au lieu de décider si un délimiteur doit être `\big` ou `\bigg` ou autre. Dis juste


```tex
\left<delim1><subformula>\right<delim2>
```

et TeX composera une sous-formule, en plaçant les délimiteurs spécifiés à gauche et à droite. La taille des délimiteurs sera juste assez grande pour couvrir la sous-formule :

![Délimiteurs définis par les commandes \left et \right](/tex/images/java/tutorial/latex-math-7-10.png)
Lorsque vous utilisez `\left` et `\right`, ils doivent être appariés, tout comme les accolades le font pour les groupes. Vous ne pouvez pas avoir « \left » dans une sous-formule et « \right » dans une autre. De plus, vous ne pouvez pas taper des éléments comme `\left(...{...\right...}` ou `\left(...\begingroup...\right)...\endgroup`. En effet, TeX doit composer la sous-formule qui apparaît entre `\left` et `\right` avant de pouvoir décider de la taille des délimiteurs. Lorsque vous n'utilisez pas `\left` et `\right`, vous ne le faites pas. Vous n'avez pas besoin de faire correspondre les parenthèses et les crochets. Vous êtes donc autorisé à taper quelque chose comme `$[0,1)$` ou `$)($` ou même `$)$`. Et même lorsque vous utilisez `\left` et `\right`, vous n'avez pas besoin de faire correspondre les symboles particuliers, de sorte que `\left)` ou `\right(` ne provoqueront pas d'erreur.

Mais pourquoi s'embêter à se renseigner sur `\bigl` et `\bigr` et d'autres du même genre, alors que TeX peut calculer automatiquement les tailles pour `\left` et `\right` ? Il existe au moins trois cas dans lesquels vous souhaiteriez décider vous-même de la sélection de la taille appropriée du délimiteur :

(1) Comparez simplement les deux formules suivantes :

![\left et \right vs. \bigl et \bigr avec barres verticales](/tex/images/java/tutorial/latex-math-7-11.png)

En effet, utiliser `\left` et `\right` n'était pas un choix judicieux, car ils ne parvenaient pas à déterminer la taille du délimiteur appropriée pour une meilleure lisibilité.

(2) D'un autre côté, parfois `\left` et `\right` choisissent un délimiteur plus grand que vous ne le souhaitez. Cela se produit principalement lorsqu'ils enferment un grand opérateur dans un écran :

![\left et \right contre \bigl et \bigr avec une sommation](/tex/images/java/tutorial/latex-math-7-12.png)

L'algorithme de TeX fait que `\left` et `\right` enferment le `\sum` avec ses limites, mais dans des cas particuliers comme celui-ci, il semble préférable de laisser les limites traîner un peu. Les délimiteurs `\bigg` sont donc meilleurs ici.

(3) Lorsque vous devez composer une énorme formule affichée, vous devez la diviser en deux lignes ou plus. Et vous voulez vous assurer que ses délimiteurs d’ouverture et de fermeture ont la même taille ; mais vous ne pouvez pas utiliser `\left` sur la première ligne et `\right` sur la dernière, puisque `\left` et `\right` doivent apparaître par paires. La seule solution est d'utiliser `\Biggl` (par exemple) sur la première ligne et `\Biggr` sur la dernière.

> Bien que `\left` et `\right` puissent généralement constituer des délimiteurs de taille arbitraire, les barres obliques et les chevrons ont une taille maximale. Si vous demandez des versions vraiment grandes de ces symboles, vous obtiendrez les plus grandes disponibles.

Vous pouvez également utiliser une astuce qui produit un délimiteur dit nul (vide). Vous auriez besoin d'un tel délimiteur lorsque vous devez composer une formule qui ne contient visuellement qu'un seul grand délimiteur. Par exemple,

![Un délimiteur nul dans les cas](/tex/images/java/tutorial/latex-math-7-13.png)

a '{' mais pas de '}'. Il peut être produit par une construction de la forme


```tex
$$|x|=\left\{ ... \right.$$ 
```

où `\right.` génère le délimiteur nul droit.

LaTeX fournit également quelques délimiteurs supplémentaires, qui ne sont pas répertoriés dans l'ensemble de base de 22 car ils sont en quelque sorte spéciaux. Les commandes `\arrowvert`, `\Arrowvert` et `\bracevert` produisent des délimiteurs constitués respectivement des parties répétables des flèches verticales, des doubles flèches verticales et des grandes accolades, sans pointes de flèches ni parties bouclées des accolades. Ils produisent des résultats similaires à `\vert` et `\Vert`, mais ils sont entourés de plus d'espaces blancs et ont un poids différent. Il existe également `\lgroup` et `\rgroup`, qui sont construits à partir d'accolades sans les parties médianes ; et `\lmoustache` et `\rmoustache`, qui produisent les moitiés supérieure et inférieure des grandes bretelles. Voici les affichages avec les versions `\Big` et `\bigg` de `\vert`, `\Vert` et ces sept délimiteurs spéciaux :

![Délimiteurs supplémentaires fournis par LaTeX](/tex/images/java/tutorial/latex-math-7-14.png)

Vous pouvez constater que `\lgroup` et `\rgroup` ressemblent plutôt à des parenthèses grasses, avec des courbures plus prononcées dans les coins ; cela les rend attrayants pour certains grands écrans. Notez que vous ne pouvez pas les utiliser exactement comme des parenthèses, car elles ne sont disponibles que dans les tailles `\Big` et plus.