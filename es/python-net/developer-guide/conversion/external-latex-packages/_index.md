---
translation: true
template: /templates/_template-python-net.md
title: Paquetes LaTeX externos | Python 
linktitle: Paquetes externos de LaTeX
weight: 19
url: /python-net/external-latex-packages/
description: La API Aspose.TeX para Python admite el uso de paquetes externos que no están incluidos en la propia biblioteca, como los paquetes fancybox y pgfplots.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Paquetes externos de LaTeX

La biblioteca **Aspose.TeX** viene con una variedad de [paquetes LaTeX comunes](/tex/{{lang.url-fragment}}net/embedded-packages/), por lo que no es necesario proporcionar manualmente estos paquetes al motor TeX. Sin embargo, puede haber situaciones en las que su archivo LaTeX requiera un paquete que no esté incluido en el "paquete" de paquetes de la biblioteca. En tales casos, puede intentar proporcionar la entrada necesaria, como los archivos fuente del paquete requerido, a través de la opción [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de la instancia de clase [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Exploraremos cómo funciona esto con dos ejemplos.

### Entrada requerida proporcionada en un formato descomprimido (el paquete `fancybox`).

Supongamos que tenemos el siguiente archivo LaTeX básico llamado `required-input-fs.tex`, que es parte de nuestra [solución de ejemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

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

La tercera línea del archivo indica que requiere el paquete `fancybox`, que no está incluido en el soporte "nativo". Supongamos que tenemos el archivo fuente del paquete `fancybox`. Dado que es un paquete simple que consta de un solo archivo, podemos colocar este archivo en cualquier lugar de nuestro sistema de archivos y especificar la ruta del directorio de la siguiente manera:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Una vez que ejecutemos un trabajo TeX con esta opción (recuerde ajustar las otras opciones según sea necesario), obtendremos el documento de salida, que en este caso es una imagen PNG.

![Documento de salida](/tex/images/python-net/Conversion-RequiredInputFs.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Proporcionar la entrada requerida en un formato archivado (el paquete `pgfplots`)

Ahora, supongamos que tenemos el siguiente archivo LaTeX llamado `required-input-zip.tex`, que también es un archivo simple de nuestra solución de ejemplo:

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

En la tercera línea, se puede observar que el archivo necesita el paquete `pgfplots`, que no es compatible "de forma nativa". Una vez más, suponiendo que poseemos los archivos fuente del paquete `pgfplots`, estos archivos son bastante numerosos y están ubicados en dos directorios diferentes dentro del directorio de instalación de cualquier aplicación de composición tipográfica LaTeX. La carpeta `pgfplots` se puede encontrar en los directorios `\tex\generic` y `\tex\latex`. Para que la biblioteca Aspose.TeX funcione correctamente, es necesario proporcionar el contenido de ambas carpetas como entrada. Para lograr esto, deseamos empaquetar estos archivos fuente en un archivo ZIP. A continuación se muestra el diseño deseado del archivo:

![Diseño del archivo](/tex/images/python-net/pgfplots-zip-layout.png)

Y aquí está el método mediante el cual definimos la accesibilidad a estos archivos fuente:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Después de ejecutar un trabajo TeX con esta opción, obtenemos el documento de salida:

![Documento de salida](/tex/images/python-net/Conversion-RequiredInputZip.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_NOTA:_** El resultado se verificó utilizando la versión 1.18.1 del paquete `pgfplots`. Mientras que la versión del paquete `pfg` incluida en la biblioteca **Aspose.TeX** es la 3.1.9a.

<!--
### Uso de paquetes de fuentes externos

Normalmente, las distribuciones LaTeX vienen con un conjunto predefinido de fuentes que se pueden usar para la composición tipográfica. Sin embargo, además de estas fuentes predeterminadas, **Aspose.TeX** también incluye varios paquetes de fuentes no estándar, como `amsfonts`, `eurosym` y `wasysym`. Como comentamos anteriormente, Aspose.TeX también admite el uso de paquetes externos, aunque la mayor parte de nuestra discusión anterior se centró en paquetes que no incluyen fuentes.

a extensión del motor *Object TeX* de **Aspose.TeX** requiere mapas de fuentes, que son archivos de texto en un formato específico con la extensión `.map`, para determinar las fuentes físicas correspondientes para cada nombre de fuente interno de TeX. Estos mapas de fuentes deben cargarse en la memoria de TeX durante la fase de inicialización y deben incluirse en el paquete que está utilizando. Como el motor no conoce los nombres de todos los mapas de fuentes, busca archivos con la extensión `.map`. Por lo tanto, al proporcionar un valor para la opción [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/), la implementación de la interfaz [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) debe permitir el acceso a colecciones de nombres de archivos por extensión. Además, esta implementación también debe implementar la interfaz [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Las implementaciones estándar, como [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), ya cumplen con estos requisitos.

A continuación, se muestra un ejemplo de un directorio de entrada obligatorio personalizado que demuestra cómo implementar la interfaz [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Este ejemplo se centra en la recopilación de nombres de archivos por extensión y omite intencionalmente los detalles de almacenamiento y recuperación de archivos.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.py" >}}
-->

### Restricciones

Si encuentra un paquete desarrollado bajo el kernel *LaTeX3e* y su archivo LaTeX lo requiere, es poco probable que funcione con la biblioteca **Aspose.TeX**. Esto se debe a que la biblioteca está basada en el kernel *LaTeX2e*.

Además, puede haber casos en los que un paquete requerido por su archivo LaTeX utilice directamente comandos primitivos dependientes del dispositivo que no son compatibles con el motor *Object TeX* de la biblioteca **Aspose.TeX**. En tales casos, el paquete no funcionará con la biblioteca.