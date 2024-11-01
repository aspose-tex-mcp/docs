---
translation: true
template: /templates/_template-cpp.md
title: Látex a XPS | Aspose.TeX para C++
linktitle: Látex a XPS
weight: 12
url: /cpp/latex-to-xps/
description: La funcionalidad de conversión de la solución API Aspose.TeX para C++ permite convertir archivos LaTeX al formato XPS.
lastmod: "2024-10-30"
---

{{<section overview>}}

Otro formato de destino admitido por **Aspose.TeX** es [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Un archivo **XPS** es en realidad un paquete ZIP que contiene el contenido paginado de un documento, junto con los metadatos necesarios para que visores específicos (como Windows XPS Viewer) lo muestren correctamente y lo impriman. Todos los datos de un paquete están representados por archivos. Algunos de ellos son binarios y contienen recursos como imágenes, fuentes y perfiles ICC. Otros son archivos XML en varios esquemas específicos. Estos últimos incluyen archivos que contienen los datos del documento en sí. Los datos del documento constan de un conjunto de archivos: cada archivo contiene datos para una página individual del documento. Dichos archivos constan de un único elemento de página y un árbol de elementos secundarios: *Canvas*, *Path* y *Glyphs*. *Canvas* es un elemento de agrupación que puede contener otros *Canvases*, *Paths* y *Glyphs*. Su misión es controlar la apariencia de todos los elementos secundarios como grupo. Los elementos *Path* se utilizan para definir rutas de gráficos vectoriales. Y los elementos *Glifos* se utilizan para definir el contenido textual. Los tres elementos tienen propiedades para definir varios aspectos de la apariencia.

Existe la biblioteca [**Aspose.Page**](https://products.aspose.com/page/) que proporciona una API para manipular documentos XPS, así como convertirlos a formatos PDF y de imágenes rasterizadas.

## Cómo convertir LaTeX a XPS

La conversión a XPS es tan simple como la [conversión a formatos de imagen rasterizada](/tex/{{lang.url-fragment}}cpp/latex-to-image/), excepto que además de [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions), tenemos que cambiar el dispositivo a una instancia de [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device) clase.

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Una forma alternativa de escribir el archivo XPS de salida principal

Hay otro constructor de la clase [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), que nos permite obtener el archivo XPS resultante de una forma alternativa.

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

El efecto es el mismo que obtenemos [aquí](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex-to-xps) gratuita de conversión de LaTeX a XPS creada en base a la API [Aspose.TeX para .NET](https://products.aspose.com/tex/net/). [Aquí](https://products.aspose.com/tex/cpp/) es la página de la versión C++.**