---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX a ZIP | Solución API .NET
url: /net/output-to-zip/
description: "Solución API .NET para trabajar con TeX. La funcionalidad de conversión de TeX a ZIP le permite guardar su archivo TeX como el archivo más popular. Ejemplos en C# de esta funcionalidad."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Escribir salida en ZIP
h2: "Guarde el resultado de la conversión de archivos TeX como ZIP a través de C# .NET"
---

{{<section overview>}}
---
p1: "TeX es conocido como uno de los lenguajes de marcado de datos. Es el núcleo principal del sistema de conjuntos de publicaciones (composición tipográfica por computadora). Es cuestionable considerar [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) como un formato de archivo, porque es un lenguaje de programación. Y por otro lado, es un motor de interpretación que entiende este lenguaje. De todos modos, en definitiva, su finalidad principal es ayudar en la creación de textos matemáticos o técnicos. Pero cuando el archivo ya está creado y no desea manipularlo más, es posible que desee convertirlo a un formato diferente y más popular."
p2: "La solución API Aspose.TeX, entre otras características diferentes, permite la conversión de archivos TeX y luego guardar el resultado como un archivo ZIP. Aquí encontrará un fragmento de código sobre cómo convertir TeX a PDF y guardar la salida del resultado en zip. El convertidor de API transforma TeX utilizando cualquier lenguaje compatible con C#. La API que ve aquí también puede usarse para crear su propia aplicación multiplataforma o integrarse en su proyecto .NET. Dichos [*conversores multiplataforma*](https://products.aspose.app/tex/conversion/tex) también están presentes en el ecosistema de Aspose. Pero para ejecutar los ejemplos necesitamos:"
p3: "Aspose.TeX para .NET API, que es una API de conversión y manipulación de documentos rica en funciones, potente y fácil de usar para la plataforma C#."
p4: "Abra el administrador de paquetes NuGet, busque Aspose.TeX e instálelo. También puede usar el siguiente comando desde la Consola del administrador de paquetes."
---

{{<section feature1>}}
---
title: Pasos para usar directorios ZIP para el archivo TeX de salida C#.
h3: "Código C# para usar directorios ZIP para la salida"
item1: "Cree la instancia de [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Especifique un directorio de trabajo de archivo ZIP para la salida usando la propiedad [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Especifique la consola como terminal de salida mediante la clase [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Defina las opciones para guardar usando la clase [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Ejecute la conversión utilizando el método [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) para [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Refinar la salida.
item7: "Para finalizar el archivo ZIP de salida, use la clase [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---