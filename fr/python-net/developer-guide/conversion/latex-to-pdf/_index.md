---
translation: true
template: /templates/_template-python-net.md
title: LaTeX en PDF | Python
linktitle: LaTeX en PDF
weight: 11
url: /python-net/latex-to-pdf/
keywords: latex en pdf, latex pdf, convertir latex en pdf
description: Découvrez comment convertir TeX en PDF à l'aide de Aspose.TeX pour Python avec cet article, qui fournit une explication détaillée et des exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Conversion de LaTeX en PDF

Examinons maintenant en profondeur le code Python qui offre l'approche la plus simple pour convertir LaTeX au format PDF.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Simplest.py" >}}

Pour commencer, nous devons créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). La méthode [console_app_options()](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/console_app_options/#aspose.tex.TeXConfig) est la seule méthode statique qui accomplit cela, alors ne vous inquiétez pas de son nom. Cette méthode prend une instance [object_latex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_latex/) de la classe [TeXConfig](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/), ce qui est parfait pour convertir un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration demande au moteur Object TeX de charger le format Object LaTeX et d'être prêt à traiter le fichier LaTeX. Le format Object LaTeX est essentiellement le même que le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), mais il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour définir les métriques de la page.

La première option qui doit être spécifiée est [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/), qui détermine l'emplacement où la sortie TeX sera enregistrée. Si nécessaire, vous pouvez trouver plus d'informations sur le [concept de répertoire de sortie dans **Aspose.TeX**](/tex/{{lang.url-fragment}}net/aspose-tex-output/). Dans ce cas particulier, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/), qui nous permet d'écrire la sortie dans un répertoire ou un dossier désigné.

La deuxième option nécessite une instance de la classe [SaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/saveoptions/), qui détermine comment le [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) est transformé dans le format souhaité. Dans notre cas, lorsque nous convertissons LaTeX en PDF, il fait référence à une instance de la classe [PdfSaveOptions](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Pour convertir un fichier LaTeX stocké dans le système de fichiers, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) en utilisant le [constructeur](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#str-aspose.tex.presentation.Device-aspose.tex.TeXOptions) qui prend le chemin complet du fichier comme paramètre. Si nous ne précisons pas le chemin complet, le moteur recherchera le fichier dans le répertoire courant (qui est le répertoire de travail du script) et risque de ne pas le trouver. Cependant, nous pouvons omettre l'extension si notre fichier porte l'extension « .tex », car le moteur l'ajoutera automatiquement. Le deuxième argument du constructeur est une instance de la classe [Device](https://reference.aspose.com/tex/python-net/aspose.tex.presentation/device/). Dans notre cas, puisque nous convertissons LaTeX en PDF, il s'agit d'une instance de la classe [PdfDevice](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/). Enfin, nous passons les options de conversion récemment préparées comme dernier argument.

Il ne reste plus qu'à [exécuter](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/run/#) le travail.

Après l’exécution, qu’elle ait réussi ou non, la première chose que nous verrons est la sortie du terminal. Si l’exécution réussit, le résultat ressemblera à ceci :

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

Dans le dossier que nous avons spécifié comme répertoire de sortie, nous trouverons le fichier de transcription et, **le voici !**, le fichier PDF de sortie principal, entre autres résultats du travail du moteur.

## Une autre façon d'écrire le fichier PDF de sortie principal

La classe *PdfDevice* a un autre [constructeur](https://reference.aspose.com/tex/python-net/aspose.tex.presentation.pdf/pdfdevice/__init__/#io.RawIOBase) qui nous permet d'obtenir différemment le fichier PDF résultant.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-LaTeXToPdf-Alternative.py" >}}

Le fichier PDF de sortie principal sera nommé « any-name.pdf » et sera situé dans le répertoire spécifié. Cependant, contrairement à la [sortie d'image](/tex/{{lang.url-fragment}}python-net/latex-to-image/#an-alternative-way-to-write-the-main-output-png-files), il n'y aura aucun autre fichier PDF dans le répertoire de sortie spécifié par les options de conversion. L'exception est si `any-name.pdf` se trouve dans le même répertoire du système de fichiers attribué à l'option *output_working_directory* à l'aide de *OutputFileSystemDirectory*.

## À propos des options de saisie

Si notre fichier d'entrée principal nécessite des dépendances, telles que des packages qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, il est nécessaire de définir l'option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de la même manière que nous définissons l'option *output_working_directory* et placez les dépendances dans ce répertoire. Les dépendances peuvent être organisées en sous-répertoires comme vous le souhaitez. De plus, si nous avons nos propres fichiers à inclure dans le processus de composition, tels que des fichiers graphiques externes, nous devons également définir le [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont stockés. Nous pouvons également placer le fichier d'entrée principal dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()`, ou ne spécifier aucun chemin si le fichier d'entrée principal se trouve à la racine. Pour plus de détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour Python** et les implémentations fournies, veuillez vous référer à [ici](/tex/{{lang.url-fragment}}python-net/aspose-tex-input/).

Il existe également [d'autres options de travail TeX](/tex/{{lang.url-fragment}}python-net/other-options/) discutées.

**Vous pouvez également explorer l'[application Web gratuite pour la conversion LaTeX en PDF](https://products.aspose.app/tex/conversion/latex-to-pdf), développée à l'aide de [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/).**