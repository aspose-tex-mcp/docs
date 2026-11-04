---
translation: true
template: /templates/_template-net.md
title: LaTeX vers l'image | .NET
linktitle: LaTeX en image
weight: 10
url: /net/latex-to-image/
keywords: latex à png, latex png, latex à image, image latex, latex à jpg, latex jpg, latex à jpeg, latex jpeg, latex à tiff, latex tiff, latex à bmp, latex bmp
description: Pour convertir TeX en formats d'image à l'aide d'Aspose.TeX pour .NET, lisez cet article pour voir comment procéder et avec des exemples de code.
lastmod: "2026-11-04"
---

{{<section overview>}}

**Aspose.TeX pour .NET** nous permet de convertir des fichiers LaTeX vers un certain nombre de formats d'images raster.

## Comment convertir LaTeX en PNG

Examinons en détail le code en C# fournissant le moyen le plus simple de convertir LaTeX au format PNG.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Simplest.cs" >}}

Ainsi, la première chose que nous devons faire (enfin, parfois pas la toute première) est de créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). La seule méthode statique qui fait cela est [ConsoleAppOptions()](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions/), alors ne soyons pas intrigués par la signification de son nom. La méthode prend l'[instance ObjectLaTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectlatex/) de la classe [TeXConfig](https://reference.aspose.com/tex/net/aspose.tex/texconfig/), qui convient parfaitement à la conversion d'un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration indique au moteur Object TeX de charger le format Object LaTeX et d'être prêt à accepter le fichier LaTeX. Le format Object LaTeX n'est en fait que le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), sauf qu'il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour configurer les métriques de la page.

La première des options requises est [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) qui définit l'espace, ou la zone, où la sortie TeX sera écrite. [Ici](/tex/{{lang.url-fragment}}net/aspose-tex-output/) sont les détails sur le concept de répertoire de sortie dans **Aspose.TeX pour .NET**. Dans cet exemple, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), qui nous permet d'écrire la sortie dans le répertoire ou dossier spécifié.

La deuxième option est une instance de classe [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) qui contrôlera la transformation du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) au format cible. Puisque nous convertissons LaTeX en PNG, c'est l'instance de classe [PngSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/pngsaveoptions/), qui nous permet de spécifier la résolution des images de sortie.

