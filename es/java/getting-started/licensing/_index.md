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

Utilice el método [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-) para aplicar la licencia al componente. En los ejemplos siguientes, establezca `licenseFilePath` en la ruta completa del archivo de licencia. El método que realiza la llamada debe capturar o declarar `Exception`.

#### Cargando una licencia desde un archivo

Este fragmento de código aplica una licencia almacenada en un archivo.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromFile.java" >}}

#### Cargando una licencia desde un objeto Stream

Estos fragmentos de código inicializan la licencia de la transmisión.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromStream.java" >}}

### Licencia medida

Aspose.TeX tiene un mecanismo de licencia alternativo llamado *Licencia medida*. Si un cliente desea que se le facture en función del uso de las funciones API, puede aplicar una *licencia medida*, que en realidad es tan simple como aplicar un par de claves criptográficas. Para obtener más detalles, consulte la [sección de preguntas frecuentes sobre licencias medidas](https://purchase.aspose.com/faqs/licensing/metered/).

Las claves públicas y privadas de una licencia medida se pueden configurar usando una instancia de la clase [*Metered*](https://reference.aspose.com/tex/java/com.aspose.tex/metered/), como se muestra a continuación:

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetMeteredLicense.java" >}}