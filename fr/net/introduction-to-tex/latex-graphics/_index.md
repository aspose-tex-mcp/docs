---
translation: true
template: /templates/_template-java.md
title: Graphiques LaTeX | Commande \includegraphics
linktitle: Graphiques LaTeX
weight: 18
url: /net/latex-graphics/
description: L'inclusion de graphiques dans TeX mérite d'être mentionnée. Quand on en parle, la première chose qui vient à l'esprit est la commande `\includegraphics`.
lastmod: "2024-09-27"
---

{{<section overview>}}

En fait, il y a deux aspects des graphiques LaTeX qui méritent d’être mentionnés :

 * graphiques vectoriels décrits directement au moyen de commandes LaTeX/TeX et,
 * inclusion de graphiques externes décrits au moyen de formats externes, comme EPS, PDF ou raster PNG et PDF.

Le premier a un support limité dans le LaTeX d'origine et ses packages. Il est implémenté à l’aide des règles verticales et horizontales TeX. En effet, le LaTeX original est basé sur le moteur TeX original, qui produit une sortie principale au format *DVI*, qui ne convient pas à la description de lignes et de courbes ou de données d'images raster binaires. Mais les moteurs capables de produire des formats prenant en charge les graphiques (comme pdfTeX en PDF) peuvent également traiter des graphiques à l'aide de packages ou de fonctionnalités de package dépendant du format. Ces derniers graphiques ne sont pas pris en charge dans LaTeX de base pour la même raison. Nous discuterons des fonctionnalités d’inclusion graphique ci-dessous.

## Le package LaTeX `graphics` et la commande `\includegraphics`

Lorsqu'on parle d'inclusion graphique LaTeX, la première chose qui vient à l'esprit est la commande `\includegraphics`. Il est défini dans le package `graphics`, que vous devez mentionner dans le préambule pour activer ses fonctionnalités.

```tex
\usepackage{graphics}
```

Si votre système de composition n'est pas configuré pour utiliser, par exemple, pdfTeX par défaut, vous devez spécifier l'option appropriée qui forcera le package à utiliser le fichier « pilote » requis :


```tex
\usepackage[pdftex]{graphics}
```
Un fichier « pilote » fait partie d'un package qui implémente l'interface entre les commandes du package et les primitives d'extension TeX de bas niveau dépendant du format. La prise en charge graphique LaTeX d'Aspose.TeX est configurée pour utiliser son propre pilote, vous n'avez donc pas besoin de spécifier l'option du pilote.

Maintenant, le moyen le plus simple d'inclure, par exemple, une image PNG est de taper :


```tex
\includegraphics{sample-image.png}
```
où `sample-image.png` est le nom du fichier que vous souhaitez inclure. Vous pouvez même omettre l'extension. Le package `graphics` contient la liste des définitions des formats pris en charge. Lors de la recherche d'un fichier, il parcourt cette liste et inclut le premier fichier correspondant trouvé.

Vous pouvez également spécifier le nom complet du fichier à l'aide d'un chemin absolu ou relatif :


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Une autre façon de spécifier le(s) emplacement(s) des fichiers graphiques consiste à définir une liste de chemins alternatifs à l'aide de la commande `\graphicspath` avant d'appeler `\includegraphics` :


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Mise à l'échelle des graphiques

Le package LaTeX `graphics` fournit des commandes pour manipuler le contenu. Vous pouvez donc mettre à l'échelle les graphiques inclus (en fait, tout ce qui est décrit par le code TeX/LaTeX) comme suit :


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Redimensionner les graphiques

C'est similaire à la mise à l'échelle, mais vous spécifiez la taille requise au lieu d'un ou plusieurs facteurs de mise à l'échelle :


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Rotation des graphiques

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## Le paquet LaTeX `graphicx`

Le package LaTeX `graphicx` fournit l'interface `key=value` pour les transformations de contenu. Pour activer ses fonctionnalités, vous devez le mentionner en préambule :


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Vous pouvez combiner n’importe laquelle des options suivantes, mais gardez à l’esprit que l’ordre est important.

### Fenêtre graphique

```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Mise à l'échelle des graphiques

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Redimensionner les graphiques

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Graphiques rotatifs

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Pour en savoir plus sur les fonctionnalités du package `graphics`, consultez la documentation [ici](https://ctan.org/pkg/graphics) et
[ici](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Vous pouvez également consulter la conversion gratuite [application Web](https://products.aspose.app/tex/conversion/latex/) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**