---
translation: true
template: /templates/_template-net.md
title: Interface de sortie d'Aspose.TeX | .FILET
linktitle: Interface de sortie d'Aspose.TeX
weight: 16
url: /net/aspose-tex-output/
description: La fonctionnalité de conversion de la solution API Aspose.TeX pour .NET avec TeX, en tant que format de sortie, est expliquée ici avec les exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for .NET** [Référence API](https://reference.aspose.com/tex/net/aspose.tex.io/) pour les définitions formelles de l'implémentation des E/S.

## Le concept du répertoire de sortie

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, Aspose.TeX définit un répertoire comme un mappage entre les noms et les lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IOutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/) pour la sortie, que l'utilisateur peut implémenter à ses propres fins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface étend [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), puisque le moteur peut d'abord créer et écrire un fichier, puis le relire. La propre méthode de l'interface [GetOutputFile()](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) renvoie le flux dans lequel écrire, par opposition au flux à lire renvoyé par [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/).

### Écriture de la sortie du fichier sur le système de fichiers du disque

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/latex-to-png/), la valeur la plus courante pour [OutputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) serait probablement une instance de la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/).

Voici comment nous le définirions :

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.cs" >}}

Ce cas d’utilisation est assez simple, il n’est donc plus nécessaire de s’y concentrer.

### Écriture de la sortie du fichier dans une archive ZIP

Nous pouvons également créer un fichier (ou un flux) et laisser le moteur TeX l'utiliser comme archive ZIP pour stocker les fichiers de sortie. C'est ici:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputZipDirectory.cs" >}}

Tout d'abord, nous créons un flux de sortie pour le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) comme étant une instance de la classe [OutputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/).

## Le concept du terminal de sortie

Il y a une autre partie importante de la sortie : la sortie du terminal. Quant à celui-ci, **Aspose.TeX pour .NET** définit l'interface générale [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) ayant une seule propriété qui renvoie une instance d'implémentation de [TextWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.textwriter). Les implémentations fournies sont discutées ci-dessous.

### Écriture de la sortie du terminal sur la console

Pour ce faire, nous devons définir l'option [TerminalOut](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalout/) pour qu'elle soit une instance de la classe [OutputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.cs" >}}

Encore une fois, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. Pour cette raison, cette section sert uniquement à des fins de démonstration.

### Écrire la sortie du terminal dans un fichier

Contrairement au terminal d'entrée, **Aspose.TeX pour .NET** fournit une implémentation de [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/), qui nous permet d'écrire la sortie du terminal dans un fichier dans un répertoire de sortie.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-OutputFileTerminal.cs" >}} 

Ici, nous demandons au moteur TeX d'écrire la sortie du terminal dans le fichier portant le nom [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, qui sera stocké dans le même répertoire de sortie que celui que nous avons spécifié pour le reste de la sortie. Mais ce n'est pas nécessaire. Nous pourrions aussi bien transmettre toute autre instance de toute implémentation de [IOutputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/ioutputterminal/) au constructeur.