---
translation: true
template: /templates/_template-net.md
title: Otros formatos de salida de conversión TeX | .NET
linktitle: Otros formatos TeX
weight: 18
url: /net/other-tex-formats/
description: La funcionalidad de conversión de la solución API Aspose.TeX para .NET permite convertir archivos LaTeX y sus propios archivos TeX personalizados.
lastmod: "2026-04-22"
---

{{<section overview>}}

Es muy poco probable que actualmente quieras convertir un archivo TeX escrito en cualquier otro formato que no sea LaTeX. Pero esto es posible si estás estudiando el lenguaje TeX y/o sus aspectos internos por algún motivo. De todos modos, **Aspose.TeX para .NET** le permite convertir archivos escritos en formato Plain TeX. También le permite crear formatos personalizados y componer documentos diseñados en estos formatos.

Comenzaremos creando un formato personalizado.

## Creando un formato personalizado

Recordemos que el archivo de formato es un volcado binario del estado interno del motor TeX.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-CreateCustomFormat.cs" >}}

Como puede ver, el código es similar al código para convertir un archivo TeX. Pero hay algunas diferencias.

Primero, aquí usamos la configuración del trabajo [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectinitex/). Se trata de una configuración especial que deja el estado del motor "virgen", es decir, los parámetros internos tienen sus valores por defecto y el conjunto de secuencias de control coincide con el conjunto de primitivas. En nuestro ejemplo, el conjunto de primitivas se amplía en el sentido mencionado [aquí](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

A continuación, configuramos los directorios de trabajo de entrada y salida como de costumbre. El directorio de trabajo de entrada debe contener el archivo fuente del formato principal y todas sus dependencias.

Y la segunda diferencia clave es la forma en que ejecutamos el trabajo. En esta ocasión utilizamos el método estático [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), que junto con las opciones toma el nombre del archivo fuente principal, que debe ser el mismo que el nombre del formato.

## Componer un archivo TeX en su formato personalizado

Ahora que tenemos nuestro propio formato TeX, queremos componer un archivo TeX escrito en este formato. Aquí está el código:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-TypesetWithCustomFormat.cs" >}}

Obviamente, tenemos que especificar el formato de alguna manera. En primer lugar, necesitamos crear una instancia de la clase [FormatProvider](https://reference.aspose.com/tex/net/aspose.tex.resourceproviders/formatprovider/). Luego, en el constructor de opciones, usamos la configuración [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objecttex/), que toma nuestro proveedor de formato como argumento y carga el formato encima del estado "virgen" del motor.

El resto del código debería resultarle familiar. Utiliza las características analizadas anteriormente en esta [guía](/tex/{{lang.url-fragment}}net/conversion/).

## Composición tipográfica de un archivo TeX en formato Plain TeX

Si descartamos el proveedor de formato del código que acabamos de demostrar, el motor cargará el formato predeterminado, que es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) en su cuarto sentido. Por lo tanto, si tiene un archivo TeX escrito en formato Plain TeX, de esta manera puede convertirlo a cualquier formato de destino compatible.
