---
translation: true
template: /templates/_template-java.md
title: LaTeX vers l'image | Java
linktitle: LaTeX en image
weight: 10
url: /java/latex-to-image/
keywords: latex à png, latex png, latex à image, image latex, latex à jpg, latex jpg, latex à jpeg, latex jpeg, latex à tiff, latex tiff, latex à bmp, latex bmp
description: Pour convertir TeX en formats d'image à l'aide de la solution API Aspose.TeX pour Java, consultez cet article qui décrit comment procéder.
lastmod: "2026-04-21"
---

{{<section overview>}}

**Aspose.TeX for Java** provides features for converting LaTeX files to a number of raster image formats.

## Comment convertir LaTeX en PNG

Examinons de plus près le code Java fournissant le moyen le plus simple de convertir LaTeX au format PNG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.java" >}}

Ainsi, la première chose que nous devons faire (parfois pas la toute première, comme nous le découvrirons plus tard) est de créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). La seule méthode statique qui fait cela est [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#consoleAppOptions-com.aspose.tex.TeXConfig-), alors ne nous soucions pas de la signification de son nom. La méthode prend l'[instance objectLaTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectLaTeX--) de la classe [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/), qui convient parfaitement à la conversion d'un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration demande au moteur Object TeX de charger le format Object LaTeX et d'être prêt à accepter le fichier LaTeX. Le format Object LaTeX n'est en fait que le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), sauf qu'il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour configurer les métriques de la page.

La première des options requises est [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) qui définit l'espace, ou la zone, où la sortie TeX sera écrite. [Ici](/tex/{{lang.url-fragment}}java/aspose-tex-output/) sont les détails sur le concept de répertoire de sortie dans **Aspose.TeX pour Java**. Dans cet exemple, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/), qui nous permet d'écrire la sortie dans le répertoire ou dossier spécifié.

La deuxième option est une instance de classe [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/saveoptions/) qui contrôlera la transformation du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) au format cible. Puisque nous convertissons LaTeX en PNG, c'est l'instance de classe [PngSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/pngsaveoptions/), qui nous permet de spécifier la résolution des images de sortie.

Ensuite, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/). Voulant convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) version du constructeur. Nous devons spécifier le chemin complet du fichier. Sinon, le moteur le cherchera dans le répertoire courant (qui est défini [ici](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) et ne le trouvera probablement pas. Néanmoins, nous pouvons omettre l'extension si notre fichier possède celle *.tex*. Le moteur l’ajoutera automatiquement. Le deuxième argument du constructeur est une instance de classe [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/device/). Puisque nous convertissons LaTeX en PNG, il s'agit d'une instance de classe [ImageDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/imagedevice/) (commune à tous les formats d'image pris en charge). Comme dernier argument, nous passons les options de conversion récemment préparées.

Il ne nous reste plus qu'à [exécuter](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#run--) le travail.

Que l'exécution ait réussi ou non, le premier résultat que nous verrons sera la sortie du terminal. En cas de succès, cela ressemble à ceci :

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Nous trouverons d'autres produits du moteur dans le dossier que nous avons spécifié comme répertoire de sortie. Il s'agira du fichier de transcription (.log) et, **Voila !**, du ou des fichiers image PNG de sortie principaux.

## Une autre façon d'écrire le(s) fichier(s) PNG de sortie principal

Il existe une autre façon d'obtenir des données d'image sous forme de tableau de tableaux d'octets, chaque tableau de la deuxième dimension représente les données d'image d'une page distincte.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.java" >}}

Le(s) fichier(s) *"page-n.png"* seront écrits dans n'importe quel chemin que nous spécifions. Contrairement à [Sortie PDF](/tex/{{lang.url-fragment}}java/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), ils dupliqueront les fichiers PNG de sortie écrits dans le répertoire de sortie.

## À propos des options de saisie

Dans le cas où notre fichier d'entrée principal nécessite des dépendances, par exemple des packages, qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, nous DEVONS définir l'option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) de la même manière que nous définissons [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--). option et placez les dépendances dans ce répertoire. Les dépendances peuvent être arbitrairement organisées en sous-répertoires. Dans le cas où nous avons nos propres fichiers à inclure tout au long du processus de composition, par exemple des fichiers graphiques externes, nous DEVONS également définir le [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont collectés. Nous pouvons également placer le fichier d'entrée principal quelque part dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()` (ou ne spécifier aucun chemin si le fichier d'entrée principal est à la racine). [Ici](/tex/{{lang.url-fragment}}java/aspose-tex-input/) sont les détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour Java** et les implémentations fournies.

D'autres options de travail TeX sont discutées [ici](/tex/{{lang.url-fragment}}java/other-options/).

**Vous pouvez également consulter la conversion gratuite LaTeX vers PNG [application Web](https://products.aspose.app/tex/conversion/latex-to-png) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**

Ci-dessous, nous discutons de la conversion de LaTeX vers d'autres formats d'image raster pris en charge. Nous n’entrerons pas dans les détails simplement parce qu’il n’y a pas de détails. La seule différence réside dans le type de la propriété [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) dans les options de conversion.

## Comment convertir LaTeX en JPG

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToJpeg.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers JPG [application Web](https://products.aspose.app/tex/conversion/latex-to-jpg) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**

## Comment convertir LaTeX en TIFF

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToTiff.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers TIFF [application Web](https://products.aspose.app/tex/conversion/latex-to-tiff) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**

## Comment convertir LaTeX en BMP

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-Conversion-LaTeXToBmp.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers BMP [application Web](https://products.aspose.app/tex/conversion/latex-to-bmp) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**


## Comment convertir LaTeX en SVG

Et encore un autre format cible pris en charge est [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** est un format d'image vectorielle basé sur XML permettant de définir des graphiques bidimensionnels, prenant en charge l'interactivité et l'animation.

Les images **SVG** sont définies dans un format graphique vectoriel et stockées dans des fichiers texte XML. Cela signifie que la taille des images **SVG** peut être redimensionnée sans perte de qualité, et que les fichiers **SVG** peuvent être recherchés, indexés, scriptés et compressés. Les fichiers texte XML peuvent être créés et modifiés avec des éditeurs de texte ou des éditeurs de graphiques vectoriels. Ils sont rendus par les navigateurs Web les plus utilisés.

Il existe également la bibliothèque [**Aspose.SVG**](https://products.aspose.com/svg/) qui possède diverses fonctionnalités basées sur le format **SVG**. Ceux-ci incluent la création, le chargement, l'édition et la conversion de documents **SVG**.

La conversion en SVG est aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}java/latex-to-image/), sauf qu'en plus des [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), nous devons changer le périphérique en une instance du [SvgDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/svgdevice/) classe.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.java" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers SVG [application Web](https://products.aspose.app/tex/conversion/latex-to-svg) construite sur la base de [Aspose.TeX pour .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**