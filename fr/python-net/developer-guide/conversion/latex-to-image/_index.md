---
translation: true
template: /templates/_template-python-net.md
title: LaTeX vers l'image | Aspose.TeX pour Python
linktitle: LaTeX en image
weight: 10
url: /python-net/latex-to-image/
aliases:
- /python-net/latex-to-png/
- /python-net/latex-to-svg/
keywords: latex à png, latex png, latex à image, image latex, latex à jpg, latex jpg, latex à jpeg, latex jpeg, latex à tiff, latex tiff, latex à bmp, latex bmp
description: Pour convertir TeX en formats d'image à l'aide de la solution API Aspose.TeX pour Python, lisez cet article pour voir qui décrit comment procéder ainsi que les exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

**Aspose.TeX pour Python** nous offre la possibilité de convertir des fichiers LaTeX en différents formats d'images raster.

## Conversion de LaTeX en PNG

Examinons maintenant en profondeur le code Python qui offre l'approche la plus simple pour convertir LaTeX au format PNG.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Simplest.py" >}}

Pour commencer, nous devons créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) en utilisant la méthode [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig). Ne vous inquiétez pas du nom, c'est juste la méthode statique qui crée l'instance. Cette méthode prend l'instance [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) de la classe [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), ce qui est parfait pour convertir un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration configure le moteur Object TeX pour charger le format Object LaTeX et être prêt à traiter le fichier LaTeX. Le format Object LaTeX est essentiellement le même que le [format LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), mais il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour définir les métriques de la page.

La première des options nécessaires est [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), qui spécifie l'emplacement où la sortie TeX sera enregistrée. Si vous êtes intéressé, vous pouvez en savoir plus sur le concept du [répertoire de sortie dans **Aspose.TeX pour Python**](/tex/{{lang.url-fragment}}python-net/aspose-tex-output/). Dans cet exemple particulier, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/) pour écrire la sortie dans un répertoire ou un dossier spécifique.

La deuxième option est une instance de la classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), qui est chargée de gérer la conversion du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) vers le format souhaité. Dans ce cas, puisque nous convertissons LaTeX en PNG, nous utilisons l'instance de classe [PngSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/pngsaveoptions/), qui nous permet de spécifier la résolution des images de sortie.

Ensuite, nous créons une instance de la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/). Dans ce cas, puisque nous souhaitons convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette version du constructeur](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions). Nous devons fournir le chemin complet du fichier, sinon le moteur le recherchera dans le répertoire courant (qui est le répertoire de travail du script) et risque de ne pas le trouver. Cependant, l'extension « .tex » peut être omise car le moteur l'ajoutera automatiquement. Le deuxième argument du constructeur est une instance de la classe [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Puisque nous convertissons LaTeX en PNG, il s'agit d'une instance de classe [ImageDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.image/imagedevice/), commune à tous les formats d'image pris en charge. Enfin, nous transmettons les options de conversion préparées comme dernier argument.

Il ne reste plus qu'à [exécuter](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) le travail.

Une fois le travail exécuté, quel que soit son succès ou son échec, la première sortie que nous rencontrerons est la sortie du terminal. En cas d'exécution réussie, le résultat ressemblera à ce qui suit :

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

Les résultats du travail du moteur peuvent être trouvés dans le répertoire de sortie que nous avons spécifié. Cela inclura le fichier de transcription et, plus important encore, le(s) fichier(s) image PNG de sortie principal.

## Une autre façon d'écrire le(s) fichier(s) PNG de sortie principal

Il existe une méthode alternative pour obtenir des données d'image sous la forme d'un tableau de tableaux d'octets, où chaque tableau de la deuxième dimension représente les données d'image d'une page distincte.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPng-Alternative.py" >}}

Le(s) fichier(s) "page-n.png" peuvent être écrits dans n'importe quel chemin spécifié. Contrairement à la [Sortie PDF](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file), ces fichiers PNG dupliqueront les fichiers PNG de sortie écrits dans le répertoire de sortie.

## Concernant les options de saisie

Si notre fichier d'entrée principal nécessite des dépendances, telles que des packages qui ne sont pas inclus dans le système LaTeX de base ou des packages pris en charge, nous devons définir l'option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de la même manière que nous définissons l'option *output_working_directory* et placez les dépendances dans ce répertoire. Les dépendances peuvent être organisées en sous-répertoires selon les besoins. Si nous devons inclure nos fichiers dans le processus de composition, tels que des fichiers graphiques externes, nous devons également définir le [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) sur l'emplacement où ces fichiers sont stockés. Nous pouvons également placer le fichier d'entrée principal dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()`, ou ne spécifier aucun chemin si le fichier d'entrée principal se trouve dans le répertoire racine. Il y a également plus de détails sur le [concept de répertoire d'entrée](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/) dans **Aspose.TeX** et les implémentations fournies décrites.

Découvrez également les [autres options de travail TeX ici](/tex/{{lang.url-fragment}}python-net/other-options/).

**Vous pouvez également explorer l'[application Web](https://products.aspose.app/tex/conversion/latex-to-png) gratuite pour la conversion LaTeX en PNG, développée à l'aide de l'[API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**

Ci-dessous, nous expliquerons brièvement la conversion de LaTeX vers d'autres formats d'images raster pris en charge, sans trop entrer dans les détails car il n'y a pas de différences significatives. La seule variation réside dans le type de la propriété [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) dans les options de conversion.

## Conversion de LaTeX en JPG

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToJpeg.py" >}}

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX en JPG](https://products.aspose.app/tex/conversion/latex-to-jpg), développée à l'aide de [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**

## Conversion de LaTeX en TIFF

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToTiff.py" >}}

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX vers TIFF](https://products.aspose.app/tex/conversion/latex-to-tiff), développée à l'aide de [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**

## Conversion de LaTeX en BMP

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToBmp.py" >}}

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX en BMP](https://products.aspose.app/tex/conversion/latex-to-bmp), développée à l'aide de [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**

## Conversion de LaTeX en SVG

Un autre format cible pris en charge est [**SVG**](https://en.wikipedia.org/wiki/SVG). **Scalable Vector Graphics (SVG)** est un format d'image vectorielle basé sur XML utilisé pour définir des graphiques bidimensionnels. Il prend en charge l'interactivité et l'animation.

Les images **SVG** sont stockées dans des fichiers texte XML et définies dans un format graphique vectoriel. Cela signifie que la taille des images **SVG** peut être redimensionnée sans perte de qualité, et que les fichiers **SVG** eux-mêmes peuvent être recherchés, indexés, scriptés et compressés. Les fichiers texte XML peuvent être créés et modifiés à l'aide d'éditeurs de texte ou d'éditeurs de graphiques vectoriels, et ils peuvent être rendus par les navigateurs Web les plus couramment utilisés.

L'API [**Aspose.SVG**](https://products.aspose.com/svg/) offre une gamme de fonctionnalités pour travailler avec **SVG**, telles que la création, le chargement, la modification et la conversion de documents **SVG**.

La conversion de LaTeX en SVG est tout aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/), la seule différence étant que les [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) doivent être définies sur une instance de la classe [SvgSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgsaveoptions/) et que Le périphérique doit être remplacé par une instance de la classe [SvgDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.svg/svgdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToSvg-Simplest.py" >}}

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX en SVG](https://products.aspose.app/tex/conversion/latex-to-svg), développée à l'aide de [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**