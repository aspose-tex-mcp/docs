---
translation: true
template: /templates/_template-java.md
linktitle: Grands opérateurs
title: 6. Grands opérateurs
weight: 60
url: /java/latex-math-large-operators/
keywords: latex, formules mathématiques en latex, mathématiques en latex, grands opérateurs mathématiques en latex, somme en latex, intégrale en latex
description: Cet article explique comment créer des formules mathématiques contenant des opérateurs volumineux tels que la sommation et l'intégration avec TeX et LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

En mathématiques, il existe des symboles qui désignent, par exemple, les opérations de « sommation » ou d'« intégration ». Ils sont appelés « grands opérateurs » et vous les tapez exactement comme vous tapez des symboles et des lettres ordinaires. La différence est que TeX choisira un symbole plus grand pour le grand opérateur dans le style d'affichage que dans le style de texte.

![Sommation et intégration sans super/indices](/tex/images/java/tutorial/latex-math-6-1.png)

Un `\sum` affiché apparaît généralement avec des "limites", c'est-à-dire avec des sous-formules qui doivent apparaître au-dessus et en dessous. Les limites doivent être saisies comme s'il s'agissait d'indices et d'exposants ;
`$$\sum_{n=1}^m$$` ou `$$\sum^m_{n=1}$$` produisent tous deux

![Sommation avec limites](/tex/images/java/tutorial/latex-math-6-2.png)

Les conventions normales de composition mathématique supposent que la formule ci-dessus doit être modifiée en

![Sommation sans limites](/tex/images/java/tutorial/latex-math-6-3.png)

(c'est-à-dire sans limites) si cela se produit dans le texte plutôt que dans un affichage. Et TeX suit ces conventions.

Les exposants et les indices sur le signe d'intégration ne sont pas définis comme limites, même dans le style d'affichage :

![Intégration dans un texte et dans un affichage](/tex/images/java/tutorial/latex-math-6-4.png)

Définir des indices et des exposants comme limites donne une meilleure apparence si les sous-formules sont complexes, mais prend plus de place sur la page. Vous pouvez forcer TeX à traiter la formule de cette manière en tapant `\limits` immédiatement après `\int`, ou `\sum`, ou un autre opérateur, quel que soit le style qui sera utilisé dans la sous-formule. D’un autre côté, les limites imposées aux signes de sommation affichés ne sont parfois pas souhaitables. Vous pouvez modifier la convention de TeX en tapant « \nolimits » immédiatement après le grand opérateur.

![Forçage des limites et aucune limite pour la sommation et l'intégration](/tex/images/java/tutorial/latex-math-6-5.png)

Si vous dites `\nolimits\limits` (par exemple, certaines macros comme `\int` spécifient `\nolimits`), la dernière commande est prioritaire. La commande `\displaylimits` peut être utilisée pour passer aux conventions normales de TeX ; c'est-à-dire que les limites seront affichées uniquement dans les styles *D* et *D'*.

Si vous devez mettre plus d'une ligne de limites sous un grand opérateur, vous pouvez le faire avec `\atop`. La bonne façon de taper la formule suivante est 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![Limites multi-lignes sous le signe de sommation](/tex/images/java/tutorial/latex-math-6-6.png)

La commande `\scriptstyle` est nécessaire ici, sinon les deux lignes de la limite auraient été en taille scriptscript, ce qui est trop petit. Il s'agit d'un autre cas rare où les règles de style de TeX doivent être remplacées.