Ensuite, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/net/aspose.tex/texjob/). Voulant convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) version du constructeur. Nous devons spécifier le chemin complet du fichier. Sinon, le moteur le recherchera dans le répertoire courant (qui est [CurrentDirectory](https://learn.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory?view=net-10.0)) et ne le trouvera probablement pas. Néanmoins, l'extension *.tex* peut être omise. Le moteur l’ajoutera automatiquement. Le deuxième argument du constructeur est une instance de classe [Device](https://reference.aspose.com/tex/net/aspose.tex.presentation/device/). Puisque nous convertissons LaTeX en PNG, il s'agit d'une instance de classe [ImageDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.image/imagedevice/), et ceci est commun à tous les formats d'image pris en charge. Comme dernier argument, nous passons les options de conversion récemment préparées.

Il ne reste plus qu'à [exécuter](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) le travail.

Que l'exécution ait réussi ou non, le premier résultat que nous verrons sera la sortie du terminal. Si l'exécution a réussi, cela ressemblera à ceci :


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

Nous retrouverons d'autres "fruits" du travail du moteur dans le dossier que nous avons spécifié comme répertoire de sortie. Il s'agira du fichier de transcription et, **le voici !**, du ou des fichiers image PNG de sortie principaux.

## Une autre façon d'écrire le(s) fichier(s) PNG de sortie principal

Il existe une autre façon d'obtenir des données d'image sous forme de tableau de tableaux d'octets, chaque tableau de la deuxième dimension représente les données d'image d'une page distincte.

**Exemple de conversion alternatif**

L'extrait de code C# suivant montre une autre façon d'obtenir la sortie PNG : le périphérique conserve les données d'image en mémoire sous forme de tableaux d'octets au lieu de les écrire dans le système de fichiers. Cette approche est utile lorsque vous avez besoin des octets PNG générés pour un traitement ultérieur, par exemple pour les envoyer sur un réseau, les stocker dans une base de données ou effectuer des transformations supplémentaires avant l'enregistrement.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPNG-Alternative.cs" >}}

Le ou les fichiers *"page-n.png"* seront écrits dans le chemin que nous indiquons. Comme l'option `DeviceWritesImages` est définie sur `false`, le périphérique lui-même n'écrit pas de fichiers PNG dans le répertoire de sortie.

## À propos des options de saisie

Dans le cas où notre fichier d'entrée principal nécessite des dépendances, par exemple des packages, qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, nous DEVONS définir l'option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) de la même manière que nous définissons [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). option et placez les dépendances dans ce répertoire. Les dépendances peuvent être arbitrairement organisées en sous-répertoires. Dans le cas où nous avons nos propres fichiers à inclure tout au long du processus de composition, par exemple des fichiers graphiques externes, nous DEVONS également définir le [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont collectés. Nous pouvons également placer le fichier d'entrée principal quelque part dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()` (ou ne spécifier aucun chemin si le fichier d'entrée principal est à la racine). [Ici](/tex/{{lang.url-fragment}}net/aspose-tex-input/) sont les détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour .NET** et les implémentations fournies.

D'autres options de travail TeX sont discutées [ici](/tex/{{lang.url-fragment}}net/other-options/).

**Vous pouvez également consulter la conversion gratuite LaTeX vers PNG [application Web](https://products.aspose.app/tex/conversion/latex-to-png) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**

Ci-dessous, nous discutons de la conversion de LaTeX vers d'autres formats d'image raster pris en charge sans entrer dans les détails car il n'y a en réalité aucun détail. La seule différence réside dans le type de la propriété [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) dans les options de conversion.

## Comment convertir LaTeX en JPG

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToJPEG.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers JPG [application Web](https://products.aspose.app/tex/conversion/latex-to-jpg) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**

## Comment convertir LaTeX en TIFF

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToTIFF.cs" >}}

{{% alert color="primary" %}}
Le package `Aspose.TeX.Drawing` ne peut pas encore enregistrer de fichiers TIFF multipages : lorsque `TiffSaveOptions.Multipage` vaut `true`, le fichier TIFF ne contient que la première page. Définissez `Multipage` sur `false` pour obtenir une image TIFF distincte par page. Voir [Linux, macOS et Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#known-limitations).
{{% /alert %}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers TIFF [application Web](https://products.aspose.app/tex/conversion/latex-to-tiff) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**

## Comment convertir LaTeX en BMP

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToBMP.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers BMP [application Web](https://products.aspose.app/tex/conversion/latex-to-bmp) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**

## Comment convertir LaTeX en SVG

Et encore un autre format cible pris en charge est [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** est un format d'image vectorielle basé sur XML permettant de définir des graphiques bidimensionnels, prenant en charge l'interactivité et l'animation.

Les images **SVG** sont définies dans un format graphique vectoriel et stockées dans des fichiers texte XML. Les images **SVG** peuvent ainsi être redimensionnées sans perte de qualité, et les fichiers **SVG** peuvent être recherchés, indexés, scriptés et compressés. Les fichiers texte XML peuvent être créés et modifiés avec des éditeurs de texte ou des éditeurs de graphiques vectoriels, et sont rendus par les navigateurs Web les plus utilisés.

Il existe la bibliothèque [**Aspose.SVG**](https://products.aspose.com/svg/) qui fournit diverses fonctionnalités liées à **SVG**. Ceux-ci incluent la création, le chargement, l'édition et la conversion de documents **SVG**.

La conversion LaTeX en SVG est également aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}net/latex-to-image/), sauf que les [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DOIVENT être définies sur une instance de classe [SvgSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgsaveoptions/), et le périphérique DOIT être remplacé par une instance de la classe [SvgDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToSVG-Simplest.cs" >}}

**Vous pouvez également consulter la conversion gratuite LaTeX vers SVG [application Web](https://products.aspose.app/tex/conversion/latex-to-svg) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**
