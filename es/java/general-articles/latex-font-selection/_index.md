---
translation: true
template: /templates/_template-java.md
linktitle: Esquema de selección de fuentes
title: Esquema de selección de fuentes LaTeX
weight: 60
url: /java/latex-font-selection/
keywords: látex, fuentes de látex, selección de fuentes de látex, nfss
description: Este artículo describe el uso de fuentes LaTeX en el procesamiento de documentos y menciona las métricas de las fuentes TeX y las formas de los caracteres.
lastmod: "2024-10-30"
---

{{<section overview>}}


Mientras procesa el documento fuente, el sistema de composición tipográfica LaTeX no tiene mucho conocimiento sobre la fuente que está utilizando. Simplemente calcula las posiciones de los personajes, sin necesidad de conocer formas. La información más importante que requiere son los *cuadros negros* de los caracteres, que están definidos por su ancho, alto y profundidad. Estas dimensiones se almacenan en un archivo externo separado conocido como archivo de métrica de fuente TeX (`.tfm`) para cada fuente.

Los capítulos de los personajes entran en juego más tarde. Si un sistema LaTeX produce un archivo `.dvi`, un programa *controlador* combina datos de ubicación de caracteres del archivo `.dvi` con información sobre las formas de los caracteres del archivo `.pk` o de descripciones de esquema (como PostScript) para producir la imagen del personaje en el medio de salida. Sin embargo, otros sistemas LaTeX como **PDF TeX** o **VTEX** omiten la producción de un archivo `.dvi` y en su lugar generan directamente salidas **PDF** o **PostScript**. En ese caso, las formas de los caracteres se incrustan cuando el formateador correspondiente produce el resultado final.