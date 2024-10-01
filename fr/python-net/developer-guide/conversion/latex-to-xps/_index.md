---
translation: true
template: /templates/_template-python-net.md
title: LaTeX vers XPS | Aspose.TeX pour Python
linktitle: LaTeX vers XPS
weight: 12
url: /python-net/latex-to-xps/
aliases: /python-net/autres-formats-cibles/
description: La solution API Aspose.TeX pour Python fournit une fonctionnalité de conversion pour convertir les fichiers LaTeX au format XPS. Voici quelques exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

Un autre format cible est [**XPS**](https://docs.aspose.com/page/net/what-is-xps-file/). Un fichier [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification) est essentiellement un package ZIP qui contient le contenu paginé d'un document, ainsi que les métadonnées nécessaires pour un affichage correct par des visualiseurs spécifiques (tels que Windows XPS Viewer) et une impression. Le package se compose de divers fichiers, dont certains sont binaires et contiennent des ressources telles que des images, des polices et des profils ICC. D'autres sont des fichiers XML dans des schémas spécifiques, y compris des fichiers contenant les données du document lui-même. Les données du document sont divisées en plusieurs fichiers, chaque fichier représentant une page individuelle du document. Ces fichiers se composent d'un seul élément de page et d'une arborescence d'éléments enfants, notamment *Canvas*, *Path* et *Glyphs*. L'élément *Canvas* est un élément de regroupement qui peut contenir d'autres *Canvas*, *Paths* et *Glyphs*, et il contrôle l'apparence de tous les éléments enfants en tant que groupe. Les éléments *Path* sont utilisés pour définir des chemins de graphiques vectoriels, tandis que les éléments *Glyphs* sont utilisés pour définir le contenu textuel. Les trois éléments ont des propriétés qui définissent divers aspects de l’apparence.

Il existe la bibliothèque [**Aspose.Page**](https://products.aspose.com/page/), qui propose une API pour manipuler les documents XPS et permet également la conversion de ces documents aux formats PDF et image raster.

## Conversion de LaTeX en XPS

Le processus de conversion de LaTeX en XPS est tout aussi simple, similaire à la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}python-net/latex-to-image/). Cependant, cela nécessite de définir [save_options](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/save_options/) sur une instance de la classe [XpsSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpssaveoptions/) (soit par défaut, soit explicitement) et de changer le périphérique en une instance de la classe [XpsDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.xps/xpsdevice/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Simplest.py" >}}

### Une autre façon d'écrire le fichier XPS de sortie principal

Il existe un constructeur alternatif disponible pour la classe *XpsDevice*, qui permet d'obtenir le fichier XPS résultant d'une manière différente.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToXps-Alternative.py" >}}

L’effet est le même que celui que nous obtenons [ici](/tex/{{lang.url-fragment}}python-net/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX vers XPS](https://products.aspose.app/tex/conversion/latex-to-xps), développée à l'aide de l'[API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**