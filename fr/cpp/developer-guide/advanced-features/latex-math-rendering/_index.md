---
translation: true
template: /templates/_template-cpp.md
title: Rendu des formules mathématiques LaTeX | C++
linktitle: Rendu des formules mathématiques LaTeX
weight: 10
url: /cpp/latex-math-formula-rendering/
description: Aspose.TeX pour le rendu des formules mathématiques C++ LaTeX est décrite dans cet article. Vous trouverez ici des exemples de code de la fonctionnalité.
lastmod: "2026-04-20"
---

{{<section overview>}}

La section de référence de l'API liée à ce sujet est [ici](https://reference.aspose.com/tex/cpp/aspose.tex.features/). En fait, le moyen le plus simple de démontrer la fonctionnalité de rendu des formules mathématiques LaTeX est de commencer par l’exemple. C'est ici:

```C++
    // Create rendering options 
    System::SharedPtr<PngMathRendererOptions> options = System::MakeObject<PngMathRendererOptions>();
    // Specify the image resolution 150 dpi
    options->set_Resolution(150);
    // Specify the preamble.
    options->set_Preamble(u"\\usepackage{amsmath}\r\n\\usepackage{amsfonts}\r\n\\usepackage{amssymb}\r\n\\usepackage{color}");
    // Specify the scaling factor 300%.
    options->set_Scale(3000);
    // Specify the foreground color.
    options->set_TextColor(System::Drawing::Color::get_Black());
    // Specify the background color.
    options->set_BackgroundColor(System::Drawing::Color::get_White());
    // Specify the output stream for the log file.
    options->set_LogStream(System::MakeObject<System::IO::MemoryStream>());
    // Specify whether to show the terminal output on the console or not.
    options->set_ShowTerminal(true);
    
    // Create the output stream for the formula image.
    {
        System::SharedPtr<System::IO::Stream> stream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"math-formula.png"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ stream});
        // ------------------------------------------
        try
        {
            System::Drawing::SizeF size = System::MakeObject<Features::PngMathRenderer>()->Render(u"\\begin{equation*}\r\ne^x = x^{\\color{red}0} + x^{\\color{red}1} + \\frac{x^{\\color{red}2}}{2} + \\frac{x^{\\color{red}3}}{6} + \\cdots = \\sum_{n\\geq 0} \\frac{x^{\\color{red}n}}{n!}\r\n\\end{equation*}", stream, options, size);
            
            // Show other results.
            System::Console::get_Out()->WriteLine(options->get_ErrorReport());
            System::Console::get_Out()->WriteLine();
            System::Console::get_Out()->WriteLine(System::String(u"Size: ") + size);
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }

```

Passons aux détails. Tout d'abord, nous créons une instance [options de rendu](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions/), similaire à la composition TeX/LaTeX. Nous le faisons ici simultanément en spécifiant la résolution de l’image de sortie.

Ensuite, nous précisons le préambule. Le préambule par défaut est :

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
``
qui fournit une prise en charge des formules mathématiques légèrement plus avancée que LaTeX de base. Vous pouvez, par exemple, ajouter le package `color` si vous souhaitez utiliser votre propre surlignage dans la formule, comme nous l'avons montré dans l'exemple de code.

Ensuite, nous demandons au moteur de rendu de mettre à l'échelle la sortie de 300 %.

Les deux options suivantes définissent les couleurs de premier plan et d'arrière-plan. Les parties de la formule qui ne sont pas couvertes (« colorées ») par la surbrillance personnalisée seront affichées dans la couleur « TextColor ».

La ligne suivante de l'exemple n'a pas beaucoup de sens. Cela démontre simplement que vous pouvez diriger la sortie du journal vers un flux.

Et la dernière option « ShowTerminal » vous permet d'écrire la sortie du terminal sur la console.

La méthode qui effectue réellement le rendu est [MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render/). Il renvoie la taille de la formule en points.

Le flux dans lequel l’image doit être écrite est pris par la méthode comme deuxième argument. Nous créons ensuite le flux.

Et enfin, nous appelons la méthode `MathRenderer.Render()` elle-même, en passant les options comme troisième argument. Le code LaTeX de la formule est transmis sous forme de chaîne via le premier argument.

Les dernières lignes de l'exemple impriment deux artefacts de rendu de formule mathématique : la taille de la formule et le bref rapport d'erreur (au cas où il y aurait des erreurs).

Il s’agit du cas d’utilisation le plus général du rendu de formules mathématiques LaTeX.

**Vous pouvez également consulter l'[application Web](https://products.aspose.app/tex/mathrenderer) gratuite construite sur la base de la fonctionnalité implémentée dans [Aspose.TeX pour l'API C++](https://products.aspose.com/tex/cpp/).**