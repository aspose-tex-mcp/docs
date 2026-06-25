---
translation: true
template: /templates/_template-java.md
title: LaTeX en PDF | Java
linktitle: LaTeX en PDF
weight: 11
url: /java/latex-to-pdf/
keywords: latex en pdf, latex pdf, convertir latex en pdf
description: Pour convertir TeX en PDF à l'aide de l'API Aspose.TeX pour Java, lisez cet article pour voir comment procéder avec les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}


## Comment convertir LaTeX en PDF

Examinons de plus près le code Java fournissant le moyen le plus simple de convertir LaTeX au format PDF.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.java" >}}

Ainsi, la première chose que nous devons faire (parfois pas la toute première, comme nous le découvrirons plus tard) est de créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions). La seule méthode statique qui fait cela est [consoleAppOptions()](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#consoleAppOptions-com.aspose.tex.TeXConfig-), alors ne nous soucions pas de la signification de son nom. La méthode prend une [instance](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig#objectLaTeX--) de la classe [TeXConfig](https://reference.aspose.com/tex/java/com.aspose.tex/TeXConfig), qui convient parfaitement à la conversion d'un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration demande au moteur Object TeX de charger le format Object LaTeX et d'être prêt à accepter le fichier LaTeX. Le format objet LaTeX est simplement le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), sauf qu'il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour configurer les métriques de la page.

La première des options requises est [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) qui définit l'espace, ou la zone, où la sortie TeX sera écrite. [Ici](/tex/{{lang.url-fragment}}java/aspose-tex-output/) sont les détails sur le concept de répertoire de sortie dans **Aspose.TeX pour Java**. Dans cet exemple, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory), qui nous permet d'écrire la sortie dans le répertoire ou dossier spécifié.

La deuxième option est une instance de classe [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/SaveOptions) qui contrôlera la transformation du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) au format cible. Puisque nous convertissons LaTeX en PDF, il s'agit de l'instance de classe [PdfSaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfSaveOptions).

Ensuite, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob). Voulant convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.lang.String-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) version du constructeur. Nous devons spécifier le chemin complet du fichier. Sinon, le moteur le cherchera dans le répertoire courant (qui est défini [ici](https://docs.oracle.com/javase/7/docs/api/java/io/File.html)) et ne le trouvera probablement pas. Néanmoins, nous pouvons omettre l'extension si notre fichier possède celle *.tex*. Le moteur l’ajoutera automatiquement. Le deuxième argument du constructeur est une instance de classe [Device](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/Device). Puisque nous convertissons LaTeX en PDF, il s'agit d'une instance de classe [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice). Comme dernier argument, nous passons les options de conversion récemment préparées.

Il ne nous reste plus qu'à [exécuter](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#run--) le travail.

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
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Nous trouverons d'autres produits du moteur dans le dossier que nous avons spécifié comme répertoire de sortie. Il s'agira du fichier de transcription (.log) et, **Voila !**, du fichier PDF de sortie principal.

## Une autre façon d'écrire le fichier PDF de sortie principal

Il existe un autre constructeur de la classe [PdfDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/PdfDevice#PdfDevice-java.io.OutputStream-), qui nous permet d'obtenir le fichier PDF résultant d'une manière alternative.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.java" >}}

Le fichier *any-name.pdf* dans le répertoire spécifié sera notre fichier PDF de sortie principal. En même temps, contrairement à [image output](/tex/{{lang.url-fragment}}java/latex-to-image/), nous ne trouverons aucun fichier PDF dans le répertoire de sortie défini par les options de conversion. Exception : *any-name.pdf* se trouve (par son chemin) dans le même répertoire du système de fichiers qui est attribué à l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) à l'aide de [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

## À propos des options de saisie

Dans le cas où notre fichier d'entrée principal nécessite des dépendances, par exemple des packages, qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, nous DEVONS définir l'option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getRequiredInputDirectory--) de la même manière que nous définissons le [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--). option et placez les dépendances dans ce répertoire. Les dépendances peuvent être arbitrairement organisées en sous-répertoires. Dans le cas où nous avons nos propres fichiers à inclure tout au long du processus de composition, par exemple des fichiers graphiques externes, nous DEVONS également définir le [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont collectés. Nous pouvons également placer le fichier d'entrée principal quelque part dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()` (ou ne spécifier aucun chemin si le fichier d'entrée principal est à la racine). [Ici](/tex/{{lang.url-fragment}}java/aspose-tex-input/) sont les détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour Java** et les implémentations fournies.

D'autres options de travail TeX sont discutées [ici](/tex/{{lang.url-fragment}}java/other-options/).

**Vous pouvez également consulter la conversion gratuite LaTeX en PDF [application Web](https://products.aspose.app/tex/conversion/latex-to-pdf) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/java/) est la page de la version Java.**