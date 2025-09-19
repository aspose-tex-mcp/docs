---
translation: true
template: /templates/_template-java.md
title: Rendu de figures LaTeX | Java
linktitle: Rendu de figures LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX pour le rendu des fragments Java LaTeX est décrite dans cet article. Découvrez les exemples de code sur la façon d’utiliser la fonctionnalité.
lastmod: "2024-09-27"
---

{{<section overview>}}

Il peut arriver que vous souhaitiez extraire du contenu (un dessin, une écriture, un tracé, etc.) d'un fichier LaTeX sous la forme d'un élément rendu séparément, ou d'une *"figure"*, quelle que soit sa place sur la page du document de sortie. . Une illustration pour votre publication sur Internet, par exemple, est le cas. Notre API peut vous aider dans cette tâche. Il existe deux formats cibles disponibles : PNG et SVG. Tout comme dans le rendu des formules mathématiques LaTeX. Nous devons également noter que le **rendu de figures LaTeX** est une généralisation du [rendu de formules mathématiques LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Comment rendre une figure LaTeX en PNG

Et comme pour le rendu de formule, nous commencerons par un exemple. C'est ici:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Tout d’abord, nous créons une instance [options de rendu](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Nous le faisons ici en spécifiant la résolution de l'image de sortie.

Ensuite, nous précisons le préambule. Il n'y a pas de préambule par défaut pour le rendu des figures LaTeX, donc si vous souhaitez, par exemple, restituer certains graphiques tracés à l'aide du package LaTeX `pict2e`, vous devez le spécifier dans le préambule :

```tex
\usepackage{pict2e}
```

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

L'option suivante définit la couleur d'arrière-plan. Contrairement au rendu de formules mathématiques, nous ne spécifions pas de couleur de premier plan puisque nous supposons que les couleurs sont entièrement sous le contrôle du code LaTeX. En fait, la couleur d’arrière-plan l’est également, ce n’est donc qu’une option pratique.

La ligne suivante de l'exemple n'a pas beaucoup de sens. Cela démontre simplement que vous pouvez diriger la sortie du journal vers un flux.

Et la dernière option « ShowTerminal » vous permet d'écrire la sortie du terminal sur la console.

La méthode qui effectue réellement le rendu est [FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Il renvoie la taille de la figure en points.

Le flux dans lequel l'image doit être écrite est accepté par la méthode comme deuxième argument. Nous créons ensuite le flux.

Et enfin, nous appelons la méthode `FigureRenderer.render()` elle-même, en passant les options comme troisième argument. Le code LaTeX de la figure est passé en premier argument.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de figure : la taille de la figure et le bref rapport d'erreur (en cas d'erreurs).

Voici le résultat du rendu.

![Rendu de la figure LaTeX en PNG](/tex/images/java/text-and-formula.png)

Il s'agit du cas d'utilisation le plus général de la fonctionnalité **Rendu de figures LaTeX**.

## Comment rendre une figure LaTeX en SVG

De la même manière, nous pouvons restituer une figure LaTeX au format SVG.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Les différences sont :

 * Nous utilisons la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) au lieu de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
 * Nous ne précisons pas la résolution.
 * Nous utilisons la classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) au lieu de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).

Voici le résultat :

<a href="/tex/images/java/text-and-formula.svg">![Rendu de figures LaTeX en SVG](/tex/images/java/text-and-formula.svg)</a>