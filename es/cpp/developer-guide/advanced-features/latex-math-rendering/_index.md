---
translation: true
template: /templates/_template-cpp.md
title: Representación de fórmulas matemáticas LaTeX | C++
linktitle: Representación de fórmulas matemáticas LaTeX
weight: 10
url: /cpp/latex-math-formula-rendering/
description: En este artículo se describe la solución API Aspose.TeX para la representación de fórmulas matemáticas C++ LaTeX. Aquí encontrará ejemplos de código de la funcionalidad.
lastmod: "2024-10-30"
---

{{<section overview>}}

La sección de referencia de API relacionada con este tema está [aquí](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features). De hecho, la forma más sencilla de demostrar la función de representación de fórmulas matemáticas de LaTeX es comenzar con el ejemplo. Aquí lo tienes:

```C++
    // Create rendering options 
    System::SharedPtr<PngMathRendererOptions> options = System::MakeObject<PngMathRendererOptions>();
    // Sspecify the image resolution 150 dpi
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

Vayamos a los detalles. En primer lugar, creamos una instancia de [opciones de renderizado](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions), similar a la composición tipográfica TeX/LaTeX. Lo hacemos aquí especificando simultáneamente la resolución de la imagen de salida.

A continuación, especificamos el preámbulo. El preámbulo predeterminado es:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que proporciona un soporte de fórmulas matemáticas ligeramente más avanzado que el LaTeX básico. Puede, por ejemplo, agregar el paquete `color` si desea utilizar su propio resaltado en la fórmula, como mostramos en el ejemplo de código.

Luego le indicamos al renderizador que escale la salida en un 300%.

Las siguientes dos opciones definen los colores de primer plano y de fondo. Aquellas partes de la fórmula que no estén cubiertas ("coloreadas") por el resaltado personalizado se mostrarán en el color "TextColor".

La siguiente línea del ejemplo no tiene mucho sentido. Simplemente demuestra que puede dirigir la salida del registro a alguna secuencia.

Y la última opción `ShowTerminal` le permite alternar la escritura de la salida del terminal en la consola.

El método que realmente realiza la renderización es [MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render). Devuelve el tamaño de la fórmula en puntos.

El método toma la secuencia donde se escribirá la imagen como segundo argumento. Creamos la secuencia a continuación.

Y finalmente, llamamos al método `MathRenderer.Render()`, pasando opciones como tercer argumento. El código LaTeX de la fórmula se pasa como una cadena a través del primer argumento.

Las últimas líneas del ejemplo imprimen dos artefactos de la representación de fórmulas matemáticas: el tamaño de la fórmula y el breve informe de errores (en caso de que haya errores).

Este es el caso de uso más general para la representación de fórmulas matemáticas LaTeX.

**También puede consultar la [aplicación web](https://products.aspose.app/tex/mathrenderer) gratuita creada en función de la función implementada en [Aspose.TeX para C++ API](https://products.aspose.com/tex/cpp/).**