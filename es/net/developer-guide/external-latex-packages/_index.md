---
translation: true
template: /templates/_template-net.md
title: Paquetes LaTeX externos | Aspose.TeX para .NET
linktitle: Paquetes externos de LaTeX
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX para .NET permite utilizar paquetes externos, es decir, los que no están incluidos en la propia biblioteca, como los paquetes pgfplots.
keywords: paquetes externos de LaTeX, Aspose TeX, .NET TeX, paquetes de LaTeX, FancyBox, pgfplots, directorio de entrada requerido, archivo zip de entrada, directorio de entrada personalizado, conversión de TeX
lastmod: "2026-11-04"
---

{{<section overview>}}

## Paquetes externos de LaTeX

La biblioteca **Aspose.TeX** incluye varios [paquetes comunes de LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Por lo tanto, no tiene que preocuparse por cómo proporcionar estos paquetes al motor TeX de la biblioteca. Pero a veces (o con bastante frecuencia) su archivo LaTeX puede requerir un paquete más allá del "paquete" de paquetes admitido "de forma nativa". Si este es el caso, puede intentar proporcionar la entrada requerida, es decir, los archivos fuente del paquete requerido, a través de la opción [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) de la instancia de clase [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Veremos cómo funciona esto con dos ejemplos.

### Entrada requerida desempaquetada (paquete `fancybox`)

Digamos que tenemos el siguiente archivo LaTeX simple, que es `required-input-fs.tex` de nuestra [solución de ejemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):

```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

En la tercera línea, podemos ver que el archivo requiere el paquete `fancybox`, que no es compatible "de forma nativa". Supongamos también que tenemos el archivo fuente del paquete `fancybox`. Es un paquete simple, por lo que realmente consta de un único archivo. Podemos colocar este archivo en cualquier lugar de nuestro sistema de archivos y especificar la ruta del directorio de la manera más simple que se muestra a continuación:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Después de ejecutar un trabajo TeX con esta opción (no olvide ajustar las otras opciones según sea necesario), obtenemos el documento de salida (es decir, una imagen PNG).

![Documento de salida](/tex/images/net/Conversion-RequiredInputFs.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Entrada requerida archivada (paquete `pgfplots`)

Digamos ahora que tenemos el siguiente archivo LaTeX también bastante simple, que es `required-input-zip.tex` de nuestra solución de ejemplo:

```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

En la tercera línea, podemos ver que el archivo requiere el paquete `pgfplots`, que tampoco es compatible de forma "nativa". Nuevamente, asumimos que tenemos los archivos fuente del paquete `pgfplots`. Es una cantidad bastante grande de archivos que se dividen en dos ubicaciones si los encuentra en el directorio de instalación de cualquier aplicación de composición tipográfica LaTeX. Puede encontrar la carpeta `pgfplots` en las carpetas `\tex\generic` y `\tex\latex`. Y el contenido de ambas carpetas debe proporcionarse como entrada requerida para la biblioteca Aspose.TeX. Queremos que estos archivos fuente estén empaquetados en un archivo ZIP, así que aquí está el diseño del archivo:

![Diseño del archivo](/tex/images/net/pgfplots-zip-layout.png)

Y así es como especificamos el acceso a estos archivos fuente:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Después de ejecutar un trabajo TeX con esta opción, obtenemos el documento de salida:

![Documento de salida](/tex/images/net/Conversion-RequiredInputZip.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_NOTA:_** El resultado se verificó utilizando la versión 1.18.1 del paquete `pgfplots`. Mientras que la versión del paquete `pfg` incluida en la biblioteca **Aspose.TeX** es la 3.1.9a.

### Emplear paquetes de fuentes externos

Como regla general, las distribuciones de LaTeX proporcionan un conjunto de fuentes predeterminadas disponibles para la composición tipográfica. Excepto estas fuentes, **Aspose.TeX** incluye varios paquetes de fuentes no estándar. Por ejemplo, "amsfonts", "eurosym" y "wasysym". Como vimos anteriormente, Aspose.TeX también permite emplear paquetes externos. Pero sobre todo estábamos hablando de paquetes que no contienen fuentes.
La extensión del motor *Object TeX* de **Aspose.TeX** necesita mapas de fuentes (que son archivos de texto en un formato determinado con la extensión `.map` por convención) para determinar qué fuentes físicas corresponden al nombre de fuente interno de cada TeX. . Estos mapas de fuentes deben cargarse en la memoria de TeX durante la fase de inicialización. Y, por supuesto, deben estar presentes entre los archivos del paquete que está conectando. Como el motor no conoce los nombres de todos los mapas de fuentes, busca todos los archivos con la extensión `.map`. Por lo tanto, una implementación de la interfaz [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) que se utiliza como valor de la opción [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) debe proporcionar una forma de acceder a colecciones de nombres de archivos por extensión. Más específicamente, esta implementación también debe implementar la interfaz [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Las implementaciones estándar, [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) y [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/), ya lo hacen.

A continuación, proporcionamos un ejemplo ilustrativo de un directorio de entrada personalizado requerido que también implementa la interfaz [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Si bien nos centramos en recopilar nombres de archivos por extensión, omitimos intencionalmente los detalles del almacenamiento y recuperación de archivos.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}

### Restricciones

Puede suceder que un paquete requerido por su archivo LaTeX esté desarrollado bajo el kernel *LaTeX3e*. Lo más probable es que un paquete de este tipo no funcione con la biblioteca **Aspose.TeX** ya que esta última se basa en el kernel *LaTeX2e*.

También puede suceder que un paquete requerido por su archivo LaTeX llame directamente a comandos primitivos dependientes del dispositivo que no son compatibles con el motor *Object TeX* de la biblioteca **Aspose.TeX**. Desafortunadamente, un paquete así no funcionará con seguridad.

## Creación de un agente de IA para la optimización de paquetes integrados en LaTeX

Si necesita crear un agente de IA que optimice el contenido para el inventario de paquetes integrado sin realizar lentas búsquedas dinámicas en la red ni en el sistema de archivos durante la generación, puede utilizar el flujo de trabajo que se describe a continuación.

En lugar de obligar a un LLM a adivinar qué paquetes son seguros o rápidos de usar, el agente se centra en este inventario específico de paquetes precompilados para evitar errores por paquetes que faltan.

![Arquitectura de ensamblaje de documentos integrados del agente de IA](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png)

1. Extracción de la intención de diseño (capa de análisis del LLM)
El usuario proporciona datos no estructurados en varios formatos o directivas conversacionales. El LLM asigna las solicitudes directamente a la lista de paquetes integrados de Aspose (`colortbl` para el sombreado de filas, `geometry` para los márgenes y `multirow` para las celdas que ocupan varias filas).

2. Aislamiento del AST e inyección de preámbulo
En lugar de escribir importaciones de paquetes voluminosas, el agente verifica los requisitos del código con la lista de paquetes integrados.

Escribe en el preámbulo solo los comandos `\usepackage` necesarios.

3. Aislamiento y ejecución de flujos (Nodo del motor Aspose.TeX)
El código fuente de LaTeX se pasa a un `TeXJob` como un flujo, con `TeXOptions` creado para `TeXConfig.ObjectLaTeX`. `TeXJob.Run()` es síncrono, por lo que el agente lo ejecuta en un trabajo en segundo plano.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,multirow,colortbl}
```

4. Serialización de recursos (Capa de renderizado de salida)
El trabajo escribe el resultado con un dispositivo de salida, como `PdfDevice` o `SvgDevice`, y el agente lo devuelve al cliente.