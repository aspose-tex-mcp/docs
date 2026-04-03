---
translation: true
template: /templates/_template-python-net.md
title: Rendu de figures LaTeX | Python via .NET
linktitle: LaTeX inclut la figure
weight: 20
url: /python-net/latex-figure-rendering/
description: L'article donne un aperçu de la API Aspose.TeX pour Python et de ses fonctionnalités de rendu de fragments LaTeX (figures). Apprenez les exemples de code.
keywords: figurine en latex, taille de figurine en latex, image en latex, image en latex, figurine incluse en latex, photo en latex, options de figurine en latex
lastmod: "2026-04-03"
---

{{<section overview>}}

Dans certaines situations, vous devrez peut-être extraire du contenu spécifique d'un fichier LaTeX en tant qu'élément rendu autonome, communément appelé *figure*, sans aucune connexion avec la mise en page. Cela peut être utile, par exemple, lors de la création d'illustrations pour une publication en ligne. Notre API vous permet d'accomplir cela. Les formats cibles pour le rendu des figures sont PNG et SVG, tout comme avec la fonction de rendu de formules mathématiques LaTeX. Il convient de noter que le **rendu de figures LaTeX** est une fonctionnalité plus générale par rapport au [rendu de formule mathématique LaTeX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Rendu d'une figure LaTeX en PNG

Si nécessaire, jetez d'abord un œil à la [section de référence API pour ce sujet](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Semblable au rendu de formule, nous commencerons par un exemple. C'est ici:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Pour commencer, nous créons une instance de la classe [LaTeX figure renderer options](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), où nous spécifions simultanément la résolution de l'image de sortie.

Ensuite, nous devons préciser le préambule. Contrairement au rendu des formules mathématiques LaTeX, il n'y a pas de préambule par défaut pour le rendu des figures LaTeX. Par conséquent, si vous envisagez de restituer des graphiques créés à l'aide du package LaTeX `pict2e`, par exemple, vous devrez le spécifier dans le préambule :

```tex
\usepackage{pict2e}
```

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

L'option suivante détermine la couleur d'arrière-plan. Contrairement au rendu des formules mathématiques, nous n'avons pas besoin de spécifier une couleur de premier plan, car nous supposons que les couleurs sont entièrement contrôlées par le code LaTeX. De même, la couleur d'arrière-plan est également contrôlée par le code LaTeX, cette option est donc simplement fournie pour plus de commodité.

La ligne suivante dans l'exemple n'est peut-être pas particulièrement significative. Il est simplement destiné à démontrer que vous avez la possibilité de diriger la sortie du journal vers un flux spécifique.

La dernière option, `ShowTerminal`, vous permet de contrôler si la sortie du terminal doit être affichée dans la console.

La méthode responsable du rendu de la figure est [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/#str-io.RawIOBase-aspose.tex.features.FigureRendererOptions). Il renvoie la taille de la figure en points.

La méthode accepte un flux comme deuxième argument, qui est le flux dans lequel l'image sera écrite. Nous créons le flux dans la ligne suivante.

Enfin, nous invoquons la méthode `FigureRenderer.render()` elle-même, en passant les options comme troisième argument. Le code LaTeX de la figure est fourni comme premier argument.

Les dernières lignes de l'exemple affichent deux informations liées au rendu de la figure : la taille de la figure et un bref rapport d'erreur (s'il y a des erreurs).

Voici le résultat du rendu.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Rendu de figure LaTeX au format PNG](/tex/images/python-net/text-and-formula.png)</a>

Il s'agit du cas d'utilisation le plus général de la fonctionnalité **Rendu de figures LaTeX**.

## Rendu d'une figure LaTeX en SVG

De même, nous pouvons également restituer une figure LaTeX au format SVG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Les différences sont :

* Au lieu d'utiliser la classe [PngFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/), nous utilisons la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Nous n'avons pas besoin de préciser la résolution.
* Au lieu d'utiliser la classe [PngFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/), nous utilisons la classe [SvgFigureRenderer](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).

Voici le résultat :

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Rendu de figures LaTeX en SVG](/tex/images/python-net/text-and-formula.svg)</a>