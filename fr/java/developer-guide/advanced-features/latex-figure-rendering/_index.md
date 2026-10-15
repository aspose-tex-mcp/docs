---
translation: true
template: /templates/_template-java.md
title: Rendu de figures LaTeX | Java
linktitle: Rendu de figures LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Aspose.TeX pour le rendu des fragments Java LaTeX est décrite dans cet article. Découvrez les exemples de code sur la façon d’utiliser la fonctionnalité.
lastmod: "2026-04-21"
---

{{<section overview>}}

Il peut arriver que vous souhaitiez extraire du contenu (un dessin, une écriture, un tracé, etc.) d'un fichier LaTeX sous la forme d'un élément rendu séparément, ou d'une *"figure"*, quelle que soit sa place sur la page du document de sortie. . Une illustration pour votre publication sur Internet, par exemple, est le cas. Notre API peut vous aider dans cette tâche. Il existe deux formats cibles disponibles : PNG et SVG. Tout comme dans le rendu des formules mathématiques LaTeX. Nous devons également noter que le **rendu de figures LaTeX** est une généralisation du [rendu de formules mathématiques LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Comment rendre une figure LaTeX en PNG

Et comme pour le rendu de formule, nous commencerons par un exemple. C'est ici:

Définissez `outputFile` comme un `java.nio.file.Path` dans un dossier existant, par exemple `Paths.get(outputDirectory, "text-and-formula.png")` pour PNG ou `Paths.get(outputDirectory, "text-and-formula.svg")` pour SVG. Importez les classes de moteur de rendu, d'options et `Size2D` d'Aspose.TeX utilisées, ainsi que `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence selon le [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d'évaluation.

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToPNG.java" >}}

Tout d’abord, nous créons une instance [options de rendu](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Nous le faisons ici en spécifiant la résolution de l'image de sortie.

Ensuite, nous précisons le préambule. Il n'y a pas de préambule par défaut pour le rendu des figures LaTeX, donc si vous souhaitez, par exemple, restituer certains graphiques tracés à l'aide du package LaTeX `pict2e`, vous devez le spécifier dans le préambule :

```tex
\usepackage{pict2e}
```

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %. Les exemples définissent aussi une marge de 5 points avec `setMargin(5)` autour de la figure. L'exemple PNG utilise 150 DPI.

L'option suivante définit la couleur d'arrière-plan. Contrairement au rendu de formules mathématiques, nous ne spécifions pas de couleur de premier plan puisque nous supposons que les couleurs sont entièrement sous le contrôle du code LaTeX. En fait, la couleur d’arrière-plan l’est également, ce n’est donc qu’une option pratique.

L'exemple dirige les journaux de rendu vers un `ByteArrayOutputStream` avec `setLogStream()`. Les flux du journal et de l'image sont fermés automatiquement après le rendu.

`showTerminal()` contrôle la sortie du terminal sur la console. Les exemples utilisent `false` ; définissez `true` pour l'afficher.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) est appelé sur une instance de `PngFigureRenderer` ou `SvgFigureRenderer` et renvoie les dimensions de la figure en points sous forme de `Size2D`.

La méthode accepte le flux de sortie de l'image comme deuxième argument. L'exemple l'ouvre dans un bloc try-with-resources, qui le ferme après le rendu.

Enfin, nous appelons `render()` sur l'instance du moteur de rendu : la figure LaTeX est le premier argument, le flux de l'image le deuxième et les options de rendu le troisième.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de figure : la taille de la figure et le bref rapport d'erreur (en cas d'erreurs).

Voici le résultat du rendu.

![Rendu de la figure LaTeX en PNG](/tex/images/java/text-and-formula.png)

Il s'agit du cas d'utilisation le plus général de la fonctionnalité **Rendu de figures LaTeX**.

## Comment rendre une figure LaTeX en SVG

De la même manière, nous pouvons restituer une figure LaTeX au format SVG.

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToSVG.java" >}}

Les différences sont :

 * Nous utilisons la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) au lieu de [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
 * Nous ne précisons pas la résolution.
 * Nous utilisons la classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) au lieu de [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).

Voici le résultat :

<a href="/tex/images/java/text-and-formula.svg">![Rendu de figures LaTeX en SVG](/tex/images/java/text-and-formula.svg)</a>