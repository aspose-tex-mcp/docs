---
translation: true
template: /templates/_template-java.md
title: LaTeX vers XPS | Java
linktitle: LaTeX vers XPS
weight: 12
url: /java/latex-to-xps/
description: De conversion de la solution API Aspose.TeX pour Java vous permet de convertir des fichiers LaTeX au format XPS. Apprenez les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}


Un autre format cible est [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un fichier **XPS** est physiquement un package ZIP qui contient le contenu paginé d'un document, ainsi que les métadonnées requises pour un affichage correct par des visualiseurs spécifiques (tels que Windows XPS Viewer) et une impression. Toutes les données d'un package sont organisées sous forme de fichiers dans des répertoires. Certains d'entre eux contiennent des ressources telles que des images, des polices et des profils ICC. D'autres sont des fichiers XML dans divers schémas spécifiques. Ces derniers incluent des fichiers contenant les données du document elles-mêmes. Les données du document sont un ensemble de fichiers - chaque fichier contient des données pour une page individuelle du document. Ces fichiers se composent d'un seul élément de page et d'une arborescence d'éléments enfants - *Canvas*, *Path* et *Glyphs*. *Canvas* est un élément de regroupement qui peut contenir d'autres *Canvas*, *Paths* et *Glyphs*. Son objectif est de contrôler l'apparence de tous les éléments enfants en tant que groupe. Les éléments *Path* sont utilisés pour définir des chemins de graphiques vectoriels. Et les éléments *Glyphs* sont utilisés pour définir le contenu du texte. Les trois éléments ont des propriétés permettant de définir divers aspects de l’apparence.

Il existe la bibliothèque [**Aspose.Page**](https://products.aspose.com/page/) qui fournit une API pour manipuler les documents XPS, ainsi que pour les convertir aux formats PDF et d'image raster.

## Comment convertir LaTeX en XPS

La conversion en XPS est aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}java/latex-to-image/), sauf qu'en plus des [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--), nous devons utiliser une instance de la classe [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) .

Définissez `inputFile` sur le chemin complet de votre fichier LaTeX, par exemple `hello-world.ltx`, et `outputDirectory` sur un dossier de sortie existant. Importez les classes de `com.aspose.tex` et `com.aspose.tex.rendering` utilisées dans l'extrait. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence comme décrit dans le [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d'évaluation. L'exemple utilise un traitement non interactif et ferme ses ressources de sortie. Pour le fichier d'entrée autonome `hello-world.ltx`, la sortie par défaut est `hello-world.xps`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Une autre façon d'écrire le fichier XPS de sortie principal

Il existe un autre constructeur de la classe [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), qui nous permet d'obtenir le fichier XPS résultant d'une manière alternative.

Utilisez les mêmes valeurs de `inputFile` et `outputDirectory` que ci-dessus. Définissez `xpsFile` comme un `java.nio.file.Path`, par exemple `Paths.get(outputDirectory, "any-name.xps")`. En plus des classes Aspose.TeX, importez `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` et `java.nio.file.Paths`. Le flux contrôle la destination du fichier XPS ; les fichiers auxiliaires sont toujours écrits dans `outputDirectory`.

{{< gist "aspose-com-gists" "1d90376049c44b97cffb85e4ac382a5b" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

L'effet est le même que celui que nous obtenons [ici](/tex/{{lang.url-fragment}}java/latex-to-pdf/#une-autre-façon-décrire-le-fichier-pdf-de-sortie-principal).

**Vous pouvez également consulter la conversion gratuite LaTeX vers XPS [application Web](https://products.aspose.app/tex/conversion/latex-to-xps) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**