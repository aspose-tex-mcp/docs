---
translation: true
template: /templates/_template-net.md
title: Graphiques LaTeX | Commande \includegraphics
linktitle: Graphiques LaTeX
weight: 18
url: /net/latex-graphics/
description: L'inclusion de graphiques dans TeX mérite d'être mentionnée. Quand on en parle, la première chose qui vient à l'esprit est la commande `\includegraphics`.
lastmod: 2026-10-19
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
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proportions
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
                                                           % at the point (10, 10) (coincides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Mise à l'échelle des graphiques

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Redimensionner les graphiques

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proportions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Graphiques rotatifs

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Pour en savoir plus sur les fonctionnalités du package `graphics`, consultez la documentation [ici](https://ctan.org/pkg/graphics) et
[ici](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Vous pouvez également consulter la conversion gratuite [application Web](https://products.aspose.app/tex/conversion/latex/) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**

## Syntaxe traditionnelle (`graphics`) vs moderne (`graphicx`)

Bien que ces deux extensions reposent sur les mêmes mécanismes fondamentaux, elles proposent des approches radicalement différentes pour la gestion des contenus dans LaTeX.

- L'extension `graphics` repose sur des commandes imbriquées et des arguments positionnels. Cela oblige l'utilisateur à encapsuler les macros d'insertion d'images dans des fonctions de transformation distinctes (par exemple, en plaçant `\includegraphics` à l'intérieur de `\scalebox`).

- L'extension `graphicx` introduit une interface « clé-valeur » claire et extensible, intégrée directement aux arguments optionnels de `\includegraphics`. Il est ainsi possible de définir plusieurs transformations au sein d'un bloc unique et lisible.

| **Opération** | **Extension traditionnelle `graphics`** | **Extension moderne `graphicx`** |
| :- | :- | :- |
| Insertion d'image simple | `\includegraphics{sample-image.png}` | `\includegraphics{sample-image.png}` |
| Mise à l'échelle uniforme | `\scalebox{0.5}{\includegraphics{sample-image.png}}` | `\includegraphics[scale=0.5]{sample-image.png}` |
| Mise à l'échelle non uniforme (X/Y indépendants) | `\scalebox{0.5}[1.5]{\includegraphics{sample-image.png}}` | (Nécessite une imbrication ou des extensions supplémentaires) |
| Redimensionnement selon une dimension | `\resizebox{10mm}{!}{\includegraphics{sample-image.png}}` | `\includegraphics[width=10mm]{sample-image.png}` |
| Redimensionnement indépendant des deux dimensions | `\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}}` | `\includegraphics[width=25mm, height=15mm]{sample-image.png}` |
| Rotation | `\rotatebox{25}{\includegraphics{sample-image.png}}` | `\includegraphics[angle=25]{sample-image.png}` |
| Découpage (viewport/rognage) | Nécessite des redéfinitions de la boîte englobante (bounding box) |`\includegraphics[viewport=10 10 280 220, clip]{sample-image.png}`|


### Avantages de l'approche par paires clé-valeur de `graphicx`

1. Combinaison native de plusieurs transformations :
Avec `graphicx`, vous pouvez appliquer simultanément une mise à l'échelle, une rotation et un découpage (clipping) au sein d'une seule commande, sans avoir à imbriquer des macros.

2. Préservation explicite des proportions :
En utilisant le paramètre `keepaspectratio=true` conjointement avec des contraintes explicites de largeur ou de hauteur, on évite toute déformation de l'image, sans avoir à calculer manuellement les facteurs d'échelle.

3. Meilleure maintenabilité dans le cadre d'une génération automatisée :
Lors de l'élaboration de programmes ou de scripts (tels que ceux reposant sur Aspose.TeX pour .NET) qui génèrent ou analysent dynamiquement des fichiers sources LaTeX, la construction de chaînes de propriétés structurées sous forme de paires clé-valeur est nettement moins sujette aux erreurs que l'analyse et l'insertion de macros imbriquées.