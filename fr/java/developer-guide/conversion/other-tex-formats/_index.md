---
translation: true
template: /templates/_template-java.md
title: Autres formats de sortie de conversion TeX | Java
linktitle: Autres formats TeX
weight: 18
url: /java/other-tex-formats/
description: De conversion de la solution API Aspose.TeX pour Java permet de convertir des fichiers LaTeX et vos propres fichiers TeX personnalisés.
lastmod: "2026-04-21"
---

{{<section overview>}}

Il est très peu probable que vous souhaitiez actuellement convertir un fichier TeX écrit dans un autre format que LaTeX. Mais cela est possible si vous étudiez le langage TeX et/ou ses composants internes pour une raison quelconque. Quoi qu'il en soit, **Aspose.TeX for Java** vous permet de convertir des fichiers écrits au format Plain TeX. Il vous permet également de créer des formats personnalisés et de composer des documents conçus dans ces formats.

Nous commencerons par créer un format personnalisé.

## Création d'un format personnalisé

Rappelons que le fichier de format est un dump binaire de l'état interne du moteur TeX.

Définissez `inputDirectory` sur un dossier contenant `customtex.tex` et ses dépendances, et `outputDirectory` sur un dossier de sortie existant. Le fichier source du format doit se terminer par `\dump` ; cet exemple y crée `customtex.fmt`. Importez les classes Aspose.TeX utilisées dans les exemples et, pour la composition, `com.aspose.tex.rendering.XpsDevice`, `java.io.ByteArrayInputStream` et `java.nio.charset.StandardCharsets`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence conformément au [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d’évaluation.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-CreateCustomTeXFormat.java" >}}

Comme vous pouvez le voir, le code est similaire au code de conversion d'un fichier TeX. Mais il existe quelques différences.

Tout d'abord, nous utilisons ici la configuration du travail [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) . Il s'agit d'une configuration spéciale qui laisse l'état du moteur « vierge », c'est-à-dire que les paramètres internes ont leurs valeurs par défaut et que l'ensemble des séquences de contrôle coïncide avec l'ensemble des primitives. Dans notre exemple, l'ensemble des primitives est étendu dans le sens mentionné [ici](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Ensuite, nous configurons les répertoires de travail d’entrée et de sortie comme d’habitude. Le répertoire de travail d'entrée doit contenir le fichier source du format principal et toutes ses dépendances.

Et la deuxième différence clé réside dans la manière dont nous gérons le travail. Cette fois, nous utilisons la méthode statique [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-)  qui, avec les options, prend le nom du fichier source principal, qui doit être le même que le nom du format.

## Composition d'un fichier TeX dans votre format personnalisé

Maintenant que nous avons notre propre format TeX, nous souhaitons composer un fichier TeX écrit dans ce format. Voici le code :

Définissez `formatDirectory` sur le dossier contenant le fichier `customtex.fmt` créé précédemment, et `outputDirectory` sur un dossier de sortie existant. L’exemple compose un flux de texte autonome dans `typeset-with-custom-format.xps`, sans nécessiter de répertoire de travail d’entrée. Définissez-en un si l’entrée principale possède des dépendances, telles que des images.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-TypesetWithCustomTeXFormat.java" >}}

Évidemment, nous devons préciser le format d’une manière ou d’une autre. Tout d’abord, nous devons créer une instance de la classe [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) . Ensuite, dans le constructeur d'options, nous utilisons la configuration [TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-), qui prend notre fournisseur de format comme argument et charge le format au-dessus de l'état "vierge" du moteur.

Les deux exemples s’exécutent sans interaction et capturent la sortie du terminal en mémoire. Après le travail, l’exemple de composition ferme le flux d’entrée, libère le périphérique XPS et ferme le répertoire de travail et le fournisseur de format. Ces fonctionnalités sont présentées plus haut dans ce [guide](/tex/{{lang.url-fragment}}java/conversion/).

## Composition d'un fichier TeX au format Plain TeX

Si nous utilisons `TeXConfig.objectTeX()` sans fournisseur de format, le moteur chargera le format par défaut, qui est [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) dans son quatrième sens. Ainsi, si vous disposez d'un fichier TeX écrit au format Plain TeX, vous pouvez ainsi le convertir dans n'importe quel format cible pris en charge.