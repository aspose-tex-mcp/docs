---
translation: true
template: /templates/_template-python-net.md
title: Rendu des formules mathématiques LaTeX | Python
linktitle: Rendu des formules mathématiques LaTeX
weight: 10
url: /python-net/latex-math-formula-rendering/
description: L'article donne un aperçu de la solution API Aspose.TeX pour Python et de ses fonctionnalités de rendu des formules mathématiques LaTeX. Apprenez les exemples de code
lastmod: "2024-09-27"
---

{{<section overview>}}

## Rendu d'une formule mathématique LaTeX au format PNG

Si nécessaire, jetez un œil à la [section de référence API pour ce sujet](https://reference.aspose.com/tex/python-net/aspose.tex.features/). En fait, la meilleure façon de démontrer la fonctionnalité de rendu de la **formule mathématique LaTeX** est de commencer par un exemple. C'est ici:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Passons aux détails. Tout d'abord, nous lançons un objet [options de rendu](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), similaire à la composition TeX/LaTeX, qui inclut la spécification de la résolution de l'image de sortie souhaitée.

Ensuite, nous précisons le préambule. Le préambule par défaut est :


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

qui offre une prise en charge améliorée des formules mathématiques par rapport au LaTeX standard. Par exemple, vous pouvez inclure le package « color » pour personnaliser la mise en évidence dans la formule, comme démontré dans l'exemple de code fourni.

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

Les deux options suivantes déterminent les couleurs de premier plan et d’arrière-plan. Toutes les parties de la formule qui ne sont pas affectées par la surbrillance personnalisée seront affichées dans la couleur « TextColor ».

La ligne suivante de l'exemple illustre que vous avez la possibilité de rediriger la sortie du journal vers un flux spécifique.

Et enfin, l'option `ShowTerminal` vous permet de contrôler si la sortie du terminal doit être affichée dans la console.

Le processus de rendu proprement dit est effectué par la méthode [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), qui renvoie la taille de la formule en points.

La méthode accepte le flux dans lequel l'image sera écrite comme deuxième argument. Par la suite, nous procédons à la création du flux.

Et enfin, la méthode `MathRenderer.render()` est invoquée, les options étant passées comme troisième argument. Le code LaTeX de la formule est fourni comme premier argument.

Les dernières lignes de l'exemple affichent deux résultats du processus de rendu de formule mathématique : la taille de la formule et un rapport d'erreur concis, si des erreurs se produisent.

Voici le résultat du rendu.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Rendu de formule mathématique LaTeX au format PNG](/tex/images/python-net/math-formula.png)</a>

Il s'agit de l'application la plus courante et la plus large de la fonctionnalité de **rendu de formule mathématique LaTeX**.

**Vous pouvez également explorer l'[application Web] gratuite(5), qui utilise la fonctionnalité implémentée de l'[API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**

## Rendu d'une formule mathématique LaTeX en SVG

De même, nous pouvons convertir une formule mathématique LaTeX au format SVG en utilisant la même approche.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Les différences sont :

* Au lieu d'utiliser la classe [PngMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/), nous utilisons la classe [SvgMathRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Nous ne précisons pas la résolution.
* Au lieu d'utiliser la classe [PngMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/), nous utilisons la classe [SvgMathRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Voici le résultat :

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Rendu de formule mathématique LaTeX en SVG](/tex/images/python-net/math-formula.svg)</a>

**Vous pouvez également explorer l'[application Web] gratuite(12), qui utilise la fonctionnalité implémentée de l'[API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**