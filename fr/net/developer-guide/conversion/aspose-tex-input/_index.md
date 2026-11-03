---
translation: true
template: /templates/_template-net.md
title: Interface de saisie d'Aspose.TeX | .NET
linktitle: Interface de saisie d'Aspose.TeX
weight: 15
url: /net/aspose-tex-input/
description: De conversion de la solution API Aspose.TeX pour .NET avec TeX, en tant que format d'entrée, est expliquée ici avec les exemples de code.
keywords: entrée tex aspose, .net tex, répertoire d'entrée, zip d'entrée, console d'entrée, options tex, répertoire de travail iinput, répertoirezip d'entrée, terminal d'entrée, conversion tex, searchcurrentdirectory
lastmod: "2026-11-03"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for .NET** [Référence API](https://reference.aspose.com/tex/net/aspose.tex.io/) pour les définitions formelles de l'implémentation des E/S.

## Le concept du répertoire d'entrée

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, **Aspose.TeX pour .NET** définit un répertoire comme un mappage entre les noms et des lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), que l'utilisateur peut implémenter pour ses propres besoins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface définit la méthode [GetFile()](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/getfile/), qui renvoie le flux de données et détermine le nom complet du fichier, tout en prenant un nom, hypothétiquement différent, comme premier argument, qui, en fait, est la clé de mappage. .

### Obtenir une entrée de fichier à partir du système de fichiers du disque

Voici comment nous procéderions :

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputFileSystemDirectory.cs" >}}

Ce cas d’utilisation est assez simple, il n’est donc plus nécessaire de s’y concentrer.

### Obtenir une entrée de fichier à partir d'une archive ZIP

Nous pouvons également mettre les fichiers d'entrée dans une archive ZIP et la considérer comme un répertoire d'entrée. Dans ce cas, il faut procéder comme suit :

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputZipDirectory.cs" >}}

Tout d'abord, nous créons le flux contenant le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/) comme étant une instance de la classe [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/). Le deuxième argument du constructeur est le chemin de base à l'intérieur de l'archive. Si nous voulons que l'archive entière soit un répertoire d'entrée, nous devons transmettre la chaîne vide. 

### Rechercher les fichiers d'entrée uniquement dans les répertoires de travail {#looking-for-input-files-only-in-the-working-directories}

Par défaut, lorsque le moteur TeX a besoin d'un fichier d'entrée portant un nom relatif, il le recherche d'abord dans le répertoire courant du processus et dans le répertoire du fichier d'entrée principal. Ce n'est qu'ensuite qu'il le recherche dans [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/inputworkingdirectory/), [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) et [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/). C'est pratique pour les applications console simples, mais cela signifie aussi que le résultat peut dépendre de l'endroit où le processus a été lancé et des fichiers qui s'y trouvent par hasard. Si nous voulons que l'entrée provienne strictement des répertoires que nous avons indiqués, nous devons définir l'option [SearchCurrentDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/searchcurrentdirectory/) sur `false` :

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-SearchCurrentDirectory.cs" >}}

Les fichiers aux noms absolus sont ouverts directement, quelle que soit cette option. La même option existe aussi pour le [rendu des formules et des figures](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/searchcurrentdirectory/) et pour la [réparation LaTeX](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/searchcurrentdirectory/).

## Le concept du terminal d'entrée

Il est maintenant temps de se rappeler qu'il y a aussi l'entrée du terminal. Quant à celui-ci, **Aspose.TeX pour .NET** définit l'interface générale [IInputTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/iinputterminal/) ayant une seule propriété qui renvoie une instance d'implémentation de [TextReader](https://docs.microsoft.com/en-us/dotnet/api/system.io.textreader). Les implémentations fournies sont discutées ci-dessous.

### Obtenir l'entrée du terminal depuis la console

Pour ce faire, nous devons définir l'option [TerminalIn](https://reference.aspose.com/tex/net/aspose.tex/texoptions/terminalin/) pour qu'elle soit une instance de la classe [InputConsoleTerminal](https://reference.aspose.com/tex/net/aspose.tex.io/inputconsoleterminal/).

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-InputConsoleTerminal.cs" >}}

Mais, à vrai dire, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. De ce fait, et tant qu'il n'y a pas d'autres implémentations, cette section sert uniquement à des fins de démonstration.

Théoriquement, si nous disposons d'un fichier (ou script) TeX interactif avec un comportement prévisible, nous souhaiterons peut-être implémenter une version du terminal d'entrée qui contiendrait un script complémentaire pour répondre aux requêtes du moteur TeX. Essayez-vous quand vous avez le temps !
