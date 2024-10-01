---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX en PDF | Solution API Aspose.TeX pour C++
linktitle: LaTeX en PDF
weight: 11
url: /cpp/latex-to-pdf/
keywords: latex en pdf, latex pdf, convertir latex en pdf
description: Pour convertir TeX en PDF à l'aide de la solution API Aspose.TeX pour C++, lisez cet article pour voir qui décrit comment procéder ainsi que les exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Comment convertir LaTeX en PDF

Examinons en détail le code en C++ fournissant le moyen le plus simple de convertir LaTeX au format PDF.

{{<app/converter
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf">}}
{{</app/converter>}}

Ainsi, la première chose que nous devons faire (enfin, parfois pas la toute première) est de créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). La seule méthode statique qui fait cela est [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), alors ne soyons pas intrigués par la signification de son nom. La méthode prend une [instance](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) de la classe [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), qui convient parfaitement à la conversion d'un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration indique au moteur Object TeX de charger le format Object LaTeX et d'être prêt à accepter le fichier LaTeX. Le format Object LaTeX n'est en fait que le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), sauf qu'il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour configurer les métriques de la page.

La première des options requises est [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) qui définit l'espace, ou la zone, où la sortie TeX sera écrite. [Ici](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) sont les détails sur le concept de répertoire de sortie dans **Aspose.TeX pour C++**. Dans cet exemple, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), qui nous permet d'écrire la sortie dans le répertoire ou dossier spécifié.

La deuxième option est une instance de classe [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/) qui contrôlera la transformation du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) au format cible. Puisque nous convertissons LaTeX en PDF, il s'agit de l'instance de classe [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Ensuite, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Voulant convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) version du constructeur. Nous devons spécifier le chemin complet du fichier. Sinon, le moteur le recherchera dans le répertoire courant (qui est [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) et ne le trouvera probablement pas. Néanmoins, nous pouvons omettre l'extension si notre fichier possède celle *.tex*. Le moteur l’ajoutera automatiquement. Le deuxième argument du constructeur est une instance de classe [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Puisque nous convertissons LaTeX en PDF, il s'agit d'une instance de classe [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). Comme dernier argument, nous passons les options de conversion récemment préparées.

Il ne reste plus qu'à [exécuter](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb) le travail.

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

Nous retrouverons d'autres "fruits" du travail du moteur dans le dossier que nous avons spécifié comme répertoire de sortie. Ce seront le fichier de transcription et, **le voici !**, le fichier PDF de sortie principal.

## Une autre façon d'écrire le fichier PDF de sortie principal

Il existe un autre constructeur de la classe [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), qui nous permet d'obtenir le fichier PDF résultant d'une manière alternative.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> pdfStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.pdf"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ pdfsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in PDF format.
            options->set_SaveOptions(System::MakeObject<PdfSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<PdfDevice>(pdfStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

Le fichier *any-name.pdf* dans le répertoire spécifié sera notre fichier PDF de sortie principal. En même temps, contrairement à [image output](/tex/{{lang.url-fragment}}cpp/latex-to-png/#an-alternative-way-to-write-main-output-png-files), nous ne trouverons aucun fichier PDF dans le répertoire de sortie défini par les options de conversion. Exception : *any-name.pdf* se trouve (par son chemin) dans le même répertoire du système de fichiers qui est attribué à l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) à l'aide de [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

## À propos des options de saisie

Dans le cas où notre fichier d'entrée principal nécessite des dépendances, par exemple des packages, qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, nous DEVONS définir l'option [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) de la même manière que nous définissons le [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory). option et placez les dépendances dans ce répertoire. Les dépendances peuvent être arbitrairement organisées en sous-répertoires. Dans le cas où nous avons nos propres fichiers à inclure tout au long du processus de composition, par exemple des fichiers graphiques externes, nous DEVONS également définir le [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont collectés. Nous pouvons également placer le fichier d'entrée principal quelque part dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()` (ou ne spécifier aucun chemin si le fichier d'entrée principal est à la racine). [Ici](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) sont les détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour C++** et les implémentations fournies.

D'autres options de travail TeX sont discutées [ici](/tex/{{lang.url-fragment}}cpp/other-options/).

**Vous pouvez également consulter la conversion gratuite LaTeX en PDF [application Web](https://products.aspose.app/tex/conversion/latex-to-pdf) construite sur la base de [Aspose.TeX pour l'API C++](https://products.aspose.com/tex/cpp/).**