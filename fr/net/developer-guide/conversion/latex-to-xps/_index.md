---
translation: true
template: /templates/_template-net.md
title: LaTeX vers XPS | .NET
linktitle: LaTeX vers XPS
weight: 12
url: /net/latex-to-xps/
description: De conversion de la solution API Aspose.TeX pour .NET permet de convertir les fichiers LaTeX au format XPS.
lastmod: "2026-11-02"
---

{{<section overview>}}


Un autre format cible est [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un fichier **XPS** est physiquement un package ZIP qui contient le contenu paginé d'un document, ainsi que les métadonnées requises pour un affichage correct par des visualiseurs spécifiques (tels que Windows XPS Viewer) et une impression. Toutes les données d'un package sont représentées par des fichiers. Certains d'entre eux sont binaires et contiennent des ressources telles que des images, des polices et des profils ICC. D'autres sont des fichiers XML dans divers schémas spécifiques. Ces derniers incluent des fichiers contenant les données du document elles-mêmes. Les données du document se composent d'un ensemble de fichiers - chaque fichier contient des données pour une page individuelle du document. Ces fichiers se composent d'un seul élément de page et d'une arborescence d'éléments enfants - *Canvas*, *Path* et *Glyphs*. *Canvas* est un élément de regroupement qui peut contenir d'autres *Canvas*, *Paths* et *Glyphs*. Il sert à contrôler l’apparence de tous les éléments enfants en tant que groupe. Les éléments *Path* sont utilisés pour définir des chemins de graphiques vectoriels. Et les éléments *Glyphs* sont utilisés pour définir le contenu textuel. Les trois éléments ont des propriétés permettant de définir divers aspects de l’apparence.

Il existe la bibliothèque [**Aspose.Page**](https://products.aspose.com/page/) qui fournit une API pour manipuler les documents XPS, ainsi que pour les convertir aux formats PDF et d'image raster.

## Comment convertir LaTeX en XPS

La conversion LaTeX en XPS est tout aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}net/latex-to-image/), sauf que [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/saveoptions/) DOIT être défini sur une instance de classe [XpsSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpssaveoptions/) (par défaut ou explicitement) , et le périphérique DOIT être remplacé par une instance de la classe [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/).

**Exemple de conversion le plus simple**

L'exemple ci-dessous montre comment convertir un fichier LaTeX en XPS en quelques étapes :

1. Créez `TeXOptions` pour le format ObjectLaTeX avec `TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX)`.
2. Indiquez le répertoire de travail de sortie, par exemple un `OutputFileSystemDirectory`.
3. Affectez à `SaveOptions` une instance de `XpsSaveOptions`.
4. Exécutez un `TeXJob` pour le fichier source `.tex` avec un `XpsDevice`. Le fichier XPS est écrit dans le répertoire de travail de sortie.

Ce code illustre la méthode la plus directe pour générer un fichier XPS à partir de LaTeX.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Simplest.cs" >}}

### Une autre façon d'écrire le fichier XPS de sortie principal

Il existe un autre constructeur de la classe [XpsDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/xpsdevice/), qui nous permet d'obtenir le fichier XPS résultant d'une manière alternative.

**Exemple de conversion alternatif**

Cet extrait de code illustre l'utilisation du constructeur `XpsDevice` qui accepte un `Stream`. Les étapes sont les suivantes :

1. Ouvrez le flux dans lequel écrire le document XPS (ici, un flux de fichier ; un `MemoryStream` fonctionne de la même manière).
2. Créez `TeXOptions`, indiquez le répertoire de travail de sortie et affectez à `SaveOptions` une instance de `XpsSaveOptions`, comme dans l'exemple précédent.
3. Exécutez un `TeXJob` avec un `XpsDevice` créé avec le flux. Le document XPS est écrit dans le flux ; les autres fichiers de sortie, comme la transcription, sont toujours écrits dans le répertoire de travail de sortie.

Cette approche est utile lorsque vous devez écrire le document XPS dans un flux de votre choix, par exemple pour le conserver en mémoire ou l'envoyer sur un réseau.

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToXPS-Alternative.cs" >}}

L’effet est le même que celui que nous obtenons [ici](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file).

**Vous pouvez également consulter la conversion gratuite LaTeX vers XPS [application Web](https://products.aspose.app/tex/conversion/latex-to-xps) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**
