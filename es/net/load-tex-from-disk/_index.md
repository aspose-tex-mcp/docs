---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Cargando TeX desde un disco | Solución API .NET
url: /net/load-tex-from-disk/
description: "Solución API .NET para trabajar con TeX. Aprenda en el ejemplo cómo cargar un archivo TeX desde el disco con unas pocas líneas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Cargar archivos fuente TeX desde el disco
h2: "Solución API .NET para cargar archivos TeX/LaTeX desde el disco"
---

{{<section overview>}}
---
p1: "TeX es conocido como un lenguaje de composición tipográfica. Significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos. Como salida, obtendrá el archivo formateado del formato necesario (especificado). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) es el núcleo central del sistema de conjuntos de publicaciones (composición tipográfica por computadora). Un trabajo TeX se ejecuta en un archivo TeX especificado explícitamente. Para comprender mejor la entrada y salida de TeX, aprenda [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación."
p2: "Como se sabe, el propósito principal de TeX es ayudar a crear textos matemáticos o técnicos. Pero antes de cualquier manipulación, primero se debe cargar el archivo. Aquí encontrará fragmentos de código que explican cómo cargar archivos fuente de TeX desde el disco utilizando directorios del sistema de archivos para entrada y salida, salida al dispositivo XPS, escritura de la salida del terminal en la consola."
p3: "Para ejecutar los ejemplos necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: Pasos para cargar TeX desde un disco C#.
h3: "Código C# para cargar TeX"
item1: "Cree opciones de conversión para un formato personalizado en la extensión del motor ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase."
item2: "Especifique un directorio de trabajo del sistema de archivos para la entrada. Utilice la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para esto."
item3: "Especifique un directorio de trabajo del sistema de archivos para la salida mediante [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) Class."
item4: "Especifique la consola como terminal de salida usando la clase [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Especifique un terminal de memoria como terminal de salida si lo necesita. Para esto, use la clase [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Ejecute el trabajo [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Refinar la salida.
---