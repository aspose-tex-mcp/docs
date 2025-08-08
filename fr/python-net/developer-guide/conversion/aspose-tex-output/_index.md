---
translation: true
template: /templates/_template-python-net.md
title: Interface de sortie d'Aspose.TeX | Python
linktitle: Interface de sortie d'Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Voici une explication de De conversion de la solution API Aspose.TeX pour Python, avec TeX comme format de sortie, avec des exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}


> Pour les définitions formelles de l'implémentation des E/S, veuillez vous référer à la [référence API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) de **Aspose.TeX pour Python**.

## L'idée derrière le répertoire de sortie

Aspose.TeX définit un répertoire comme un mappage entre des noms et des blocs de données, où les blocs de données peuvent être des fichiers, des flux, des tableaux ou d'autres types de données. L'API permet de spécifier des répertoires de travail d'entrée et de sortie distincts. Pour la sortie, l'API fournit l'interface générale [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), qui peut être implémentée par l'utilisateur pour ses besoins spécifiques. De plus, l'API fournit des implémentations prêtes à l'emploi, qui seront abordées ci-dessous. L'interface *IOutputWorkingDirectory* étend [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), car le moteur peut d'abord créer et écrire un fichier, puis le relire. L'interface inclut la méthode [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), qui renvoie le flux dans lequel écrire, contrairement à la méthode [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), qui renvoie le flux à partir duquel lire.

### Enregistrement de la sortie sous forme de fichier dans le système de fichiers du disque

Comme mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/latex-to-image/), le [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) est généralement défini comme une instance de la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Voici comment nous le définirions :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Ce cas d’utilisation particulier est simple, il n’est donc pas nécessaire de l’approfondir davantage.

### Enregistrement de la sortie sous forme de fichier d'archive ZIP.

Une autre option consiste à créer un fichier ou un flux et à l'utiliser comme archive ZIP pour stocker les fichiers de sortie. Voici un exemple :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

Pour commencer, nous créons un flux de sortie pour le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option *output_working_directory* comme étant une instance de la classe [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## L'idée derrière le terminal de sortie

La sortie du terminal est un autre aspect important de la sortie. Pour cela, **Aspose.TeX pour Python** définit l'interface générale [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), qui possède une seule propriété qui renvoie une instance de l'implémentation de [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). Les implémentations disponibles seront discutées ci-dessous.

### Écrire la sortie du terminal sur la console

Pour y parvenir, nous devons définir l'option [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) comme instance de la classe [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Encore une fois, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. Par conséquent, cette section est fournie uniquement à des fins de démonstration.

### Écrire la sortie du terminal dans un fichier

Contrairement au terminal d'entrée, **Aspose.TeX pour Python** inclut une implémentation de l'interface *IOutputTerminal* qui nous permet d'écrire la sortie du terminal dans un fichier dans un répertoire de sortie spécifié.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

Dans ce cas, nous demandons au moteur TeX d'écrire la sortie du terminal dans un fichier nommé [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, qui sera situé dans le même répertoire de sortie que le reste de la sortie. Toutefois, cela n’est pas obligatoire. Nous pouvons également fournir toute autre instance d'implémentation de *IOutputTerminal* au constructeur.