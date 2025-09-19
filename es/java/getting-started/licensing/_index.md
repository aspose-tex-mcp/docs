---
translation: true
template: /templates/_template-java.md
linktitle: Licencias
title: Licencias | Aspose.TeX para Java
weight: 70
url: /java/licensing/
description: Cuando se detuvo en la versión con licencia de la solución API Aspose.TeX para Java, aquí descubrirá cómo aplicar la licencia.
lastmod: "2024-10-30"
---

{{<section overview>}}


### Limitaciones de la versión de evaluación

La versión de evaluación de Aspose.TeX (sin una licencia especificada) proporciona la funcionalidad completa del producto, excepto que solo se pueden obtener hasta cuatro primeras páginas en el documento de salida. Además, esas páginas estarán estampadas con una marca de agua en modo de evaluación.

Si desea probar Aspose.TeX sin limitaciones de evaluación, solicite una licencia temporal de 30 días. Consulte [¿Cómo obtener una licencia temporal?](https://purchase.aspose.com/temporary-license/) para obtener más información.

### Aplicar la licencia utilizando un archivo o un objeto de secuencia

Utilice el método [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/License#setLicense-java.lang.String-) para obtener la licencia del componente. La forma más sencilla de configurar una licencia es colocar el archivo de licencia en la misma carpeta que *aspose.tex.jar* y especificar el nombre del archivo, sin una ruta, como se muestra a continuación.

#### Cargando una licencia desde un archivo

Este fragmento de código inicializa una licencia almacenada en un archivo o en un recurso integrado.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### Cargando una licencia desde un objeto Stream

Estos fragmentos de código inicializan la licencia de la transmisión.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### Licencia medida

Aspose.TeX tiene un mecanismo de licencia alternativo llamado *Licencia medida*. Si un cliente desea que se le facture en función del uso de las funciones API, puede aplicar una *licencia medida*, que en realidad es tan simple como aplicar un par de claves criptográficas. Para obtener más detalles, consulte la [sección de preguntas frecuentes sobre licencias medidas](https://purchase.aspose.com/faqs/licensing/metered/).

Las claves públicas y privadas de una licencia medida se pueden configurar usando una instancia de la clase [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/), como se muestra a continuación: 

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-SetMeteredLicense.java" >}}