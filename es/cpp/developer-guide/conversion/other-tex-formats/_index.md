---
translation: true
template: /templates/_template-cpp.md
title: Otros formatos de salida de conversión TeX | C++
linktitle: Otros formatos TeX
weight: 18
url: /cpp/other-tex-formats/
description: La funcionalidad de conversión de la solución API Aspose.TeX para C++ permite convertir archivos LaTeX y sus propios archivos TeX personalizados.
lastmod: "2024-10-30"
---

{{<section overview>}}

Es muy poco probable que actualmente quieras convertir un archivo TeX escrito en cualquier otro formato que no sea LaTeX. Pero esto es posible si estás estudiando el lenguaje TeX y/o sus aspectos internos por algún motivo. De todos modos, **Aspose.TeX para C++** te permite convertir archivos escritos en formato Plain TeX. También le permite crear formatos personalizados y componer documentos diseñados en estos formatos.

Comenzaremos creando un formato personalizado.

## Creando un formato personalizado

Recordemos que el archivo de formato es un volcado binario del estado interno del motor TeX.

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

Como puede ver, el código es similar al código para convertir un archivo TeX. Pero hay algunas diferencias.

Primero, aquí usamos la configuración del trabajo [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Se trata de una configuración especial que deja el estado del motor "virgen", es decir, los parámetros internos tienen sus valores por defecto y el conjunto de secuencias de control coincide con el conjunto de primitivas. En nuestro ejemplo, el conjunto de primitivas se amplía en el sentido mencionado [aquí](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

A continuación, configuramos los directorios de trabajo de entrada y salida como de costumbre. El directorio de trabajo de entrada debe contener el archivo fuente del formato principal y todas sus dependencias.

Y la segunda diferencia clave es la forma en que ejecutamos el trabajo. En esta ocasión utilizamos el método estático [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), que junto con las opciones toma el nombre del archivo fuente principal, que debe ser el mismo que el nombre del formato.

## Componer un archivo TeX en su formato personalizado

Ahora que tenemos nuestro propio formato TeX, queremos componer un archivo TeX escrito en este formato. Aquí está el código:

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

Obviamente, tenemos que especificar el formato de alguna manera. En primer lugar, necesitamos crear una instancia de la clase [FormatProvider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/). Luego, en el constructor de opciones, usamos la configuración [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), que toma nuestro proveedor de formato como argumento y carga el formato encima del estado "virgen" del motor.

El resto del código debería resultarle familiar. Utiliza las características analizadas anteriormente en esta [guía](/tex/{{lang.url-fragment}}cpp/conversion/).

## Composición tipográfica de un archivo TeX en formato Plain TeX

Si descartamos el proveedor de formato del código que acabamos de demostrar, el motor cargará el formato predeterminado, que es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) en su cuarto sentido. Por lo tanto, si tiene un archivo TeX escrito en formato Plain TeX, de esta manera puede convertirlo a cualquier formato de destino compatible.