---
translation: true
template: /templates/_template-python-net.md
linktitle: Licencias
title: Licencias - Aspose.TeX para Python
weight: 70
url: /python-net/licensing/
description: Si está utilizando la versión con licencia de la solución API Aspose.TeX para Python, puede aprender aquí cómo aplicar la licencia.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Evaluar Aspose.TeX

Para evaluar Aspose.TeX para Python, puede descargar fácilmente el producto desde la [página de descarga de Aspose.TeX para Python](https://pypi.org/project/aspose-tex-net/). La versión de evaluación es la misma que la versión comprada. Al agregar algunas líneas de código para aplicar la licencia, la versión de evaluación adquiere la licencia. Consulte la página de descarga para obtener la última versión.

### Limitaciones de la versión de evaluación

La versión de evaluación de Aspose.TeX proporciona la funcionalidad completa del producto, con la excepción de que solo se pueden obtener las primeras cuatro páginas en el documento de salida. Además, estas páginas estarán estampadas con una marca de agua en modo de evaluación.

Si desea probar Aspose.TeX sin estas limitaciones de evaluación, puede [solicitar una licencia temporal de 30 días](https://purchase.aspose.com/temporary-license/) que le permitirá probar todos los aspectos de un producto antes de comprarlo.

## Aplicar una licencia

Una vez que haya completado su evaluación de Aspose.TeX para Python y esté satisfecho con su rendimiento, puede comprar una licencia a través del sitio web de Aspose en el [Portal de compras](https://purchase.aspose.com/pricing?). Se recomienda familiarizarse con los diferentes tipos de licencia disponibles antes de realizar una compra. Si tiene alguna pregunta o necesita ayuda, no dude en [contactar al equipo de ventas de Aspose](https://consulting.aspose.com/), ya que estarán encantados de ayudarle.

Cada licencia de Aspose incluye una suscripción de un año que le da derecho a actualizaciones gratuitas de cualquier nueva versión o corrección publicada durante ese período. También ofrecemos soporte técnico gratuito e ilimitado a usuarios con licencia y de evaluación.

La licencia de Aspose es un archivo XML de texto sin formato que incluye información como el nombre del producto, la cantidad de desarrolladores con licencia y la fecha de vencimiento de la suscripción. Es importante no modificar el archivo ya que está firmado digitalmente, e incluso agregar un salto de línea adicional lo invalidará.

### Cuándo solicitar una licencia

Siga estas pautas:

- La licencia solo debe configurarse una vez por dominio de aplicación.
- Configure la licencia antes de usar cualquier otra clase de Aspose.TeX.
- Llamar a `set_license` varias veces no es perjudicial pero desperdicia tiempo del procesador.

#### Cargando una licencia desde un archivo

Aplique la licencia antes de utilizar otras clases de Aspose.TeX. Establezca `ASPOSE_TEX_PYTHON_NET_LICENSE_PATH` con la ruta de la licencia o coloque `Aspose.TeX.Python-net.lic` en el directorio de trabajo.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### Cargando una licencia desde un objeto Stream

El siguiente ejemplo abre el archivo de licencia como un flujo binario y lo cierra después de aplicar la licencia. Utiliza la misma configuración de ruta que el ejemplo de archivo.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### Licencia medida

Aspose.TeX ofrece un mecanismo de licencia alternativo llamado *Licencia medida*, que permite facturar a los clientes en función del uso de las funciones API. Aplicar una *Licencia medida* es tan sencillo como aplicar un par de claves criptográficas. Para obtener más información, consulte la [sección de preguntas frecuentes sobre licencias medidas](https://purchase.aspose.com/faqs/licensing/metered/).

Para configurar las claves públicas y privadas de una licencia medida, puede utilizar una instancia de la clase [*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/), como se muestra en el siguiente ejemplo: Proporcione sus claves mediante `ASPOSE_TEX_METERED_PUBLIC_KEY` y `ASPOSE_TEX_METERED_PRIVATE_KEY`.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}