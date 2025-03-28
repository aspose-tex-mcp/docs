---
translation: true
template: /templates/_template-net.md
title: E/S de látex | Aspose.TeX para .NET
linktitle: Entrada/salida de látex
weight: 17
url: /net/latex-io/
description: Esta página describe las peculiaridades de trabajar con LaTeX como formato de entrada o salida y el archivo *.aux* como parte obligatoria de LaTeX.
keywords: látex io, látex i, látex o, archivo de entrada de látex, entrada en látex
lastmod: "2024-10-30"
---

{{<section overview>}}

## archivo látex

Si tenemos un [archivo TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) que tiene la siguiente estructura, entonces llamaremos a este archivo *archivo LaTeX*:

```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

donde `<una clase de documento>` es el nombre de una [clase de documento](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes) que es un archivo TeX de entrada que define la apariencia de las páginas y macros del documento de salida que son más adecuadas para un determinado tipo de documento.

Para ser honesto, puede insertar secuencias de control primitivas antes de `\documentclass{}`, como `\nonstopmode`, etc. Pero cada macro de LaTeX verifica si está ubicada en una parte adecuada de un archivo.

Hay algunas cosas que vale la pena destacar sobre TeX [entrada](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) y [salida](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) en el contexto de trabajar con archivos LaTeX.

## Archivo de salida LaTeX

Un trabajo típico de LaTeX crea un archivo de salida auxiliar con [nombre del trabajo](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) como nombre y extensión *.aux*. Este archivo generalmente contiene datos de referencia que el motor recopila a lo largo de la ejecución del trabajo, si, por ejemplo, establece etiquetas para fórmulas matemáticas (ecuaciones) y luego hace referencia a ellas en algún lugar del texto. En caso de que no utilice nada de este tipo, este archivo contiene sólo la secuencia de control `\relax` (que es una de las primitivas TeX). Así que no te sorprendas.

Aunque las primitivas `\openout`, `\write` y `\closeout` no están prohibidas, los paquetes son el lugar más adecuado para ellas. Por lo tanto, será mejor que los utilices en tus propios paquetes personalizados si los estás desarrollando.

Otras partes de la salida son arbitrarias, también siguen el concepto general de [salida TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) y dependen de qué se supone que debe hacer exactamente su archivo (programa) TeX, qué paquetes (ver más abajo) está utilizando, etc.

## Archivo de entrada de látex

El archivo *.aux* mencionado anteriormente es una parte obligatoria de la entrada en LaTeX al mismo tiempo. Algorítmicamente, LaTeX no puede realizar esas tareas relacionadas con las referencias en una sola ejecución, por lo que el mismo trabajo debe ejecutarse dos veces: la primera vez para recopilar datos y la segunda para utilizarlos. Muchos sistemas de software basados ​​en LaTeX ejecutan trabajos LaTeX dos veces automáticamente. Spoiler: Hay una [opción](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) en la API Aspose.TeX que nos permite controlar este comportamiento.

Otra parte obligatoria es una [clase de documento](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). El archivo de clase de documento, a su vez, puede depender implícitamente de otros archivos, que por tanto también se incluyen en la entrada de LaTeX.

Si desea utilizar funciones que van más allá del alcance de LaTeX básico y sus clases de documentos, pero que son compatibles con una determinada implementación del motor TeX, normalmente utiliza un paquete, sobre el cual debe notificar al motor en el preámbulo. Un *paquete LaTeX* es un archivo, o un grupo de archivos reunidos bajo un mismo nombre, que proporciona dichas características. Para notificar al motor, debe usar el comando `\usepackage` con el nombre del paquete y opciones omitibles, si el paquete define alguna.

Por ejemplo,

```tex
\usepackage[a6paper,landscape]{geometry}
```

Aunque las primitivas `\input`, `\openin`, `\read` y `\closein` no están prohibidas, los paquetes son el lugar más adecuado para ellas. Por lo tanto, será mejor que los utilices en tus propios paquetes personalizados si los estás desarrollando.

Otras partes de la entrada son arbitrarias, también siguen el concepto general de [entrada TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) y dependen de qué se supone que debe hacer exactamente su archivo (programa) TeX, qué paquetes está utilizando, etc.