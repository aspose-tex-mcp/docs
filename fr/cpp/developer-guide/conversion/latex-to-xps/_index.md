---
translation: true
template: /templates/_template-cpp.md
title: LaTeX vers XPS | Aspose.TeX pour C++
linktitle: LaTeX vers XPS
weight: 12
url: /cpp/latex-to-xps/
description: La fonctionnalité de conversion de la solution API Aspose.TeX pour C++ permet de convertir les fichiers LaTeX au format XPS. Voici quelques exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

Un autre format cible pris en charge par **Aspose.TeX** est [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un fichier **XPS** est en fait un package ZIP qui contient le contenu paginé d'un document, ainsi que les métadonnées requises pour un affichage correct par des visualiseurs spécifiques (tels que Windows XPS Viewer) et une impression. Toutes les données d'un package sont représentées par des fichiers. Certains d'entre eux sont binaires et contiennent des ressources telles que des images, des polices et des profils ICC. D'autres sont des fichiers XML dans divers schémas spécifiques. Ces derniers incluent des fichiers contenant les données du document elles-mêmes. Les données du document se composent d'un ensemble de fichiers - chaque fichier contient des données pour une page individuelle du document. Ces fichiers se composent d'un seul élément de page et d'une arborescence d'éléments enfants - *Canvas*, *Path* et *Glyphs*. *Canvas* est un élément de regroupement qui peut contenir d'autres *Canvas*, *Paths* et *Glyphs*. Sa mission est de contrôler l'apparence de tous les éléments enfants en tant que groupe. Les éléments *Path* sont utilisés pour définir des chemins de graphiques vectoriels. Et les éléments *Glyphs* sont utilisés pour définir le contenu textuel. Les trois éléments ont des propriétés permettant de définir divers aspects de l’apparence.

Il existe la bibliothèque [**Aspose.Page**](https://products.aspose.com/page/) qui fournit une API pour manipuler les documents XPS, ainsi que pour les convertir aux formats PDF et d'image raster.

## Comment convertir LaTeX en XPS

La conversion en XPS est aussi simple que la [conversion aux formats d'image raster](/tex/{{lang.url-fragment}}cpp/latex-to-image/), sauf qu'en plus des [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions), nous devons changer le périphérique en une instance du [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device) classe.


```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Une autre façon d'écrire le fichier XPS de sortie principal

Il existe un autre constructeur de la classe [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), qui nous permet d'obtenir le fichier XPS résultant d'une manière alternative.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.xps"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in XPS format.
            options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<XpsDevice>(xpsStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

L'effet est le même que celui que nous obtenons [ici](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Vous pouvez également consulter la conversion gratuite LaTeX vers XPS [application Web](https://products.aspose.app/tex/conversion/latex-to-xps) construite sur la base de l'API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Ici](https://products.aspose.com/tex/cpp/) est la page de la version C++.**