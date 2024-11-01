---
translation: true
template: /templates/_template-java.md
linktitle: Inclure des graphiques
title: LaTeX inclut des graphiques | Aspose.TeX pour Java
weight: 10
url: /java/latex-includegraphics/
keywords: includegraphics latex, latex includegraphic, insérer des images latex, latex graphx, insérer une image en latex, package includegraphics latex, draw io latex, latex includegraphics width, includegraphics width, figure scale latex
description: LaTeX inclut les graphiques, les transformations d'image, la fenêtre d'affichage, le recadrage et la différence entre les packages graphiques et Graphicx.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Introduction

Lorsque vous travaillez sur vos documents académiques et scientifiques, tels que des documents de recherche, des actes de conférences et des présentations académiques, vous souhaiterez peut-être occasionnellement inclure des figures graphiques.

D'une part, il peut s'agir de dessins, de tracés, d'histogrammes ou de quelque chose d'autre généralement appelé graphique vectoriel. Les systèmes LaTeX modernes (tels que « pdfTeX ») fournissent de nombreux outils pour créer de tels graphiques dans un document. Par exemple, les packages `pict2e`, `PGF(TikZ)` et `PGFplots`. Dans la plupart des cas, les figures elles-mêmes sont générées par un moteur TeX et incluses dans le fichier de sortie sous forme de séquences d'instructions graphiques vectorielles appropriées à un format de sortie spécifique.

D'un autre côté, vous pouvez avoir des images raster que vous souhaitez également inclure dans votre publication. Les systèmes LaTeX sont actuellement également capables de le faire, mais vous devez spécifier le chemin d'accès à votre fichier image dans votre fichier LaTeX en tant que paramètre d'une macro LaTeX.

Cet article couvre l'inclusion d'images raster dans des fichiers LaTeX à l'aide de la macro `\includegraphics` du package `graphics` (et du package `graphicx` qui l'accompagne).

## Quel package choisir, «graphics» ou «graphicx» ?

Les deux packages, `graphics` et `graphicx`, sont très similaires. La principale différence réside dans la syntaxe. Alors que le package `graphics` utilise un ensemble de macros distinctes pour appliquer des transformations à une image, le package `graphicx` utilise la notation `key=value` pour les paramètres de la macro `\includegraphics` afin de spécifier ces transformations. Nous donnerons des exemples de chaque cas d'utilisation pour les deux packages à la fois pour rendre la différence plus claire.

## Y compris le forfait choisi

Cela se fait avec la commande `\usepackage` de la même manière que pour tout autre package LaTeX :


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Spécification d'un pilote

Si votre système de composition n'est pas configuré pour utiliser, par exemple, « pdfTeX » par défaut, vous devez spécifier l'option appropriée qui forcera le package à utiliser le « pilote » requis :


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

Un « pilote » fait partie d'un package qui implémente l'interface entre les commandes du package et les primitives d'extension TeX de bas niveau dépendant du format. La prise en charge graphique LaTeX de **Aspose.TeX** est configurée pour utiliser son propre pilote, vous n'avez donc pas besoin de spécifier l'option du pilote.

## Macro LaTeX `\includegraphics`

Passons maintenant à l'exemple le plus simple. Il s’agit bien sûr d’inclure une image sans aucune transformation. Comme prévu, le code LaTeX utilisant les deux packages est le même :


```tex
\includegraphics{sample-image.png}
```

Cet exemple suppose que votre fichier image se trouve dans le même répertoire que le fichier LaTeX. Mais il existe plusieurs façons de spécifier un emplacement différent. Le code LaTeX sera à nouveau le même pour les deux packages :


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Une autre façon de spécifier le(s) emplacement(s) des fichiers graphiques consiste à définir une liste de chemins alternatifs à l'aide de la commande `\graphicspath` avant d'appeler `\includegraphics` :


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Transformations graphiques LaTeX

Les packages LaTeX `graphics` et `graphicx` fournissent un certain nombre de façons de manipuler le contenu.

### Figure à l'échelle LaTeX

Vous pouvez donc mettre à l'échelle les graphiques inclus (en fait, tout ce qui est décrit par le code TeX/LaTeX) comme suit :


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Redimensionner la figure LaTeX

C'est similaire à la mise à l'échelle, mais vous spécifiez la taille requise au lieu d'un ou plusieurs facteurs de mise à l'échelle :


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Faire pivoter la figure LaTeX

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Définition d'une fenêtre et d'un découpage

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Comme pour le package `graphicx`, les transformations peuvent être combinées, mais l'ordre est important.
Pour en savoir plus sur les fonctionnalités du package `graphics`, reportez-vous à la [page du package sur CTAN](https://ctan.org/pkg/graphics) et
la [documentation du paquet](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### Application Web gratuite LaTeX Include Graphics

Si vous ne souhaitez pas travailler avec le package latex includegraphics par programme, vous pouvez également consulter l'application Web gratuite [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/). 

L'application vous permet de sélectionner plusieurs images et d'ajuster visuellement leurs transformations. Il génère également du code source LaTeX à l'aide du package `graphicx` et le restitue en affichant le résultat sur la page.

### Fonctionnalité de rendu de figures LaTeX dans la bibliothèque Aspose.TeX

La bibliothèque **Aspose.TeX** fournit un moyen de créer des figures raster et SVG que vous pouvez utiliser dans vos publications en dehors du contexte TeX/LaTeX. Par exemple, sur une page Web. C'est ce qu'on appelle le **Rendu de figures LaTeX**. En bref, cette partie de l'API vous permet de restituer un fragment du code source LaTeX quelle que soit la mise en page. Pour plus de détails, reportez-vous à cet [article](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

L'article sur [y compris les packages LaTeX externes](/tex/{{lang.url-fragment}}java/external-latex-packages/) peut également vous donner un indice sur la façon de créer des figures à partir de tracés LaTeX.