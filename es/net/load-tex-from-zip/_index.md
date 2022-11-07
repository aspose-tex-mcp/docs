---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Cargando TeX desde ZIP | Solución API .NET
url: /net/load-tex-from-zip/
description: "Solución API .NET para trabajar con TeX. Aprenda en el ejemplo cómo cargar un archivo TeX desde ZIP con unas pocas líneas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Cargue archivos fuente TeX desde ZIP
h2: "Solución API .NET para cargar archivos TeX desde un archivo ZIP"
---

{{<section overview>}}
---
p1: "TeX es conocido como un lenguaje de composición tipográfica. Significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos. Como salida, obtendrá el archivo formateado del formato necesario (especificado). Para comprender mejor la entrada y salida de TeX, aprenda [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación."
p2: "Como se sabe, el propósito principal de TeX es ayudar a crear textos matemáticos o técnicos. Pero antes de cualquier manipulación, primero se debe cargar el archivo. Aquí encontrará fragmentos de código que explican cómo cargar archivos fuente TeX desde ZIP utilizando directorios ZIP para entrada y salida, salida a dispositivo PDF, escritura de salida de terminal en consola."
p3: "Para cargar archivos .tex necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: "Pasos para cargar TeX desde un archivo ZIP C#:"
h3: "Código C# para cargar TeX"
item1: "Abra el flujo en el archivo ZIP para usarlo como directorio de trabajo de entrada."
item2: "Abra el flujo en el archivo ZIP para usarlo como directorio de trabajo de salida."
item3: "Cree opciones de conversión para el formato ObjectTeX predeterminado en la extensión del motor ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase."
item4: "Especifique un directorio de trabajo de archivo ZIP para la entrada o especifique una ruta dentro del archivo. Use constructores de la clase [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) para esto."
item5: "Especifique un directorio de trabajo de archivo ZIP para la salida o especifique una ruta dentro del archivo. Use constructores de la clase [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) para esto."
item6: "Especifique la consola como terminal de salida usando la clase [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Defina las opciones de guardado usando la clase [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Ejecute el trabajo [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Refinar la salida.
---