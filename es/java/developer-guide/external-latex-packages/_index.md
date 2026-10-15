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

Establezca `inputFile` en la ruta completa del documento LaTeX correspondiente y `outputDirectory` en una carpeta de salida existente. Ambos ejemplos de conversión generan PNG a 150 DPI. Importe las clases Aspose.TeX usadas en el ejemplo seleccionado, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions` y, para entrada ZIP, `java.io.InputStream` y `java.nio.file.Files`. Gestione o declare las excepciones en el método que llama al ejemplo. Aplique una licencia según la [guía de licencias](/tex/{{lang.url-fragment}}java/licensing/).

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

La tercera línea requiere el paquete externo `fancybox`. Establezca `packagesDirectory` en una carpeta local con `fancybox.sty` y sus dependencias. El ejemplo completo siguiente asigna esta carpeta a `RequiredInputDirectory` y genera una imagen PNG. El dispositivo y los directorios de trabajo permanecen abiertos hasta que termina el trabajo y después se liberan o cierran.

![Documento de salida](/tex/images/java/Conversion-RequiredInputFs.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-FileSystem.java" >}}

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

Establezca `packagesZip` en un `java.nio.file.Path` al archivo que contiene las fuentes genéricas y LaTeX del paquete. El ejemplo Java completo siguiente lo abre con `Files.newInputStream(...)` y asigna un `InputZipDirectory` a `RequiredInputDirectory`. El argumento de ruta base vacío selecciona todo el archivo. Mantenga abiertos el flujo ZIP y el directorio hasta que termine el trabajo TeX y después ciérrelos. El resultado es una imagen PNG con las dos gráficas.

![Documento de salida](/tex/images/java/Conversion-RequiredInputZip.png)

Aquí está el código fuente completo del ejemplo:

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInput-Zip.java" >}}

> **_NOTA:_** El resultado se verificó utilizando la versión 1.18.1 del paquete `pgfplots`. Mientras que la versión del paquete `pfg` incluida en la biblioteca **Aspose.TeX** es la 3.1.9a.

### Usar paquetes de fuentes externos

Normalmente, las distribuciones de LaTeX vienen con una selección de fuentes predeterminadas que se pueden utilizar para la composición tipográfica. Además de estas fuentes, **Aspose.TeX** ofrece varios paquetes de fuentes no estándar, como `amsfonts`, `eurosym` y `wasysym`. Como se mencionó anteriormente, **Aspose.TeX** también admite el uso de paquetes externos, aunque nos hemos centrado principalmente en paquetes que no incluyen fuentes.
La extensión del motor *Object TeX* en **Aspose.TeX** requiere mapas de fuentes, que son archivos de texto con la extensión `.map` que especifican las fuentes físicas correspondientes al nombre de fuente interna de cada TeX. Estos mapas de fuentes deben cargarse en la memoria de TeX durante la fase de inicialización y deben incluirse en los archivos del paquete. Dado que el motor no conoce los nombres de todos los mapas de fuentes, busca cualquier archivo con la extensión `.map`. Por lo tanto, la implementación de la interfaz [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) utilizada como valor de la opción [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) debe proporcionar una forma de acceder a colecciones de nombres de archivos según su extensión. Específicamente, esta implementación también debe implementar la interfaz [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Las implementaciones estándar, [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) e [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), ya cumplen este requisito.

El siguiente `RequiredInputDirectory` personalizado implementa ambas interfaces y lee archivos locales registrados explícitamente. Guárdelo como `RequiredInputDirectory.java` con sus importaciones incluidas. Registre cada archivo con `storeFileName(...)`, asigne la instancia con `options.setRequiredInputDirectory(...)` y ciérrela después del trabajo. Es un registro plano: los nombres de archivo deben ser únicos cuando se solicitan sin ruta completa. Las extensiones no distinguen mayúsculas de minúsculas; la ruta de recopilación opcional selecciona un directorio del sistema de archivos. Registre todos los archivos de paquete, mapas de fuentes, métricas y fuentes físicas necesarios. La recopilación permite encontrar los mapas, pero no proporciona datos de fuentes que falten.

{{< gist "aspose-com-gists" "be002eee5d3f1f880cf1b77424b754e1" "Example-RequiredInputDirectory.java" >}}

### Restricciones

Un paquete requerido por su archivo LaTeX puede desarrollarse bajo el kernel *LaTeX3e*. Lo más probable es que un paquete de este tipo no funcione con la biblioteca **Aspose.TeX** ya que esta última se basa en el kernel *LaTeX2e*.

Además, un paquete requerido por su archivo LaTeX puede llamar directamente a comandos primitivos dependientes del dispositivo que no son compatibles con el motor *Object TeX* de la biblioteca **Aspose.TeX**. Desafortunadamente, un paquete así no funcionará con seguridad.