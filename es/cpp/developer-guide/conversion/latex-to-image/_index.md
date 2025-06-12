---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX a la imagen | Aspose.TeX para C++
linktitle: LaTeX a imagen
weight: 10
url: /cpp/latex-to-image/
keywords: látex a png, látex png, látex a imagen, imagen de látex, látex a jpg, látex jpg, látex a jpeg, látex jpeg, látex a tiff, látex tiff, látex a bmp, látex bmp
description: Para convertir TeX a formatos de imagen utilizando la Aspose.TeX paraC++, lea este artículo que describe cómo hacerlo y los ejemplos de código.
lastmod: 2023-03-23
---

{{<section overview>}}

**Aspose.TeX para C++** también nos permite convertir archivos LaTeX a otros formatos de imágenes rasterizadas.

## Cómo convertir LaTeX a PNG

Echemos un vistazo detallado al código en C++ que proporciona la forma más sencilla de convertir LaTeX a formato PNG.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Entonces, lo primero que debemos hacer (bueno, a veces no lo primero) es crear una instancia de la clase [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). El único método estático que hace esto es [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), así que no nos dejemos desconcertar por el significado de su nombre. El método toma la [instancia get_ObjectLaTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) de la clase [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), que es exactamente adecuada para convertir un [archivo LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Esta configuración le dice al motor Object TeX que cargue el formato Object LaTeX y que esté listo para aceptar el archivo LaTeX. El formato Object LaTeX es en realidad solo el formato [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), excepto que utiliza primitivas específicas de [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) para configurar las métricas de la página.

La primera de las opciones requeridas es [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) que define el espacio o área donde se escribirá la salida TeX. [Aquí](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) se encuentran los detalles sobre el concepto de directorio de salida en **Aspose.TeX para C++**. En este ejemplo, usamos la clase [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), que nos permite escribir la salida en el directorio o carpeta especificado.

La segunda opción es una instancia de clase [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/) que controlará la transformación del [modelo de objeto](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) al formato de destino. Dado que estamos convirtiendo LaTeX a PNG, es la instancia de clase [PngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), que nos permite especificar la resolución de las imágenes de salida.

A continuación, necesitamos crear una instancia de la clase [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Al querer convertir un archivo LaTeX almacenado en el sistema de archivos, utilizamos [esta](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) versión del constructor. Necesitamos especificar la ruta completa al archivo. De lo contrario, el motor lo buscará en el directorio actual (que es [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) y lo más probable es que no lo encuentre. No obstante, podremos omitir la extensión si nuestro archivo tiene la *.tex*. El motor lo agregará automáticamente. El segundo argumento del constructor es una instancia de clase [Dispositivo](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Dado que estamos convirtiendo LaTeX a PNG, es una instancia de clase [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) (que es común a todos los formatos de imagen admitidos). Como último argumento, pasamos las opciones de conversión preparadas recientemente.

Todo lo que queda por hacer ahora es [ejecutar](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb) el trabajo.

Independientemente de si la ejecución fue exitosa o no, el primer resultado que veremos será la salida del terminal. En caso de éxito, se verá así:

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

Encontraremos otros "frutos" del trabajo del motor en la carpeta que especificamos como directorio de salida. Esos serán el archivo de transcripción y, **¡aquí está!**, los archivos de imagen PNG de salida principal.

## Una forma alternativa de escribir los archivos PNG de salida principales

Hay otra forma de obtener datos de imagen como una matriz de matrices de bytes; cada matriz en la segunda dimensión representa datos de imagen para una página separada.

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

Los archivos *"page-n.png"* se escribirán en cualquier ruta que especifiquemos. A diferencia de [Salida PDF](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), duplicarán los archivos PNG de salida escritos en el directorio de salida.

## Acerca de las opciones de entrada

En caso de que nuestro archivo de entrada principal requiera dependencias, por ejemplo, paquetes, que no están incluidos en el sistema LaTeX básico y los paquetes compatibles, DEBEMOS configurar la opción [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) de la misma manera que configuramos [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory). opción y coloque las dependencias en ese directorio. Las dependencias pueden organizarse arbitrariamente en subdirectorios. En caso de que tengamos nuestros propios archivos para incluir durante el proceso de composición tipográfica, digamos archivos de gráficos externos, DEBEMOS también configurar [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory) usando la ruta a la ubicación donde se recopilan esos archivos. También podemos colocar el archivo de entrada principal en algún lugar dentro del directorio de entrada y especificar la ruta relativa en el método `run()` (o no especificar ninguna ruta si el archivo de entrada principal está en la raíz). [Aquí](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) se encuentran los detalles sobre el concepto de directorio de entrada en **Aspose.TeX para C++** y las implementaciones proporcionadas.

Otras opciones de trabajo en TeX se analizan [aquí](/tex/{{lang.url-fragment}}cpp/other-options/).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-png) gratuita de conversión de LaTeX a PNG creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/cpp/) está la página de la versión C++.**

A continuación, analizamos la conversión de LaTeX a otros formatos de imágenes rasterizados compatibles. No entraremos en detalles sólo porque en realidad no hay ningún detalle. La única diferencia está en el tipo de propiedad [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) en las opciones de conversión.

## Cómo convertir LaTeX a JPEG

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-jpg) gratuita de conversión de LaTeX a JPEG creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/cpp/) es la página de la versión C++.**

## Cómo convertir LaTeX a TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-tiff) gratuita de conversión de LaTeX a TIFF creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/cpp/) es la página de la versión C++.**

## Cómo convertir LaTeX a BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-bmp) gratuita de conversión de LaTeX a BMP creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/cpp/) está la página de la versión C++.**