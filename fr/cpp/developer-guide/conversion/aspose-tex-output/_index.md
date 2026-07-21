---
translation: true
template: /templates/_template-cpp.md
title: Interface de sortie d'Aspose.TeX | C++
linktitle: Interface de sortie d'Aspose.TeX
weight: 16
url: /cpp/aspose-tex-output/
description: De conversion de la solution API Aspose.TeX pour C++ avec TeX, en tant que format de sortie, est expliquée ici avec les exemples de code.
lastmod: "2026-04-20"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for C++** [Référence API](https://reference.aspose.com/tex/cpp/aspose.tex.io/) pour les définitions formelles de l'implémentation des E/S.

## Le concept du répertoire de sortie

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, Aspose.TeX définit un répertoire comme un mappage entre les noms et les lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IOutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/) pour la sortie, que l'utilisateur peut implémenter à ses propres fins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface étend [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/), puisque le moteur peut d'abord créer et écrire un fichier, puis le relire. La propre méthode de l'interface [GetOutputFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputworkingdirectory/getoutputfile/) renvoie le flux dans lequel écrire, par opposition au flux à lire renvoyé par [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6).

### Écriture de la sortie du fichier sur le système de fichiers du disque

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}cpp/latex-to-image/), la valeur la plus courante pour [OutputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) serait probablement une instance de la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory/).

Voici comment nous le définirions :

```C++
// Create conversion options instance.
...
// Specify a file system working directory for the output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
```
Ce cas d’utilisation est assez simple, il n’est donc plus nécessaire de s’y concentrer.

### Écriture de la sortie du fichier dans une archive ZIP

Nous pouvons également créer un fichier (ou un flux) et laisser le moteur TeX l'utiliser comme archive ZIP pour stocker les fichiers de sortie. C'est ici:

```C++
    // Open the stream for the ZIP archive that will serve as the output working directory.
    System::SharedPtr<System::IO::Stream> outZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"zip-pdf-out.zip"), System::IO::FileMode::Create);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputZipDirectory>(outZipStream));
```

Tout d'abord, nous créons un flux de sortie pour le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory/) comme étant une instance de la classe [OutputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputzipdirectory/).

## Le concept du terminal de sortie

Il y a une autre partie importante de la sortie : la sortie du terminal. Quant à celui-ci, **Aspose.TeX pour C++** définit l'interface générale [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal/) ayant une seule propriété qui renvoie une instance d'implémentation de [TextWriter](https://reference.aspose.com/tex/cpp/system.io/textwriter/). Les implémentations fournies sont discutées ci-dessous.

### Écriture de la sortie du terminal sur la console

Pour ce faire, nous devons définir l'option [TerminalOut](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalout/) pour qu'elle soit une instance de la classe [OutputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputconsoleterminal/).

```C++
// Create conversion options instance.
...
// Specify the console as the output terminal.
options->set_TerminalOut(System::MakeObject<OutputConsoleTerminal>()); // Default. No need to specify.
```

Encore une fois, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. Pour cette raison, cette section sert uniquement à des fins de démonstration.

### Écrire la sortie du terminal dans un fichier

Contrairement au terminal d'entrée, **Aspose.TeX pour C++** fournit une implémentation de [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal/), qui nous permet d'écrire la sortie du terminal dans un fichier dans un répertoire de sortie.

```C++
// Create conversion options instance.
...
// Specify that the terminal output must be written to a file in the output working directory.
// The file name is <job_name>.trm.
options->set_TerminalOut(System::MakeObject<OutputFileTerminal>(options->get_OutputWorkingDirectory()));
```
Ici, nous demandons au moteur TeX d'écrire la sortie du terminal dans le fichier portant le nom [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, qui sera stocké dans le même répertoire de sortie que celui que nous avons spécifié pour le reste de la sortie. Mais ce n'est pas nécessaire. Nous pourrions aussi bien transmettre toute autre instance de toute implémentation de [IOutputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/ioutputterminal/) au constructeur.