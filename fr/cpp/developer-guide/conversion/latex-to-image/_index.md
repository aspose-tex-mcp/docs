---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX vers l'image | Aspose.TeX pour C++
linktitle: LaTeX en image
weight: 10
url: /cpp/latex-to-image/
aliases: /cpp/latex-vers-png/
keywords: latex à png, latex png, latex à image, image latex, latex à jpg, latex jpg, latex à jpeg, latex jpeg, latex à tiff, latex tiff, latex à bmp, latex bmp
description: Pour convertir TeX en formats d'image à l'aide de la solution API Aspose.TeX pour C++, découvrez cet article qui décrit comment procéder ainsi que les exemples de code.
lastmod: 2023-03-23
---

{{<section overview>}}

**Aspose.TeX pour C++** nous permet également de convertir des fichiers LaTeX vers un certain nombre d'autres formats d'images raster.

## Comment convertir LaTeX en PNG

Examinons en détail le code en C++ fournissant le moyen le plus simple de convertir LaTeX au format PNG.

{{<app/converter
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Ainsi, la première chose que nous devons faire (enfin, parfois pas la toute première) est de créer une instance de la classe [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). La seule méthode statique qui fait cela est [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), alors ne soyons pas intrigués par la signification de son nom. La méthode prend l'[instance get_ObjectLaTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) de la classe [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), qui convient parfaitement à la conversion d'un [fichier LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Cette configuration indique au moteur Object TeX de charger le format Object LaTeX et d'être prêt à accepter le fichier LaTeX. Le format Object LaTeX n'est en fait que le format [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), sauf qu'il utilise des primitives spécifiques à [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) pour configurer les métriques de la page.

La première des options requises est [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) qui définit l'espace, ou la zone, où la sortie TeX sera écrite. [Ici](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) sont les détails sur le concept de répertoire de sortie dans **Aspose.TeX pour C++**. Dans cet exemple, nous utilisons la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), qui nous permet d'écrire la sortie dans le répertoire ou dossier spécifié.

La deuxième option est une instance de classe [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/) qui contrôlera la transformation du [modèle objet](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) au format cible. Puisque nous convertissons LaTeX en PNG, c'est l'instance de classe [PngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), qui nous permet de spécifier la résolution des images de sortie.

Ensuite, nous devons créer une instance de la classe [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Voulant convertir un fichier LaTeX stocké dans le système de fichiers, nous utilisons [cette](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) version du constructeur. Nous devons spécifier le chemin complet du fichier. Sinon, le moteur le recherchera dans le répertoire courant (qui est [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) et ne le trouvera probablement pas. Néanmoins, nous pouvons omettre l'extension si notre fichier possède celle *.tex*. Le moteur l’ajoutera automatiquement. Le deuxième argument du constructeur est une instance de classe [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Puisque nous convertissons LaTeX en PNG, il s'agit d'une instance de classe [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) (commune à tous les formats d'image pris en charge). Comme dernier argument, nous passons les options de conversion récemment préparées.

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Nous retrouverons d'autres "fruits" du travail du moteur dans le dossier que nous avons spécifié comme répertoire de sortie. Il s'agira du fichier de transcription et, **le voici !**, du ou des fichiers image PNG de sortie principaux.

## Une autre façon d'écrire le(s) fichier(s) PNG de sortie principal

Il existe une autre façon d'obtenir des données d'image sous forme de tableau de tableaux d'octets, chaque tableau de la deuxième dimension représente les données d'image d'une page distincte.

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```

Le(s) fichier(s) *"page-n.png"* seront écrits dans n'importe quel chemin que nous spécifions. Contrairement à [Sortie PDF](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), ils dupliqueront les fichiers PNG de sortie écrits dans le répertoire de sortie.

## À propos des options de saisie

Dans le cas où notre fichier d'entrée principal nécessite des dépendances, par exemple des packages, qui ne sont pas inclus dans le système LaTeX de base et les packages pris en charge, nous DEVONS définir l'option [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) de la même manière que nous définissons [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory). option et placez les dépendances dans ce répertoire. Les dépendances peuvent être arbitrairement organisées en sous-répertoires. Dans le cas où nous avons nos propres fichiers à inclure tout au long du processus de composition, par exemple des fichiers graphiques externes, nous DEVONS également définir le [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) en utilisant le chemin d'accès à l'emplacement où ces fichiers sont collectés. Nous pouvons également placer le fichier d'entrée principal quelque part dans le répertoire d'entrée et spécifier le chemin relatif dans la méthode `run()` (ou ne spécifier aucun chemin si le fichier d'entrée principal est à la racine). [Ici](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) sont les détails sur le concept de répertoire d'entrée dans **Aspose.TeX pour C++** et les implémentations fournies.

D'autres options de travail TeX sont discutées [ici](/tex/{{lang.url-fragment}}cpp/other-options/).

**Vous pouvez également consulter la conversion gratuite LaTeX vers PNG [application Web](https://products.aspose.app/tex/conversion/latex-to-png) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/cpp/) est la page de la version C++.**

Ci-dessous, nous discutons de la conversion de LaTeX vers d'autres formats d'image raster pris en charge. Nous n’entrerons pas dans les détails simplement parce qu’il n’y a pas de détails. La seule différence réside dans le type de la propriété [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) dans les options de conversion.

## Comment convertir LaTeX en JPEG

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**Vous pouvez également consulter la conversion gratuite LaTeX vers JPEG [application Web](https://products.aspose.app/tex/conversion/latex-to-jpg) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/cpp/) est la page de la version C++.**

## Comment convertir LaTeX en TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**Vous pouvez également consulter la conversion gratuite LaTeX vers TIFF [application Web](https://products.aspose.app/tex/conversion/latex-to-tiff) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/cpp/) est la page de la version C++.**

## Comment convertir LaTeX en BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**Vous pouvez également consulter la conversion gratuite LaTeX vers BMP [application Web](https://products.aspose.app/tex/conversion/latex-to-bmp) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/cpp/) est la page de la version C++.**