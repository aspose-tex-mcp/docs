---
translation: true
template: /templates/_template-python-net.md
title: Interface de saisie d'Aspose.TeX | Python
linktitle: Interface de saisie d'Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: La fonctionnalité de conversion de la solution API Aspose.TeX pour Python avec TeX, en tant que format d'entrée, est expliquée ici avec les exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

> Pour les définitions formelles de l'implémentation E/S dans **Aspose.TeX pour Python**, veuillez consulter la [référence API](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## L'idée derrière le répertoire d'entrée

Étant donné que les primitives d'E/S du langage TeX ne peuvent gérer que les noms de fichiers, **Aspose.TeX pour Python** définit un répertoire comme un mappage entre des noms et des collections de données. Ces collections de données peuvent être des fichiers, des flux, des tableaux ou tout autre type. L'API permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit la classe générale [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), que les utilisateurs peuvent implémenter pour leurs besoins spécifiques. De plus, l'API fournit des implémentations intégrées, qui seront abordées plus tard. L'interface inclut la méthode [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), qui récupère le flux de données et détermine le nom complet du fichier en fonction d'un nom donné, qui sert de clé de mappage.

### Récupération des entrées de fichiers à partir du système de fichiers du disque

Voici l’approche que nous adopterions :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Ce cas d'utilisation particulier est assez simple, nous pouvons donc passer à autre chose maintenant.

### Récupération d'un fichier d'entrée à partir d'une archive ZIP

Une autre option consiste à stocker les fichiers d'entrée dans une archive ZIP et à la traiter comme un répertoire d'entrée. Dans un tel scénario, les étapes suivantes doivent être suivies :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

Pour commencer, nous créons le flux qui contient le fichier ZIP. Par la suite, après avoir créé les options de conversion, nous attribuons une instance de la classe [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) à la propriété [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). Le deuxième paramètre du constructeur représente le chemin de base dans l'archive. Si nous souhaitons que l’archive entière fonctionne comme répertoire d’entrée, nous devons fournir une chaîne vide comme argument.

## L'idée derrière le terminal d'entrée

Considérons maintenant le concept d'entrée de terminal. **Aspose.TeX pour Python** définit l'interface générale [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) spécifiquement à cet effet, qui inclut une propriété unique qui renvoie une instance de l'implémentation de [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Les implémentations disponibles seront discutées plus tard.

### Obtenir l'entrée du terminal depuis la console

Pour y parvenir, nous devons attribuer une instance de la classe [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) à l'option [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

Cependant, pour être honnête, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier explicitement. Compte tenu de l'absence d'autres implémentations, cette section est purement à des fins de démonstration.

En théorie, si nous disposons d'un fichier (ou script) TeX interactif avec un comportement prévisible, il pourrait être souhaitable d'implémenter une version du terminal d'entrée qui inclut un script correspondant pour répondre aux requêtes du moteur TeX. N'hésitez pas à essayer dès que vous en avez l'occasion !