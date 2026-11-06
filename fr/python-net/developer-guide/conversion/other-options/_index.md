---
translation: true
template: /templates/_template-python-net.md
title: Autres options de gestion de TeX | Python
linktitle: Autres options
weight: 17
url: /python-net/other-options/
description: Aspose.TeX pour Python inclut une fonctionnalité de conversion qui vous permet de définir le mode d'interaction initial dans lequel le moteur démarre.
lastmod: "2024-09-27"
---

{{<section overview>}}

Les exemples produisent des fichiers XPS. Appliquez d’abord une [licence](/tex/{{lang.url-fragment}}python-net/licensing/) et définissez `ASPOSE_TEX_OUTPUT_DIR` sur le dossier de sortie (par défaut : `output`). Utilisez un dossier distinct pour chaque exemple afin de conserver tous les résultats.

## Définir le mode d'interaction

Comme mentionné [dans le paragraphe sur l'interaction TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX pour Python** offre la possibilité de définir le mode d'interaction initial dans lequel le moteur démarre. Voici un exemple de la façon dont cela peut être fait :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Définition du nom du travail

Lorsque le fichier d'entrée principal est fourni comme nom de fichier, les fichiers de sortie résultants auront le même nom mais avec des extensions différentes. Le moteur TeX fait référence au nom du fichier d'entrée comme *nom du travail* et l'utilise pour les fichiers de sortie. L'exception concerne les fichiers auxiliaires dont les noms de fichiers sont explicitement spécifiés. Cependant, lorsque le fichier d'entrée principal est passé en tant que [stream](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream), le moteur TeX utilise le nom de travail par défaut, qui est *texput*. Dans les deux scénarios, il est possible de remplacer le nom du travail en attribuant l'option de conversion appropriée.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## "Arrêter le temps"

Pour générer automatiquement un titre à partir de certaines définitions du préambule, LaTeX propose une fonctionnalité qui inclut généralement la date actuelle. Cependant, il peut y avoir des cas où nous souhaitons fixer la date à une valeur spécifique. Voici une méthode pour y parvenir :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Ignorer les paquets manquants

Si nous disposons d'un fichier LaTeX qui inclut des références à des packages qui ne sont pas pris en charge par la bibliothèque **Aspose.TeX for Python**, le moteur TeX rencontrera une erreur et s'arrêtera lors de la tentative de chargement de ces packages. Pour éviter cela, nous pouvons utiliser l'option suivante :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## Comment éviter de construire des ligatures

Par défaut, le moteur TeX construit des ligatures pour des paires de caractères spécifiques si la police contient les données nécessaires. Cependant, nous pouvons demander au moteur de contourner la construction de ligatures en utilisant le code suivant :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## Répéter le travail

Comme mentionné [dans le paragraphe du fichier d'entrée LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file), les étiquettes et les références, il existe des situations dans lesquelles nous pouvons avoir besoin d'exécuter le même travail deux fois. Voici une méthode pour y parvenir :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Transformer des formules mathématiques en images raster

S'il est nécessaire de convertir des formules mathématiques en images raster au lieu de les restituer avec des polices, l'option suivante peut être utilisée à cette fin :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Transformer des graphiques en images raster

Le moteur ObjectTeX offre la possibilité d'inclure des fichiers graphiques dans des formats raster tels que PNG et JPG, ainsi que dans les formats PS (EPS) et XPS (OXPS). Ces deux derniers formats contiennent généralement des éléments vectoriels et du texte. Si nous voulons les pixelliser et les inclure sous forme d'images solides, nous pouvons utiliser l'option suivante :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

L’exemple graphique lit `Typesetting/triangle.eps` sous `ASPOSE_TEX_INPUT_DIR` (par défaut : `input`). Conservez ce sous-dossier lors de la préparation des ressources.

## Polices de sous-ensemble

Si nous souhaitons réduire la taille du fichier de sortie, nous pouvons utiliser un sous-réglage de polices, ce qui implique que les polices du document résultant n'incluront pas de données pour les glyphes qui ne sont pas présents dans le document. Voici une solution pour y parvenir :

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}