---
translation: true
template: /templates/_template-java.md
title: Rendu des formules mathématiques LaTeX | Java
linktitle: Rendu des formules mathématiques LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: Le rendu des formules mathématiques LaTeX dans l'API Aspose.TeX pour Java est décrit dans cet article. Découvrez les exemples de code expliquant comment utiliser la fonctionnalité.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Comment restituer une formule mathématique LaTeX au format PNG

En fait, le moyen le plus simple de démontrer la fonctionnalité de rendu de la **formule mathématique LaTeX** est de commencer par l'exemple. C'est ici:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Passons aux détails. Tout d'abord, nous créons une instance [options de rendu](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), similaire à la composition TeX/LaTeX. Nous le faisons ici simultanément en spécifiant la résolution de l’image de sortie.

Ensuite, nous précisons le préambule. Le préambule par défaut est :

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

qui fournit une prise en charge des formules mathématiques légèrement plus avancée que LaTeX de base. Vous pouvez, par exemple, ajouter le package `color` si vous souhaitez utiliser votre propre surlignage dans la formule, comme nous l'avons montré dans l'exemple de code.

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

Les deux options suivantes définissent les couleurs de premier plan et d'arrière-plan. Les parties de la formule qui ne sont pas couvertes (« colorées ») par la surbrillance personnalisée seront affichées dans la couleur « TextColor ».

La ligne suivante de l'exemple n'a pas beaucoup de sens. Cela démontre simplement que vous pouvez diriger la sortie du journal vers un flux.

Et la dernière option « ShowTerminal » vous permet d'écrire la sortie du terminal sur la console.

La méthode qui effectue réellement le rendu est [MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Il renvoie la taille de la formule en points.

Le flux dans lequel l'image doit être écrite est accepté par la méthode comme deuxième argument. Nous créons ensuite le flux.

Et enfin, nous appelons la méthode `MathRenderer.render()` elle-même, en passant les options comme troisième argument. Le code LaTeX de la formule est passé en premier argument.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de formule mathématique : la taille de la formule et le bref rapport d'erreur (au cas où il y aurait des erreurs).

Voici le résultat du rendu.

<a href="/tex/images/java/math-formula.png">![Rendu de la figure LaTeX au format PNG](/tex/images/java/math-formula.png)</a>

Il s'agit du cas d'utilisation le plus général du rendu de **formule mathématique LaTeX**.

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/equation-editor/png) gratuite construite sur la base de la fonctionnalité implémentée dans l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**

## Comment rendre une formule mathématique LaTeX en SVG

De la même manière, nous pouvons restituer une formule mathématique LaTeX au format SVG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Les différences sont :

 * Nous utilisons la classe [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) au lieu de [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
 * Nous ne précisons pas la résolution.
 * Nous utilisons la classe [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) au lieu de [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Voici le résultat :

<a href="/tex/images/java/math-formula.svg">![Rendu de formule mathématique LaTeX en SVG](/tex/images/java/math-formula.svg)</a>

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/equation-editor/svg) gratuite construite sur la base de la fonctionnalité implémentée dans [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**