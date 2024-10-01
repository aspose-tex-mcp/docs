---
translation: true
template: /templates/_template-java.md
linktitle: incluir gráficos
title: LaTeX incluye gráficos | Aspose.TeX para Java
weight: 10
url: /java/latex-includegraphics/
keywords: incluir gráficos de látex, incluir gráficos de látex, insertar imágenes de látex, gráficos de látex, insertar imagen de látex, paquete de látex incluir gráficos, dibujar io látex, ancho de incluir gráficos de látex, ancho de incluir gráficos, látex de escala de figura
description: Obtenga información sobre la macro de gráficos incluidos en LaTeX, junto con las transformaciones de imágenes, la ventana gráfica, el recorte y la diferencia entre gráficos y paquetes de gráficos.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Introducción

Mientras trabaja en sus documentos académicos y científicos, como trabajos de investigación, actas de congresos y presentaciones académicas, es posible que en ocasiones desee incluir figuras gráficas.

Por un lado, pueden ser dibujos, diagramas, histogramas o algo más, lo que generalmente se denomina gráficos vectoriales. Los sistemas LaTeX modernos (como `pdfTeX`) proporcionan muchas herramientas para crear dichos gráficos en un documento. Por ejemplo, los paquetes `pict2e`, `PGF(TikZ)` y `PGFplots`. En la mayoría de los casos, las figuras mismas son generadas por un motor TeX y se incluyen en el archivo de salida como secuencias de instrucciones de gráficos vectoriales apropiadas para un formato de salida específico.

Por otro lado, es posible que tengas imágenes rasterizadas que también quieras incluir en tu publicación. Actualmente, los sistemas LaTeX también son capaces de hacer esto, pero debe especificar la ruta a su archivo de imagen en su archivo LaTeX como parámetro para alguna macro de LaTeX.

Este artículo cubre la inclusión de imágenes rasterizadas en archivos LaTeX usando la macro `\includegraphics` del paquete `graphics` (y el paquete `graphicx` que lo acompaña).

## ¿Qué paquete elegir, `graphics` o `graphicx`?

Ambos paquetes, `graphics` y `graphicx`, son muy similares. La principal diferencia está en la sintaxis. Mientras que el paquete `graphics` usa un conjunto de macros separadas para aplicar transformaciones a una imagen, el paquete `graphicx` usa la notación `key=value` para los parámetros de la macro `\includegraphics` para especificar estas transformaciones. Daremos ejemplos de cada caso de uso para ambos paquetes a la vez para que la diferencia sea más clara.

## Incluyendo el paquete elegido

Esto se hace con el comando `\usepackage` de la misma manera que con cualquier otro paquete LaTeX:

```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Especificación de un controlador

Si su sistema de composición tipográfica no está configurado para usar, digamos, `pdfTeX` de forma predeterminada, debe especificar la opción adecuada que obligará al paquete a usar el `controlador` requerido:

```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

Un "controlador" es parte de un paquete que implementa la interfaz entre los comandos del paquete y las primitivas de extensión TeX de bajo nivel que dependen del formato. **La compatibilidad con gráficos LaTeX de Aspose.TeX** está configurada para usar su propio controlador, por lo que no es necesario especificar la opción del controlador.

## Macro de LaTeX `\ includegraphics`

Ahora procedamos con el ejemplo más simple. Por supuesto, se trata de incluir una imagen sin ninguna transformación. Como era de esperar, el código LaTeX que utiliza ambos paquetes es el mismo:

```tex
\includegraphics{sample-image.png}
```

Este ejemplo supone que su archivo de imagen está ubicado en el mismo directorio que el archivo LaTeX. Pero hay varias formas de especificar una ubicación diferente. El código LaTeX volverá a ser el mismo para ambos paquetes:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Otra forma de especificar la(s) ubicación(es) de los archivos de gráficos es definir una lista de rutas alternativas usando el comando `\graphicspath` antes de llamar a `\includegraphics`:

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Transformaciones de gráficos LaTeX

Los paquetes LaTeX `graphics` y `graphicx` proporcionan varias formas de manipular el contenido.

### Figura a escala LaTeX

Así que puedes escalar los gráficos incluidos (de hecho, cualquier cosa descrita por el código TeX/LaTeX) de la siguiente manera:

```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Cambiar el tamaño de la figura LaTeX

Es similar al escalado, pero usted especifica el tamaño requerido en lugar de un factor de escala:

```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Girar figura LaTeX

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Configurar una ventana gráfica y recortar

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

En cuanto al paquete `graphicx`, las transformaciones se pueden combinar, pero el orden es importante.

Para obtener más información sobre las características del paquete `graphics`, consulte la [página del paquete en CTAN](https://ctan.org/pkg/graphics) y
la [documentación del paquete](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### Aplicación web gratuita LaTeX Incluir gráficos

Si no desea trabajar con el paquete latex includegraphics mediante programación, también puede consultar la aplicación web gratuita [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics/) creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/). 

La aplicación te permite seleccionar varias imágenes y ajustar visualmente las transformaciones para ellas. También genera código fuente LaTeX usando el paquete `graphicx` y lo muestra mostrando el resultado en la página.

### Función de representación de figuras LaTeX en la biblioteca Aspose.TeX

La biblioteca **Aspose.TeX** proporciona una manera de crear figuras rasterizadas y SVG que puedes usar en tus publicaciones fuera del contexto TeX/LaTeX. Por ejemplo, en una página web. Esto se llama **Representación de figuras LaTeX**. Brevemente, esta parte de la API le permite representar un fragmento de código fuente de LaTeX independientemente del diseño de la página. Para obtener más detalles, consulte este [artículo](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

El artículo sobre [incluidos paquetes externos de LaTeX](/tex/{{lang.url-fragment}}java/external-latex-packages/) también puede darle una pista sobre cómo crear figuras a partir de gráficos de LaTeX.