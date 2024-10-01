---
translation: true
template: /templates/_template-python-net.md
title: Otros formatos de salida de conversión TeX | Pitón
linktitle: Otros formatos TeX
weight: 18
url: /python-net/other-tex-formats/
description: La solución API Aspose.TeX para Python proporciona una funcionalidad que le permite convertir archivos LaTeX y archivos TeX personalizados. A continuación se muestran algunos ejemplos de código.
lastmod: "2024-10-30"
---

{{<section overview>}}

Es poco probable que actualmente necesites convertir un archivo TeX escrito en un formato que no sea LaTeX. Sin embargo, si por algún motivo estás estudiando el lenguaje TeX o las partes internas de TeX, todavía es posible. En cualquier caso, **Aspose.TeX para Python** le permite convertir archivos escritos en formato *Plain TeX* y también le permite crear formatos personalizados y componer documentos diseñados en estos formatos.

Para comenzar, crearemos un formato personalizado.

## Creando un formato personalizado

Tengamos en cuenta que el archivo de formato es una representación binaria del estado interno del motor TeX.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

Como puede ver, el código se parece al código para convertir un archivo TeX. Sin embargo, hay algunas distinciones.

En primer lugar, en este caso, utilizamos la configuración del trabajo [TeXConfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/). Esta configuración garantiza que el estado del motor sea "virgen", lo que significa que los parámetros internos tienen sus valores predeterminados y el conjunto de secuencias de control se alinea con el conjunto de primitivas. En nuestro ejemplo, el conjunto de primitivas se amplía [en el artículo Aspose.TeX y Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

A continuación, procedemos a configurar los directorios de trabajo de entrada y salida como de costumbre. El directorio de trabajo de entrada debe incluir el archivo fuente del formato principal y todas sus dependencias.

Y la segunda gran diferencia es el método mediante el cual ejecutamos el trabajo. En este caso, utilizamos el método estático [create_format()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions), que, junto con las opciones, requiere que el nombre del archivo fuente principal sea idéntico al nombre del formato.

## Componer un archivo TeX en su formato personalizado

Ahora que hemos creado nuestro propio formato TeX, podemos proceder a componer un archivo TeX escrito en este formato. Aquí está el código:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

Para especificar el formato, necesitamos crear una instancia de la clase [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/). En el constructor de opciones, usamos la configuración [TeXConfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider), que requiere nuestro proveedor de formato como argumento y carga el formato encima del estado "virgen" del motor.

El código restante debería resultarle familiar, ya que utiliza las funciones que se analizaron anteriormente en esta [guía](/tex/{{lang.url-fragment}}net/conversion/).

## Composición tipográfica de un archivo TeX en formato Plain TeX

Si eliminamos el proveedor de formato del código mostrado arriba, el motor cargará el formato predeterminado, que es [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) en su cuarto sentido. Por lo tanto, si tiene un archivo TeX escrito en formato Plain TeX, puede convertirlo a cualquier formato de destino compatible utilizando este enfoque.