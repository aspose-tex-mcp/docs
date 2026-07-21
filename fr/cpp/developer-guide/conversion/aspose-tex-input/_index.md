---
translation: true
template: /templates/_template-cpp.md
title: Interface de saisie d'Aspose.TeX | C++
linktitle: Interface de saisie d'Aspose.TeX
weight: 15
url: /cpp/aspose-tex-input/
description: De conversion de la solution API Aspose.TeX pour C++ avec TeX, en tant que format d'entrée, est expliquée ici avec les exemples de code.
lastmod: "2026-04-20"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for C++** [Référence API](https://reference.aspose.com/tex/cpp/aspose.tex.io/) pour les définitions formelles de l'implémentation des E/S.

## Le concept du répertoire d'entrée

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, **Aspose.TeX pour C++** définit un répertoire comme un mappage entre les noms et des blocs de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/), que l'utilisateur peut implémenter pour ses propres besoins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface définit la méthode [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6), qui renvoie le flux de données et détermine le nom complet du fichier, tout en prenant un nom, hypothétiquement différent, comme premier argument, qui, en fait, est la clé de mappage. .

### Obtenir une entrée de fichier à partir du système de fichiers du disque

Voici comment nous procéderions :

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
```

Ce cas d’utilisation est assez simple, il n’est donc plus nécessaire de s’y concentrer.

### Obtenir une entrée de fichier à partir d'une archive ZIP

Nous pouvons également mettre les fichiers d'entrée dans une archive ZIP et la considérer comme un répertoire d'entrée. Dans ce cas, il faut procéder comme suit :

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Tout d'abord, nous créons le flux contenant le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/) comme étant une instance de la classe [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory/). Le deuxième argument du constructeur est le chemin de base à l'intérieur de l'archive. Si nous voulons que l'archive entière soit un répertoire d'entrée, nous devons transmettre la chaîne vide. 

## Le concept du terminal d'entrée

Il est maintenant temps de se rappeler qu'il y a aussi l'entrée du terminal. Quant à celui-ci, **Aspose.TeX pour C++** définit l'interface générale [IInputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal/) ayant une seule propriété qui renvoie une instance d'implémentation de [TextReader](https://reference.aspose.com/tex/cpp/system.io/textreader/). Les implémentations fournies sont discutées ci-dessous.

### Obtenir l'entrée du terminal depuis la console

Pour ce faire, nous devons définir l'option [TerminalIn](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin/) pour qu'elle soit une instance de la classe [InputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputconsoleterminal/).


```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.
```

Mais, à vrai dire, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. :-) De ce fait, et tant qu'il n'y a pas d'autres implémentations, cette section sert uniquement à des fins de démonstration.

Théoriquement, si nous disposons d'un fichier (ou script) TeX interactif avec un comportement prévisible, nous souhaiterons peut-être implémenter une version du terminal d'entrée qui contiendrait un script complémentaire pour répondre aux requêtes du moteur TeX. Essayez-vous quand vous avez le temps !