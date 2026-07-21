---
translation: true
template: /templates/_template-cpp.md
title: Otras formas de proporcionar el archivo de entrada TeX principal| C++
linktitle: Proporcionar el archivo de entrada TeX principal
weight: 14
url: /cpp/other-ways-of-main-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para C++ tiene un constructor que acepta una secuencia como primer argumento. Aquí hay algunos ejemplos de código.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Proporcionar el archivo de entrada principal al motor TeX como una secuencia

Hasta este punto, sólo sabíamos cómo pasar el [archivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motor TeX como un nombre de archivo, ya sea completamente especificado o en formato corto, con o sin extensión. Pero hay otro [constructor](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) de la clase `TeXJob`, que toma una secuencia como primer argumento. Esto es conveniente si por alguna razón tenemos el archivo de entrada principal en un formato que no sea un archivo en el sistema de archivos del disco. Así es como se puede implementar:

```C++
// Create conversion options instance.
...
// Create some device.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(
    u"\\documentclass{article} \\begin{document} Hello, World! \\end{document}")), device, options)->Run();
```

Tenga en cuenta que todos los archivos de salida tendrán el nombre *texput*. Esto se debe a que el motor no puede recibir ningún otro nombre en ninguna parte. *texput* es el nombre del trabajo predeterminado. [Aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) y [aquí](/tex/{{lang.url-fragment}}cpp/other-options/#how-to-set-the-job-name) son detalles sobre los nombres de los trabajos.

## Ingresando el archivo de entrada TeX principal desde la terminal

Hay otro [constructor](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) de la clase `TeXJob`, que no nos permite especificar la entrada en absoluto. Entonces, ¿qué va a procesar un trabajo TeX de este tipo?, te preguntarás. Esta vez necesitaremos un terminal de entrada. El motor TeX nos pedirá que introduzcamos el nombre del archivo desde la terminal.

Aquí está el código:

```C++
// Create conversion options instance.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<XpsDevice>(), options)->Run();
```

Tan pronto como se ejecuta, el motor se queda esperando a que introduzcamos el nombre del archivo (con o sin ruta, con o sin extensión):


![Ventana de terminal](/tex/images/cpp/Conversion-MainInputTerminal.png)

Y así quedaría en el terminal de salida que es la consola:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```