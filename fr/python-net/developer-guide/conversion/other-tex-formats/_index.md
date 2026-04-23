---
translation: true
template: /templates/_template-python-net.md
title: Autres formats de sortie de conversion TeX | Python
linktitle: Autres formats TeX
weight: 18
url: /python-net/other-tex-formats/
description: La solution API Aspose.TeX pour Python fournit des fonctionnalités qui vous permettent de convertir des fichiers LaTeX et des fichiers TeX personnalisés.
lastmod: "2026-04-20"
---

{{<section overview>}}

Il est peu probable que vous ayez actuellement besoin de convertir un fichier TeX écrit dans un format autre que LaTeX. Cependant, si vous étudiez le langage TeX ou les composants internes de TeX pour une raison quelconque, cela est toujours possible. Dans tous les cas, **Aspose.TeX for Python** vous permet de convertir des fichiers écrits au format *Plain TeX* et vous permet également de créer des formats personnalisés et de composer des documents conçus dans ces formats.

Pour commencer, nous allons créer un format personnalisé.

## Création d'un format personnalisé

Gardons à l'esprit que le fichier de format est une représentation binaire de l'état interne du moteur TeX.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

Comme vous pouvez le constater, le code ressemble au code de conversion d'un fichier TeX. Il existe cependant quelques distinctions.

Tout d'abord, dans ce cas, nous utilisons la configuration du travail [TeXConfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/). Cette configuration garantit que l'état du moteur est « vierge », ce qui signifie que les paramètres internes ont leurs valeurs par défaut et que l'ensemble des séquences de contrôle s'aligne sur l'ensemble des primitives. Dans notre exemple, l'ensemble des primitives est développé [dans l'article Aspose.TeX et Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Ensuite, nous procédons à la configuration des répertoires de travail d'entrée et de sortie comme d'habitude. Le répertoire de travail d'entrée doit inclure le fichier source du format principal et toutes ses dépendances.

Et la deuxième différence majeure réside dans la méthode par laquelle nous exécutons le travail. Dans ce cas, nous utilisons la méthode statique [create_format()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions) qui, en conjonction avec les options, nécessite que le nom du fichier source principal soit identique au nom du format.

## Composition d'un fichier TeX dans votre format personnalisé

Maintenant que nous avons créé notre propre format TeX, nous pouvons procéder à la composition d'un fichier TeX écrit dans ce format. Voici le code :

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

Pour spécifier le format, nous devons créer une instance de la classe [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/). Dans le constructeur d'options, nous utilisons la configuration [TeXConfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider), qui nécessite notre fournisseur de format comme argument et charge le format au-dessus de l'état "vierge" du moteur.

Le code restant devrait vous être familier, car il utilise les fonctionnalités évoquées plus tôt dans ce [guide](/tex/{{lang.url-fragment}}net/conversion/).

## Composition d'un fichier TeX au format Plain TeX

Si nous supprimons le fournisseur de format du code ci-dessus, le moteur chargera le format par défaut, qui est [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) dans son quatrième sens. Par conséquent, si vous disposez d'un fichier TeX écrit au format Plain TeX, vous pouvez le convertir dans n'importe quel format cible pris en charge en utilisant cette approche.