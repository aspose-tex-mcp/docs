---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: funcionalidad de composición tipográfica TeX | .NET
url: /net/typeset-tex-files/
description: "Solución API .NET para trabajar con TeX. Aprenda en el ejemplo cómo crear composiciones tipográficas TeX con unas pocas líneas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Componer archivos TeX
h2: "Escriba un archivo TeX usando un formato TeX personalizado C# .NET"
---

{{<section overview>}}
---
p1: "TeX es conocido como uno de los lenguajes de marcado de datos y/o un lenguaje de composición tipográfica al mismo tiempo. Significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos. Como salida, obtendrá el archivo formateado del formato necesario (especificado). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) es el núcleo central del sistema de conjuntos de publicaciones (composición tipográfica por computadora)."
p2: "Para comprender mejor la composición tipográfica de TeX, aprenda [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación. Y en esta página encontrará fragmentos de código que explican cómo componer un archivo TeX utilizando un formato TeX personalizado."
p3: "Para ejecutar los ejemplos necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: Pasos para componer TeX usando C#.
h3: "Código C# para escribir TeX"
item1: "Cree el proveedor de formato mediante la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Cree opciones de conversión para un formato personalizado en la extensión del motor ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase."
item3: "Especifique el directorio de trabajo de entrada si la entrada principal no se proporciona como una secuencia. Utilice la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para esto."
item4: "Especifique un directorio de trabajo del sistema de archivos para la salida. Utilice la clase [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) para esto."
item5: "Ejecute el trabajo [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Refinar la salida.
---