---
translation: true
template: /_templates/_output-to-disk-net.md
title: Escribir la salida TeX en el disco | API .NET
url: /net/output-to-disk/
description: "Solución API .NET para trabajar con TeX. Aprenda en el ejemplo cómo crear una salida personalizada para un archivo TeX con unas pocas líneas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Escribir la salida TeX en el disco
h2: "Guarde el resultado de la conversión de archivos TeX como disco a través de C# .NET"
---

{{<section overview>}}
---
p1: "TeX se conoce como un lenguaje de composición tipográfica, lo que significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos. Como se sabe por el artículo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación, el trabajo TeX se ejecuta en un archivo TeX especificado explícitamente. Allí también puede encontrar información sobre los modos de interacción de TeX y las primitivas relacionadas con la entrada y salida de TeX."
p2: "El uso principal de TeX es ayudar con la creación de textos matemáticos o técnicos. Pero cuando el archivo ya está creado y no desea manipularlo más, es posible que desee convertirlo a un formato diferente y más popular."
p3: "En esta página, encontrará un ejemplo de código que explica el uso de directorios del sistema de archivos para la entrada y la salida, la salida al dispositivo XPS, la anulación del nombre del trabajo y la escritura de la salida del terminal en el disco. En palabras simples, es una conversión con la escritura de la salida en el disco. Para ejecutar dicha operación necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: "Pasos para escribir la salida del terminal en el disco C#:"
h3: "Código C# para convertir TeX y escribir la salida en el disco"
item1: "Cree opciones de conversión sobre la extensión del motor ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase."
item2: "Especifique un nombre de trabajo si no desea que el primer argumento del constructor TeXJob se tome como nombre de trabajo."
item3: "Especifique un directorio de trabajo del sistema de archivos para la entrada. Utilice la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para esto."
item4: "Especifique un directorio de trabajo del sistema de archivos para la salida con la ayuda de las entidades de la clase [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Especifique que la salida del terminal debe escribirse en un archivo en el directorio de trabajo de salida."
item6: "Ejecute el trabajo [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---