---
translation: true
template: /templates/_template-net.md
title: Autres options de gestion de TeX | .NET
linktitle: Autres options
weight: 17
url: /net/other-options/
description: De conversion de la solution API Aspose.TeX pour .NET permet de définir le mode d'interaction initial dans lequel le moteur démarre.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Comment définir le mode d'interaction

Comme nous l'avons mentionné [ici](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX for .NET** nous permet de définir le mode d'interaction initial dans lequel le moteur démarre. Voici comment nous procédons :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-InteractionMode.cs" >}}

## Comment définir le nom du travail

Lorsque nous transmettons le fichier d'entrée principal comme nom de fichier, nous obtenons des fichiers de sortie portant le même nom, mais avec d'autres extensions. Le moteur TeX appelle le nom du fichier d'entrée *nom du travail* et l'utilise pour les fichiers de sortie, sauf dans les cas où des fichiers auxiliaires avec d'autres noms explicitement spécifiés sont écrits. Lorsque nous transmettons le fichier d'entrée principal en tant que [stream](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), le moteur TeX utilise le nom de travail par défaut, qui est *texput*.
Dans les deux cas, nous pouvons remplacer le nom du travail en attribuant l'option de conversion appropriée.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-JobName.cs" >}}

## Comment "arrêter le temps"

LaTeX dispose d'une fonctionnalité permettant de générer automatiquement un titre à partir de certaines définitions du préambule. Ce titre contient normalement la date actuelle. Nous souhaiterons peut-être geler la date dans une valeur souhaitée. Voici comment procéder :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-DateTime.cs" >}}

## Comment ignorer les paquets manquants

Nous souhaiterons peut-être convertir un fichier LaTeX faisant référence à certains packages qui ne sont pas pris en charge par la bibliothèque Aspose.TeX pour .NET. Dans ce cas, le moteur TeX s'arrêtera avec une erreur lors de la tentative de chargement d'un tel package. Pour éviter cela, nous pouvons utiliser l'option suivante :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-IgnoreMissingPackages.cs" >}}

## Comment éviter de construire des ligatures

Normalement, le moteur TeX crée des ligatures pour certaines paires de caractères si la police fournit les données requises pour ce faire. Nous pouvons demander au moteur d’ignorer la construction de ligatures avec le code suivant :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-NoLigatures.cs" >}}

## Comment répéter le travail

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) concernant les étiquettes et les références, il existe des cas où nous souhaiterions exécuter deux fois le même travail. Voici comment procéder :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-Repeat.cs" >}}

## Comment transformer des formules mathématiques en images raster

Parfois, nous pouvons avoir besoin d'avoir des formules mathématiques sous forme d'images raster plutôt que de les saisir dans des polices. L'option suivante peut servir à cet effet :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeFormulas.cs" >}}

## Comment transformer des graphiques en images raster

Le moteur ObjectTeX nous permet d'inclure des fichiers graphiques aux formats raster (PNG et JPG) ainsi qu'aux formats PS(EPS) et XPS(OXPS). Les deux derniers formats contiennent généralement des éléments vectoriels et des textes. Pour les pixelliser et les inclure sous forme d'images solides, nous pouvons utiliser l'option suivante :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RasterizeIncludedGraphics.cs" >}}

## Comment sous-ensembler des polices

Si nous souhaitons réduire la taille du fichier de sortie, nous pouvons recourir au sous-réglage des polices, ce qui signifie que les polices du document de sortie ne contiendront que des données sur les glyphes utilisés dans le document. Voici comment nous pouvons résoudre ce problème :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-SubsetFonts.cs" >}}
