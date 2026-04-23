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

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.java" >}}

Comme vous pouvez le voir, le code est similaire au code de conversion d'un fichier TeX. Mais il existe quelques différences.

Tout d'abord, nous utilisons ici la configuration du travail [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectIniTeX--). Il s'agit d'une configuration spéciale qui laisse l'état du moteur « vierge », c'est-à-dire que les paramètres internes ont leurs valeurs par défaut et que l'ensemble des séquences de contrôle coïncide avec l'ensemble des primitives. Dans notre exemple, l'ensemble des primitives est étendu dans le sens mentionné [ici](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Ensuite, nous configurons les répertoires de travail d’entrée et de sortie comme d’habitude. Le répertoire de travail d'entrée doit contenir le fichier source du format principal et toutes ses dépendances.

Et la deuxième différence clé réside dans la manière dont nous gérons le travail. Cette fois, nous utilisons la méthode statique [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) qui, avec les options, prend le nom du fichier source principal, qui doit être le même que le nom du format.

## Composition d'un fichier TeX dans votre format personnalisé

Maintenant que nous avons notre propre format TeX, nous souhaitons composer un fichier TeX écrit dans ce format. Voici le code :

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.java" >}}

Évidemment, nous devons préciser le format d’une manière ou d’une autre. Tout d’abord, nous devons créer une instance de la classe [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/FormatProvider). Ensuite, dans le constructeur d'options, nous utilisons la configuration [TeXConfig.objectTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectTeX--), qui prend notre fournisseur de format comme argument et charge le format au-dessus de l'état "vierge" du moteur.

Le reste du code devrait vous être familier. Il utilise les fonctionnalités évoquées plus haut dans ce [guide](/tex/{{lang.url-fragment}}java/conversion/).

## Composition d'un fichier TeX au format Plain TeX

Si nous supprimons le fournisseur de format du code que nous venons de démontrer, le moteur chargera le format par défaut, qui est [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) dans son quatrième sens. Ainsi, si vous disposez d'un fichier TeX écrit au format Plain TeX, vous pouvez ainsi le convertir dans n'importe quel format cible pris en charge.