---
translation: true
template: /_templates/_customize-output-net.md
title: Crear salida personalizada TeX | API .NET
url: /net/customize-output/
description: "Solución API .NET para trabajar con TeX. Lea el ejemplo sobre cómo crear una salida personalizada para un archivo TeX con unas pocas líneas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personalizar salida
h2: "Solución API .NET para personalizar la salida de archivos TeX"
---

{{<section overview>}}
---
p1: "TeX es conocido como un lenguaje de composición tipográfica. Significa que no formatea su texto en el documento, sino que ingresa el texto sin formato junto con los comandos."
p2: "El artículo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentación nos enseña que un archivo TeX puede no contener ningún dato para componer sino solo secuencias de control . Sin embargo, normalmente contiene dichos datos, y un archivo en el formato de destino tiene el texto compuesto. El archivo también tendrá el mismo nombre que el archivo especificado como entrada y es el archivo de salida principal. Para el TeX original, este es un archivo en formato DVI. Llamaremos el nombre de los archivos de entrada y salida sin extender el nombre del trabajo."
p3: "En esta página, encontrará un ejemplo de código que explica la creación de un archivo de formato TeX personalizado donde puede ver cómo personalizar la salida de los archivos TeX. Para personalizar la salida de archivos .tex necesitamos:"
p4: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p5: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: "Pasos para personalizar la salida de TeX C#:"
h3: "Código C# para la personalización de salida de TeX"
item1: "Con la ayuda del método [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Clase, crea opciones de motor TeX sin formato en la extensión del motor ObjectTeX."
item2: "Utilice la clase [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para especificar un directorio de trabajo del sistema de archivos para la entrada."
item3: "Utilice la clase [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) para especificar un directorio de trabajo del sistema de archivos para la salida."
item4: "Para crear el nuevo formato, use el método [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Refinar la salida.
---