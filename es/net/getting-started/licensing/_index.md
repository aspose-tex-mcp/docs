---
translation: true
template: /templates/_template-net.md
linktitle: Licencias
title: Licencias | Aspose.TeX para .NET
weight: 70
url: /net/licensing/
description: Cuando se detuvo en la versión con licencia de la solución API Aspose.TeX para .NET, aquí descubrirá cómo aplicar la licencia.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Evaluar Aspose.TeX

Puede descargar fácilmente el producto Aspose.TeX para .NET con fines de evaluación. Consulte la [página de descarga de Aspose.TeX para .NET](https://www.nuget.org/packages/Aspose.TeX/) para conocer la última versión. La descarga de evaluación es la misma que la descarga comprada. La versión de evaluación simplemente adquiere la licencia cuando agrega unas pocas líneas de código para aplicar la licencia.

### Limitaciones de la versión de evaluación

La versión de evaluación de Aspose.TeX (sin una licencia especificada) proporciona la funcionalidad completa del producto, excepto que solo se pueden obtener hasta cuatro primeras páginas en el documento de salida. Además, esas páginas estarán estampadas con una marca de agua en modo de evaluación.

Si desea probar Aspose.TeX sin limitaciones de evaluación, solicite una licencia temporal de 30 días. Consulte [¿Cómo obtener una licencia temporal?](https://purchase.aspose.com/temporary-license/) para obtener más información.

## Aplicar una licencia

Una vez que esté satisfecho con su evaluación de Aspose.TeX para .NET, compre una licencia en el sitio web de Aspose: [Portal de compras](http://www.aspose.com/purchase/default.aspx). Familiarícese con los diferentes tipos de licencia disponibles. Si tiene alguna pregunta, [comuníquese con el equipo de ventas de Aspose](http://www.aspose.com/corporate/contact/default.aspx) y estarán encantados de ayudarle.

Cada licencia de Aspose incluye una suscripción de un año para actualizaciones gratuitas de cualquier nueva versión o corrección que surja durante este tiempo. Brindamos soporte técnico gratuito e ilimitado a usuarios con licencia y de evaluación.

La licencia es un archivo XML de texto sin formato que contiene detalles como el nombre del producto, la cantidad de desarrolladores con licencia, la fecha de vencimiento de la suscripción, etc. El archivo está firmado digitalmente, así que no lo modifique: incluso agregar un salto de línea adicional al archivo lo invalida.

### Cuándo solicitar una licencia

Siga estas sencillas reglas:

- La licencia solo debe configurarse una vez por dominio de aplicación.
- Debe configurar la licencia antes de utilizar cualquier otra clase de Aspose.TeX.
- Llamar a SetLicense varias veces no es perjudicial, pero desperdicia tiempo del procesador.
- Si está desarrollando una aplicación de consola o Windows Forms, llame a SetLicense en el código de inicio, antes de usar las clases Aspose.TeX.
- Al desarrollar una aplicación ASP.NET, llame a SetLicense desde el archivo Global.asax.cs, en el método protegido Aplication_Start. Se llama una vez cuando se inicia la aplicación.
- No llame a SetLicense desde los métodos Page_Load ya que significa que la licencia se cargará cada vez que se cargue una página web.
- Si estás desarrollando una biblioteca de clases, puedes llamar a SetLicense desde un constructor estático de la clase que usa Aspose.TeX. El constructor estático se ejecuta antes de que se cree una instancia de su clase, asegurándose de que la licencia Aspose.TeX esté configurada correctamente.

### Aplicar la licencia utilizando un archivo o un objeto de secuencia

Utilice el método [License.SetLicense](https://reference.aspose.com/tex/net/aspose.tex/license/) para obtener la licencia del componente. La forma más sencilla de configurar una licencia es colocar el archivo de licencia en la misma carpeta que *Aspose.TeX.dll* y especificar el nombre del archivo, sin una ruta, como se muestra a continuación.

#### Cargando una licencia desde un archivo

Este fragmento de código inicializa una licencia almacenada en un archivo o en un recurso integrado.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromFile.cs" >}}

#### Cargando una licencia desde un objeto Stream

Estos fragmentos de código inicializan la licencia de la transmisión.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromStream.cs" >}}

### Licencia medida

Aspose.TeX tiene un mecanismo de licencia alternativo. Aquellos clientes que deseen que se les facture según el uso de las funciones API pueden utilizar *Licencias medidas*. Aplicar una *Licencia medida* es en realidad tan simple como aplicar un par de claves criptográficas. Para obtener más detalles, consulte la [sección de preguntas frecuentes sobre licencias medidas](https://purchase.aspose.com/faqs/licensing/metered/).

Las claves públicas y privadas de una licencia medida se configuran utilizando una instancia de la clase [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/), como se muestra en el siguiente ejemplo: 

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetMeteredLicense.cs" >}}
