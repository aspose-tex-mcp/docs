---
translation: true
template: /_templates/_create-custom-tex-net.md
title: Archivos TeX personalizados | Solución API .NET
url: /net/create-custom-tex/
description: "API .NET para trabajar con TeX. Incluye la funcionalidad para crear formatos TeX personalizados. Ejemplos de funcionalidad en C# para personalizar TeX."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Crear formato TeX personalizado
h2: "Cree un archivo de formato TeX personalizado a través de C# .NET"
---

{{<section overview>}}
---
p1: "TeX es conocido como uno de los lenguajes de marcado de datos. Es el núcleo principal del sistema de conjuntos de publicaciones (composición tipográfica por computadora). Es cuestionable considerar [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) como un formato de archivo, porque es un lenguaje de programación. Y por otro lado, es un motor de interpretación que entiende este lenguaje. De todos modos, en definitiva, su finalidad principal es ayudar en la creación de textos matemáticos o técnicos. Se han creado muchos paquetes diferentes sobre la base de ΤeΧ. Su objetivo es facilitar el procesamiento de los documentos, especialmente cuando tienen fórmulas o ecuaciones matemáticas."
p2: "La solución API de Aspose.TeX, entre otras funciones diferentes, permite crear sus propios archivos TeX destacados. Aquí encontrará información que explica cómo crear archivos de un formato tan personalizado. Dicho archivo tendrá las opciones de motor personalizadas. Para esto necesitamos:"
p3: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p4: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: Pasos para crear un archivo TeX personalizado C#.
h3: "Código C# para personalizar archivos TeX"
item1: "Usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase, crea opciones de motor TeX sin formato en la extensión del motor ObjectTeX."
item2: "Utilizando la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), especifique un directorio de trabajo del sistema de archivos para la entrada."
item3: "Utilice la clase [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) para especificar un directorio de trabajo del sistema de archivos para la salida."
item4: "Cree el formato usando el método [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Refinar la salida.
---