---
translation: true
template: /templates/_template-java.md
title: Autres options de gestion de TeX | Java
linktitle: Autres options
weight: 17
url: /java/other-options/
description: De conversion de la solution API Aspose.TeX pour Java permet de définir le mode d'interaction initial dans lequel le moteur démarre.
lastmod: "2024-09-27"
---

{{<section overview>}}


Chaque exemple crée des `TeXOptions` pour LaTeX et configure une option. Transmettez ces options à un `TeXJob`, fournissez une entrée LaTeX appropriée et définissez un répertoire de travail de sortie avant l’exécution. Importez `com.aspose.tex.TeXOptions`, `TeXConfig` et les classes utilisées dans l’exemple choisi : `Interaction`, `com.aspose.tex.rendering.XpsSaveOptions` ou `PdfSaveOptions`, et `java.util.Calendar`/`GregorianCalendar` pour l’exemple de date. Gérez ou déclarez les exceptions dans la méthode appelante. Les exemples de rastérisation et de sous-ensembles de polices utilisent `PdfSaveOptions` ; effectuez le rendu avec un `PdfDevice` compatible. Appliquez une licence conformément au [guide des licences](/tex/{{lang.url-fragment}}java/licensing/).

## Comment définir le mode d'interaction

Comme nous l'avons mentionné [ici](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX for Java** nous permet de définir le mode d'interaction initial dans lequel le moteur démarre. Voici comment nous procédons :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-InteractionMode.java" >}}

## Comment définir le nom du travail

Lorsque nous transmettons le fichier d'entrée principal comme nom de fichier, nous obtenons des fichiers de sortie portant le même nom, mais avec d'autres extensions. Le moteur TeX appelle le nom du fichier d'entrée *nom du travail* et l'utilise pour les fichiers de sortie, sauf dans les cas où des fichiers auxiliaires avec d'autres noms explicitement spécifiés sont écrits. Lorsque nous transmettons le fichier d'entrée principal en tant que [stream](/tex/{{lang.url-fragment}}java/other-ways-of-main-input/#providing-the-main-input-file-to-the-tex-engine-as-a-stream), le moteur TeX utilise le nom de travail par défaut, qui est *texput*.
Dans les deux cas, nous pouvons remplacer le nom du travail en attribuant l'option de conversion appropriée.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-JobName.java" >}}

## Comment "arrêter le temps"

LaTeX dispose d'une fonctionnalité permettant de générer automatiquement un titre à partir de certaines définitions du préambule. Ce titre contient normalement la date actuelle. Nous souhaiterons peut-être geler la date dans une valeur souhaitée. Voici comment procéder :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-DateTime.java" >}}

## Comment ignorer les paquets manquants

Un fichier LaTeX peut faire référence à des packages indisponibles dans la bibliothèque Aspose.TeX pour Java. Le moteur s’arrête normalement avec une erreur lorsqu’il tente de charger un tel package. Utilisez `ignoreMissingPackages(true)` pour ignorer les packages indisponibles. Cela ne fournit pas les commandes que ces packages définiraient ; l’entrée ne doit pas en dépendre.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-IgnoreMissingPackages.java" >}}

## Comment éviter de construire des ligatures

Normalement, le moteur TeX crée des ligatures pour certaines paires de caractères si la police fournit les données requises pour ce faire. Nous pouvons demander au moteur d’ignorer la construction de ligatures avec le code suivant :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-NoLigatures.java" >}}

## Comment répéter le travail

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) concernant les étiquettes et les références, il existe des cas où nous pouvons souhaiter exécuter deux fois le même travail. Voici comment procéder :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-Repeat.java" >}}

## Comment transformer des formules mathématiques en images raster

Parfois, nous pouvons avoir besoin d'avoir des formules mathématiques sous forme d'images raster plutôt que de les saisir dans des polices. L'option suivante peut servir à cet effet :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeFormulas.java" >}}

## Comment transformer des graphiques en images raster

Le moteur ObjectTeX nous permet d'inclure des fichiers graphiques aux formats raster (PNG et JPG) ainsi qu'aux formats PS(EPS) et XPS(OXPS). Les deux derniers formats contiennent généralement des éléments vectoriels et des textes. Pour les pixelliser et les inclure sous forme d'images solides, nous pouvons utiliser l'option suivante :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RasterizeIncludedGraphics.java" >}}

## Comment sous-ensembler des polices

Les sous-ensembles de polices limitent les polices incorporées aux glyphes utilisés dans le document. L’effet sur la taille de sortie dépend de la police et de son incorporation par le périphérique de sortie. Affectez les options d’enregistrement avant d’activer `subsetFonts(true)`, comme indiqué ci-dessous :

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-SubsetFonts.java" >}}