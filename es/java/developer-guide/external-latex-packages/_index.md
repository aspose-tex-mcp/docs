---
translation: true
template: /templates/_template-java.md
title: Paquetes LaTeX externos | Java
linktitle: Paquetes externos de LaTeX
weight: 30
url: /java/external-latex-packages/
description: Aspose.TeX para Java permite el uso de paquetes externos, es decir, aquellos que no están incluidos en la propia biblioteca, como los paquetes fancybox.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Paquetes externos de LaTeX

Hay varios [paquetes comunes de LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/) incluidos en la biblioteca **Aspose.TeX** para Java. Por lo tanto, no tiene que preocuparse por cómo proporcionar estos paquetes al motor TeX de la biblioteca. Pero a veces (tal vez a menudo) su archivo LaTeX puede requerir un paquete más allá del "paquete" de paquetes admitido "de forma nativa". En este caso, puede intentar proporcionar la entrada requerida, es decir, los archivos fuente del paquete requerido, utilizando el método [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) de la instancia de clase [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Veremos cómo funciona esto con dos ejemplos.

### Entrada requerida desempaquetada (paquete `fancybox`)

Digamos que tenemos el siguiente archivo LaTeX simple, que es `required-input-fs.tex` de nuestra [solución de ejemplo](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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

En la tercera línea, vemos que el archivo requiere el paquete `fancybox`, que no es compatible "de forma nativa". También asumimos que tenemos el archivo fuente del paquete `fancybox`. Es un paquete simple, por lo que en realidad consta de un solo archivo. Podemos colocar este archivo en cualquier lugar de nuestro sistema de archivos y especificar la ruta del directorio de la siguiente manera:

```Java
options.setRequiredInputDirectory(new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located"));
```

Después de ejecutar un trabajo TeX con esta opción (no olvide ajustar las otras opciones según sea necesario), obtenemos el documento de salida (es decir, una imagen PNG).

![Documento de salida](/tex/images/java/Conversion-RequiredInputFs.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.java" >}}

### Entrada requerida archivada (paquete `pgfplots`)

Supongamos ahora que tenemos el siguiente archivo LaTeX también bastante simple, que es `required-input-zip.tex` de nuestra solución de ejemplo:

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

En la tercera línea, vemos que el archivo requiere el paquete `pgfplots`, que tampoco es compatible de forma "nativa". Nuevamente, asumimos que tenemos los archivos fuente del paquete `pgfplots`. Es un conjunto bastante grande de archivos que se dividen en dos ubicaciones si los encuentra en el directorio de instalación de cualquier aplicación de composición tipográfica LaTeX. Puede encontrar la carpeta `pgfplots` en las carpetas `\tex\generic` y `\tex\latex`. Y el contenido de ambas carpetas debe proporcionarse como entrada requerida para la biblioteca Aspose.TeX. Queremos que estos archivos fuente estén empaquetados en un archivo ZIP, así que aquí está el diseño del archivo:

![diseño del archivo](/tex/images/java/pgfplots-zip-layout.png)

Y así es como especificamos el acceso a estos archivos fuente:

```Java
final Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
try {
    ...
    options.setRequiredInputDirectory(new InputZipDirectory(zipStream));
    ...
} finally {
    if (zipStream != null)
        zipStream.close();
}
```

Después de ejecutar un trabajo TeX con esta opción, obtenemos el documento de salida:

![Documento de salida](/tex/images/java/Conversion-RequiredInputZip.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.java" >}}

> **_NOTA:_** El resultado se verificó utilizando la versión 1.18.1 del paquete `pgfplots`. Mientras que la versión del paquete `pfg` incluida en la biblioteca **Aspose.TeX** es la 3.1.9a.

### Usar paquetes de fuentes externos

Normalmente, las distribuciones de LaTeX vienen con una selección de fuentes predeterminadas que se pueden utilizar para la composición tipográfica. Además de estas fuentes, **Aspose.TeX** ofrece varios paquetes de fuentes no estándar, como `amsfonts`, `eurosym` y `wasysym`. Como se mencionó anteriormente, **Aspose.TeX** también admite el uso de paquetes externos, aunque nos hemos centrado principalmente en paquetes que no incluyen fuentes.
La extensión del motor *Object TeX* en **Aspose.TeX** requiere mapas de fuentes, que son archivos de texto con la extensión `.map` que especifican las fuentes físicas correspondientes al nombre de fuente interna de cada TeX. Estos mapas de fuentes deben cargarse en la memoria de TeX durante la fase de inicialización y deben incluirse en los archivos del paquete. Dado que el motor no conoce los nombres de todos los mapas de fuentes, busca cualquier archivo con la extensión `.map`. Por lo tanto, la implementación de la interfaz [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) utilizada como valor de la opción [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) debe proporcionar una forma de acceder a colecciones de nombres de archivos según su extensión. Específicamente, esta implementación también debe implementar la interfaz [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Las implementaciones estándar, [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), ya cumplen este requisito.

A continuación, presentamos un ejemplo de un directorio de entrada requerido personalizado que también implementa la interfaz [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Nuestro énfasis principal está en recopilar nombres de archivos según su extensión, y omitimos intencionalmente los detalles del almacenamiento y recuperación de archivos.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInputDirectory.java" >}}

### Restricciones

Un paquete requerido por su archivo LaTeX puede desarrollarse bajo el kernel *LaTeX3e*. Lo más probable es que un paquete de este tipo no funcione con la biblioteca **Aspose.TeX** ya que esta última se basa en el kernel *LaTeX2e*.

Además, un paquete requerido por su archivo LaTeX puede llamar directamente a comandos primitivos dependientes del dispositivo que no son compatibles con el motor *Object TeX* de la biblioteca **Aspose.TeX**. Desafortunadamente, un paquete así no funcionará con seguridad.