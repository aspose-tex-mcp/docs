---
translation: true
template: /templates/_template-net.md
title: Rendu de figures LaTeX | Aspose.TeX pour .NET
linktitle: LaTeX inclut la figure
weight: 20
url: /net/latex-figure-rendering/
description: La solution API Aspose.TeX pour le rendu des fragments (figures) .NET LaTeX est décrite dans cet article. Découvrez les exemples de code sur la façon d’utiliser la fonctionnalité.
keywords: figurine en latex, taille de figurine en latex, image en latex, image en latex, figurine incluse en latex, photo en latex, options de figurine en latex
lastmod: "2024-09-27"
---

{{<section overview>}}


Parfois, vous souhaiterez peut-être extraire du contenu d'un fichier LaTeX sous la forme d'un élément rendu séparément, ou d'une *"figure"*, sans aucune connexion avec la mise en page. Il peut s'agir d'une illustration pour votre publication sur Internet par exemple. Vous pouvez le faire avec notre API. Quant aux formats cibles, il existe deux options : PNG et SVG. Comme c’est le cas avec la fonctionnalité de rendu de formules mathématiques LaTeX. Il convient également de noter que le **rendu de figures LaTeX** est une généralisation du [rendu de formule mathématique LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Comment rendre une figure LaTeX en PNG

La section de référence de l'API liée à ce sujet est [ici](https://reference.aspose.com/tex/net/aspose.tex.features/). Et comme pour le rendu de formule, nous commencerons par un exemple. C'est ici:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.cs" >}}

Tout d'abord, nous créons une instance [LaTeX figure options](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Nous le faisons ici simultanément en spécifiant la résolution de l’image de sortie.

Ensuite, nous précisons le préambule. Il n'y a pas de préambule par défaut pour le rendu des figures LaTeX, donc si vous souhaitez, par exemple, restituer des graphiques tracés à l'aide du package LaTeX `pict2e`, vous devez le spécifier dans le préambule :


```tex
\usepackage{pict2e}
```

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

L'option suivante définit la couleur d'arrière-plan. Contrairement au rendu de formules mathématiques, nous ne spécifions pas de couleur de premier plan puisque nous supposons que les couleurs sont entièrement sous le contrôle du code LaTeX. En fait, la couleur d’arrière-plan l’est également, ce n’est donc qu’une option pratique.

La ligne suivante de l'exemple n'a pas beaucoup de sens. Cela démontre simplement que vous pouvez diriger la sortie du journal vers un flux.

Et la dernière option « ShowTerminal » vous permet d'écrire la sortie du terminal sur la console.

La méthode qui effectue réellement le rendu est [FigureRenderer.Render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Il renvoie la taille de la figure en points.

Le flux dans lequel l'image doit être écrite est accepté par la méthode comme deuxième argument. Nous créons ensuite le flux.

Et enfin, nous appelons la méthode `FigureRenderer.Render()` elle-même, en passant les options comme troisième argument. Le code LaTeX de la figure est passé en premier argument.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de figure : la taille de la figure et le bref rapport d'erreur (en cas d'erreurs).

Voici le résultat du rendu.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Rendu de figure LaTeX au format PNG](/tex/images/net/text-and-formula.png)</a>

Il s'agit du cas d'utilisation le plus général de la fonctionnalité **Rendu de figures LaTeX**.

## Comment rendre une figure LaTeX en SVG

De la même manière, nous pouvons restituer une figure LaTeX au format SVG.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.cs" >}}

Les différences sont :

* Nous utilisons la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) au lieu de [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Nous ne précisons pas la résolution.
* Nous utilisons la classe [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) au lieu de [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).


Voici le résultat :

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Rendu de figure LaTeX en SVG](/tex/images/net/text-and-formula.svg)</a>