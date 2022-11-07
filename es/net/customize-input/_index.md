---
translation: true
template: /_templates/_customize-input-net.md
title: Crear entrada personalizada TeX | API .NET
url: /net/customize-input/
description: "Solución API .NET para trabajar con TeX. Aprenda en el ejemplo cómo crear una entrada personalizada para el archivo TeX con unas pocas líneas de código C#."
keywords: entrada personalizada tex net api, C# api para personalizar tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizar entrada
h2: "Solución API .NET para personalizar la entrada de archivos TeX"
---

{{<section overview>}}
---
p1: "TeX es conocido como un lenguaje de composición tipográfica. Significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos. Como se describe en el artículo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación, el trabajo TeX se ejecuta en un archivo TeX especificado explícitamente. Entonces, incluimos este archivo en la entrada de cierto trabajo de TeX."
p2: "En esta página encontrará un ejemplo de código que explica cómo personalizar la entrada de los archivos fuente de TeX teniendo en cuenta que la entrada debe seguir la sintaxis de TeX e, idealmente, contener solo comandos conocidos por el motor."
p3: "Para personalizar la entrada de archivos .tex necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: "Pasos para personalizar la entrada TeX C#:"
h3: "Código C# para la personalización de entrada de TeX"
item1: "Usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase, crea opciones de motor TeX sin formato en la extensión del motor ObjectTeX."
item2: "Utilizando la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), especifique un directorio de trabajo del sistema de archivos para la entrada."
item3: "Con la ayuda del método [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), cree el formato personalizado."
---