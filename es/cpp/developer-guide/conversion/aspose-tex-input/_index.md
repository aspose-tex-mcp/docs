---
translation: true
template: /templates/_template-cpp.md
title: Interfaz de entrada de Aspose.TeX | C++
linktitle: Interfaz de entrada de Aspose.TeX
weight: 15
url: /cpp/aspose-tex-input/
description: La funcionalidad de conversión de la solución API Aspose.TeX para C++ con TeX, como formato de entrada, se explica aquí con los ejemplos de código.
lastmod: "2026-04-20"
---

{{<section overview>}}

Consulte **Aspose.TeX para C++** [referencia de API](https://reference.aspose.com/tex/cpp/aspose.tex.io/) para obtener definiciones formales de implementación de E/S.

## El concepto del directorio de entrada.
Dado que las primitivas de E/S del lenguaje TeX solo pueden tratar con nombres de archivos, **Aspose.TeX para C++** define un directorio como una asignación entre nombres y grandes cantidades de datos. Se supone que la gran cantidad de datos son archivos, secuencias, matrices o cualquier otra cosa. La API nos permite especificar los directorios de trabajo de entrada y salida por separado. Proporciona la interfaz general [IInputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory/), que el usuario puede implementar para sus propios fines. También proporciona sus propias implementaciones, que se analizarán a continuación. La interfaz define el método [GetFile()](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputworkingdirectory#adc0d6f35f9a0c426ba010779d90b5cd6), que devuelve el flujo de datos y determina el nombre completo del archivo, mientras toma algún nombre, hipotéticamente diferente, como primer argumento, que, de hecho, es la clave de mapeo. .

### Obtener entrada de archivos del sistema de archivos del disco

Así es como lo haríamos:

```C++
// Create conversion options instance.
...
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
```

Este caso de uso es bastante simple, por lo que ya no es necesario centrarse en él.

### Obtener entrada de archivo desde un archivo ZIP

También podemos poner los archivos de entrada en un archivo ZIP y considerarlo un directorio de entrada. En este caso debemos proceder de la siguiente manera:

```C++
    // Open a stream on a ZIP archive that will serve as the input working directory.
    System::SharedPtr<System::IO::Stream> inZipStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::InputDirectory, u"zip-in.zip"), System::IO::FileMode::Open);

    // Create conversion options instance.
    ...
    // Specify a ZIP archive working directory for input.
    options->set_InputWorkingDirectory(System::MakeObject<InputZipDirectory>(inZipStream, u"in"));
```

Primero, creamos la secuencia que contiene el archivo ZIP. Luego, después de crear las opciones de conversión, configuramos la opción [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory/) para que sea una instancia de la clase [InputZipDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputzipdirectory/). El segundo argumento del constructor es la ruta base dentro del archivo. Si queremos que todo el archivo sea un directorio de entrada, debemos pasar la cadena vacía. 

## El concepto de terminal de entrada.

Ahora toca recordar que también está la entrada del terminal. En cuanto a este, **Aspose.TeX para C++** define la interfaz general [IInputTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/iinputterminal/) que tiene solo una propiedad que devuelve una instancia de implementación [TextReader](https://reference.aspose.com/tex/cpp/system.io/textreader/). Las implementaciones proporcionadas se analizan a continuación.

### Obtener entrada de terminal desde la consola

Para hacer esto, necesitamos configurar la opción [TerminalIn](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_terminalin/) para que sea una instancia de la clase [InputConsoleTerminal](https://reference.aspose.com/tex/cpp/aspose.tex.io/inputconsoleterminal/).

```C++
// Create conversion options instance.
...
// Specify the console as the input terminal.
options->set_TerminalIn(System::MakeObject<InputConsoleTerminal>()); // Default. Not necessary to specify.

```

Pero, a decir verdad, este es el valor predeterminado de la opción, por lo que no es necesario especificarlo. :-) Debido a este hecho, y mientras no existan otras implementaciones, esta sección sirve únicamente para fines de demostración.

En teoría, si tenemos un archivo (o secuencia de comandos) TeX interactivo con un comportamiento predecible, es posible que deseemos implementar una versión del terminal de entrada que contenga una secuencia de comandos complementaria para responder a las solicitudes del motor TeX. ¡Prueba suerte cuando tengas tiempo!