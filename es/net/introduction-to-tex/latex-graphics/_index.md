---
translation: true
template: /templates/_template-net.md
title: Gráficos de LaTeX | comando \incluir gráficos
linktitle: Gráficos de LaTeX
weight: 18
url: /net/latex-graphics/
description: La inclusión de gráficos en TeX es un tema que vale la pena mencionar. Al hablar de ello, lo primero que hay que mencionar es el comando `\includegraphics`
lastmod: 2026-10-19
---

{{<section overview>}}

En realidad, hay dos aspectos de los gráficos LaTeX que vale la pena mencionar:

 * gráficos vectoriales descritos directamente mediante comandos LaTeX/TeX y,
 * inclusión de gráficos externos descritos mediante formatos externos, como EPS, PDF o PNG y PDF rasterizados.

El primero tiene soporte limitado en el LaTeX original y sus paquetes. Se implementa con la ayuda de reglas verticales y horizontales de TeX. Esto se debe a que el LaTeX original se basa en el motor TeX original, que produce la salida principal en formato *DVI*, que no es adecuado para describir líneas y curvas ni datos de imágenes rasterizadas binarias. Pero los motores que son capaces de generar formatos que admiten gráficos (como pdfTeX a PDF) también pueden procesar gráficos utilizando paquetes o funciones de paquete que dependen del formato. Estos últimos gráficos no son compatibles con LaTeX básico por la misma razón. Discutiremos las características de inclusión de gráficos a continuación.

## El paquete LaTeX `graphics` y el comando `\includegraphics`

Cuando se habla de inclusión de gráficos LaTeX, lo primero que me viene a la mente es el comando `\includegraphics`. Está definido en el paquete `graphics`, que debes mencionar en el preámbulo para habilitar sus funciones.

```tex
\usepackage{graphics}
```

Si su sistema de composición tipográfica no está configurado para usar, digamos, pdfTeX de forma predeterminada, debe especificar la opción apropiada que obligará al paquete a usar el archivo `controlador` requerido:

```tex
\usepackage[pdftex]{graphics}
```
Un archivo `driver` es parte de un paquete que implementa la interfaz entre los comandos del paquete y las primitivas de extensión TeX de bajo nivel que dependen del formato. La compatibilidad con gráficos LaTeX de Aspose.TeX está configurada para utilizar su propio controlador, por lo que no es necesario especificar la opción del controlador.

Ahora, la forma más sencilla de incluir, digamos, una imagen PNG es escribir:

```tex
\includegraphics{sample-image.png}
```

donde `sample-image.png` es el nombre del archivo que desea incluir. Incluso puedes omitir la extensión. El paquete `graphics` contiene la lista de definiciones de formatos admitidos. Cuando busca un archivo, recorre esa lista e incluye el primer archivo coincidente encontrado.

También puede especificar el nombre completo del archivo utilizando una ruta absoluta o relativa:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Otra forma de especificar la(s) ubicación(es) de los archivos de gráficos es definir una lista de rutas alternativas usando el comando `\graphicspath` antes de llamar a `\includegraphics`:

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Escalar los gráficos

El paquete LaTeX `graphics` proporciona comandos para manipular el contenido. Así que puedes escalar los gráficos incluidos (de hecho, cualquier cosa descrita por el código TeX/LaTeX) de la siguiente manera:

```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Cambiar el tamaño de los gráficos

Es similar al escalado, pero usted especifica el tamaño requerido en lugar de un factor de escala:

```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proportions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Rotar los gráficos

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## El paquete LaTeX `graphicx`

El paquete LaTeX `graphicx` proporciona la interfaz `key=value` para transformaciones de contenido. Para habilitar sus funciones, debes mencionarlo en el preámbulo:

```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Puedes combinar cualquiera de las siguientes opciones, pero ten en cuenta que el orden es importante.

### Ventana gráfica

```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coincides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Escalar gráficos

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Cambiar el tamaño de los gráficos

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proportions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Gráficos giratorios

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Para obtener más información sobre las características del paquete `graphics`, consulte la documentación [aquí](https://ctan.org/pkg/graphics) y
[aquí](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex/) de conversión gratuita creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**

## Sintaxis tradicional (`graphics`) frente a la moderna (`graphicx`)

Aunque ambos paquetes comparten los mismos mecanismos subyacentes, representan paradigmas fundamentalmente distintos para el manejo de contenido en LaTeX.

- El paquete `graphics` se basa en envoltorios de comandos anidados y argumentos posicionales. Esto obliga a incluir las macros de inserción dentro de funciones de transformación independientes (por ejemplo, anidando `\includegraphics` dentro de `\scalebox`).

- El paquete `graphicx` introduce una interfaz de «clave-valor» (key-value) clara y extensible, integrada directamente en los argumentos opcionales de `\includegraphics`. Esto permite definir múltiples transformaciones en un único bloque legible.

| **Operación** | **Paquete tradicional `graphics`** | **Paquete moderno `graphicx`** |
| :- | :- | :- |
| Inserción básica de imagen | `\includegraphics{sample-image.png}` | `\includegraphics{sample-image.png}` |
| Escalado uniforme | `\scalebox{0.5}{\includegraphics{sample-image.png}}` | `\includegraphics[scale=0.5]{sample-image.png}` |
| Escalado no uniforme (X/Y independientes) | `\scalebox{0.5}[1.5]{\includegraphics{sample-image.png}}` | (Requiere anidamiento o paquetes adicionales) |
| Cambio de tamaño por dimensión | `\resizebox{10mm}{!}{\includegraphics{sample-image.png}}` | `\includegraphics[width=10mm]{sample-image.png}` |
| Cambio de tamaño de ambas dimensiones de forma independiente | `\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}}` | `\includegraphics[width=25mm, height=15mm]{sample-image.png}` |
| Rotación | `\rotatebox{25}{\includegraphics{sample-image.png}}` | `\includegraphics[angle=25]{sample-image.png}` |
| Recorte (viewport clipping) | Requiere la anulación de la caja delimitadora (*bounding box*) a un nivel inferior |`\includegraphics[viewport=10 10 280 220, clip]{sample-image.png}`|


### Ventajas del enfoque de «clave-valor» de `graphicx`

1. Combina múltiples transformaciones de forma nativa:
Con `graphicx`, es posible aplicar escalado, rotación y recorte de manera simultánea mediante un único comando, sin necesidad de anidar macros.

2. Preserva las proporciones de forma clara:
Al utilizar el parámetro `keepaspectratio=true` junto con restricciones explícitas de anchura o altura, se evita la distorsión de la imagen sin necesidad de calcular manualmente los factores de escala.

3. Mayor facilidad de mantenimiento en la generación automatizada:
Al desarrollar programas o scripts (como los basados ​​en Aspose.TeX para .NET) que generan o analizan dinámicamente archivos fuente de LaTeX, la construcción de cadenas de propiedades estructuradas mediante pares «clave-valor» resulta mucho menos propensa a errores que el análisis e inserción de macros anidadas.