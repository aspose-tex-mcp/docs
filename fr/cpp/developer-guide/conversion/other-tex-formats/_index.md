---
translation: true
template: /templates/_template-cpp.md
title: Autres formats de sortie de conversion TeX | C++
linktitle: Autres formats TeX
weight: 18
url: /cpp/other-tex-formats/
description: De conversion de la solution API Aspose.TeX pour C++ permet de convertir des fichiers LaTeX et vos propres fichiers TeX personnalisés. Voici quelques exemples de code.
lastmod: "2026-04-20"
---

{{<section overview>}}

Il est très peu probable que vous souhaitiez actuellement convertir un fichier TeX écrit dans un autre format que LaTeX. Mais cela est possible si vous étudiez le langage TeX et/ou ses composants internes pour une raison quelconque. Quoi qu'il en soit, **Aspose.TeX for C++** vous permet de convertir des fichiers écrits au format Plain TeX. Il vous permet également de créer des formats personnalisés et de composer des documents conçus dans ces formats.

Nous commencerons par créer un format personnalisé.

## Création d'un format personnalisé

Rappelons que le fichier de format est un dump binaire de l'état interne du moteur TeX.

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Comme vous pouvez le voir, le code est similaire au code de conversion d'un fichier TeX. Mais il existe quelques différences.

Tout d'abord, nous utilisons ici la configuration du travail [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Il s'agit d'une configuration spéciale qui laisse l'état du moteur « vierge », c'est-à-dire que les paramètres internes ont leurs valeurs par défaut et que l'ensemble des séquences de contrôle coïncide avec l'ensemble des primitives. Dans notre exemple, l'ensemble des primitives est étendu dans le sens mentionné [ici](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Ensuite, nous configurons les répertoires de travail d’entrée et de sortie comme d’habitude. Le répertoire de travail d'entrée doit contenir le fichier source du format principal et toutes ses dépendances.

Et la deuxième différence clé réside dans la manière dont nous gérons le travail. Cette fois, nous utilisons la méthode statique [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), qui, avec les options, prend le nom du fichier source principal, qui doit être le même que le nom du format.

## Composition d'un fichier TeX dans votre format personnalisé

Maintenant que nous avons notre propre format TeX, nous souhaitons composer un fichier TeX écrit dans ce format. Voici le code :

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Évidemment, nous devons préciser le format d’une manière ou d’une autre. Tout d’abord, nous devons créer une instance de la classe [FormatProvider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/). Ensuite, dans le constructeur d'options, nous utilisons la configuration [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), qui prend notre fournisseur de format comme argument et charge le format au-dessus de l'état "vierge" du moteur.

Le reste du code devrait vous être familier. Il utilise les fonctionnalités évoquées plus haut dans ce [guide](/tex/{{lang.url-fragment}}cpp/conversion/).

## Composition d'un fichier TeX au format Plain TeX

Si nous supprimons le fournisseur de format du code que nous venons de démontrer, le moteur chargera le format par défaut, qui est [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) dans son quatrième sens. Ainsi, si vous disposez d'un fichier TeX écrit au format Plain TeX, vous pouvez ainsi le convertir dans n'importe quel format cible pris en charge.