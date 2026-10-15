---
translation: true
template: /templates/_template-java.md
title: Rendu des formules mathématiques LaTeX | Java
linktitle: Rendu des formules mathématiques LaTeX
weight: 10
url: /java/latex-math-formula-rendering/
description: Le rendu des formules mathématiques LaTeX dans l'API Aspose.TeX pour Java est décrit dans cet article avec les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Comment restituer une formule mathématique LaTeX au format PNG

En fait, le moyen le plus simple de démontrer la fonctionnalité de rendu de la **formule mathématique LaTeX** est de commencer par l'exemple. C'est ici:

Définissez `outputFile` comme un `java.nio.file.Path` dans un dossier existant, par exemple `Paths.get(outputDirectory, "math-formula.png")` pour PNG ou `Paths.get(outputDirectory, "math-formula.svg")` pour SVG. Importez les classes de moteur de rendu, d'options et `Size2D` d'Aspose.TeX utilisées, ainsi que `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence selon le [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d'évaluation.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Passons aux détails. Tout d'abord, nous créons une instance [options de rendu](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), similaire à la composition TeX/LaTeX. Nous le faisons ici simultanément en spécifiant la résolution de l’image de sortie.

Ensuite, nous précisons le préambule. Le préambule par défaut est :

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

qui fournit une prise en charge des formules mathématiques légèrement plus avancée que LaTeX de base. Vous pouvez, par exemple, ajouter le package `color` si vous souhaitez utiliser votre propre surlignage dans la formule, comme nous l'avons montré dans l'exemple de code.

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

Les deux options définissent les couleurs de premier plan et d'arrière-plan. Les parties de la formule sans surbrillance personnalisée utilisent la couleur définie par `setTextColor()`.

L'exemple dirige les journaux de rendu vers un `ByteArrayOutputStream` avec `setLogStream()`. Les flux du journal et de l'image sont fermés automatiquement après le rendu.

`showTerminal()` contrôle la sortie du terminal sur la console. Les exemples utilisent `false` ; définissez `true` pour l'afficher.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) est appelé sur une instance de `PngMathRenderer` ou `SvgMathRenderer` et renvoie les dimensions de la formule en points sous forme de `Size2D`.

La méthode accepte le flux de sortie de l'image comme deuxième argument. L'exemple l'ouvre dans un bloc try-with-resources, qui le ferme après le rendu.

Enfin, nous appelons `render()` sur l'instance du moteur de rendu : la formule LaTeX est le premier argument, le flux de l'image le deuxième et les options de rendu le troisième.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de formule mathématique : la taille de la formule et le bref rapport d'erreur (au cas où il y aurait des erreurs).

Voici le résultat du rendu.

<a href="/tex/images/java/math-formula.png">![Rendu de la figure LaTeX au format PNG](/tex/images/java/math-formula.png)</a>

Il s'agit du cas d'utilisation le plus général du rendu de **formule mathématique LaTeX**.

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/equation-editor/png) gratuite construite sur la base de la fonctionnalité implémentée dans l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**

## Comment rendre une formule mathématique LaTeX en SVG

De la même manière, nous pouvons restituer une formule mathématique LaTeX au format SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Les différences sont :

* Nous utilisons la classe [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) au lieu de [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Nous ne précisons pas la résolution.
* Nous utilisons la classe [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) au lieu de [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Voici le résultat :

<a href="/tex/images/java/math-formula.svg">![Rendu de formule mathématique LaTeX en SVG](/tex/images/java/math-formula.svg)</a>

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/equation-editor/svg) gratuite construite sur la base de la fonctionnalité implémentée dans [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**