---
translation: true
template: /templates/_template-java.md
linktitle: Clases de documentos LaTeX
title: Clases de documentos LaTeX | Aspose.TeX para Java
weight: 20
url: /java/latex-document-classes/
keywords: clase de artículo de látex, clase de documento de látex, plantilla de documento de látex, artículo de látex, libro de látex, diapositivas de látex, informe de látex, carta de látex, clase de documento en látex
description: Este artículo es un resumen conciso de las clases de documentos LaTeX y sus opciones. También proporciona algunos ejemplos.
lastmod: "2024-10-30"
---

{{<section overview>}}

## ¿Qué es una clase de documento en LaTeX?

LaTeX define algunas reglas que todo autor de documentos debe seguir. También define la estructura del archivo fuente, que es esencialmente un programa de composición tipográfica. Según esta estructura, el código fuente del documento debe contener una parte responsable del contenido del documento en sí - *cuerpo* - que está encerrado en un par de comandos: `\begin{document}` y `\end{document}`. LaTeX ignora todo lo que sigue al final del cuerpo. La parte del código fuente anterior a `\begin{document}` se llama *preámbulo*.

Normalmente, el primer comando en el preámbulo tiene que ser `\documentclass`, que toma un único argumento requerido que es el nombre de la **clase de documento**. La clase de documento en sí es un conjunto de parámetros de formato, métricas de diseño, macros, etc. que son adecuados y útiles para desarrollar documentos de un tipo determinado y recopilados bajo un nombre único. En este artículo, analizaremos las clases de documentos **predefinidas** de LaTeX que están integradas en LaTeX y mostraremos sus usos, diferencias y similitudes. También mencionaremos algunos argumentos opcionales que puede tomar el comando `\documentclass` y que personalizan la apariencia del documento.

## Clases de documentos LaTeX predefinidas

El LaTeX estándar contiene las siguientes clases de documentos:

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | La clase LaTeX article se utiliza para crear artículos para revistas científicas, informes breves, documentación de programas y, en general, cualquier documento breve que no necesite una división compleja en capítulos y partes. |
| **report** | La clase LaTeX report se utiliza para artículos largos que pueden contener varios capítulos (algo así como libros pequeños y tesis). |
| **book** | Se utiliza para componer libros reales. Incluye todo tipo de estándares de composición tipográfica adecuados para libros impresos: capítulos y partes, dos tipos de páginas, front matter, back matter, etc.|
| **slides** | Se puede utilizar para producir diapositivas, aunque existe el paquete externo [beamer](https://ctan.org/pkg/beamer) que es mucho más potente para este propósito. |
| **letter** | Esta clase de documento se utiliza para escribir cartas. |

Las dos primeras clases de documentos son básicas. Por lo tanto, comience con **artículo** siempre que no esté seguro de qué clase necesita.

La clase **informe** es muy similar. La principal diferencia con **artículo** es que puedes insertar capítulos con el comando `\chapter`, mientras que la clase de documento **artículo** no define dicha unidad de sección.

## La clase de **libro** de LaTeX

Los libros, en los estándares tipográficos, tienen la portada y la contraportada, que son la principal diferencia entre libros y, digamos, informes o artículos. La portada de un libro generalmente consta de media página de título, una página de título principal, una página de derechos de autor, un prefacio o prólogo y un índice de tabla. Partes menos obligatorias son los agradecimientos, una dedicatoria, una lista de figuras, una lista de tablas, una lista de otros libros de la misma serie y otro contenido editorial y promocional. El material posterior suele incluir un índice y puede contener un epílogo, así como agradecimientos, una bibliografía, un colofón, etc.

La clase de documento libro le ofrece comandos para producir las estructuras lógicas antes mencionadas, mientras que otras clases de documento no pueden proporcionarle dichas herramientas. Sin embargo, los diferentes editores suelen tener sus propios paquetes con comandos adicionales para diseñar estructuras según su propio estilo.

## Comandos de materia frontal, materia principal y materia posterior

La cuestión principal es lo que comprende el cuerpo del libro, comenzando por el primer capítulo o parte y terminando con los apéndices. Los asuntos frontal, principal y posterior comienzan con los comandos `\frontmatter`, `\mainmatter` y `\backmatter`, respectivamente.

> En la clase de libro estándar, las páginas de portada se numeran con números romanos, mientras que las páginas de portada y de contraportada se numeran con números arábigos.

> El comando `\chapter` no produce un número de capítulo en las páginas de portada y de contraportada, aunque sí crea una entrada en la tabla de contenidos. Esto se utiliza normalmente para crear un prefacio o una sección de agradecimientos. Dentro de dichos capítulos, solo se deben utilizar las versiones marcadas con asterisco de otros comandos de seccionamiento (como `\section*` y `\subsection`).

## Un ejemplo de uso de la clase de libro LaTeX

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

A continuación se muestra la estructura del documento generada por este código LaTeX:

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-document-classes-1.png) </a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-document-classes-2.png) </a>

Y aquí está el índice en detalle:

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Tabla de contenido](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **Páginas impares** y **pares** en libros
En los libros, las páginas ** impares ** y ** pares ** no tienen el mismo aspecto. Los márgenes, y normalmente los encabezados y pies de página, difieren para que el libro sea más legible cuando está encuadernado. La clase de documento LaTeX maneja esto y es posible que encuentres que:

- Las páginas **izquierdas (pares)** tienen un margen izquierdo más grande, el número de página está en la parte superior derecha de la página y el título del capítulo actual está a la derecha;
- Las páginas **derecha (impar)** tienen un margen derecho más grande y solo el número de página en la parte superior derecha de la página.

Tenga en cuenta que los nuevos capítulos siempre comienzan en la página derecha, donde el encabezado está vacío, dejando solo el número de página en el centro del pie.

## **Falta la sección Resumen**

Los trabajos académicos, como artículos o informes, suelen incluir una sección introductoria llamada **"Resumen"**. Su propósito es brindar una descripción general rápida del tema tratado en el documento. Es posible que lo encuentre impreso justo después del título y antes del índice, con el título "Resumen" en negrita. En LaTeX, dicha estructura se implementa como entorno "abstracto".

El entorno **abstracto** no lo proporciona la clase de documento de libro, y esta es otra diferencia con las clases de artículo e informe.

## Clase de **letra** de LaTeX

En la actualidad, la clase de documento de carta parece algo anticuada (en realidad, también lo es la clase de documento de diapositiva). Si necesitas hacer cartas tradicionales, ponerlas en sobres y enviarlas por correo, esta clase de documento probablemente te resulte útil. Aunque se trata de una forma de comunicación obsoleta, todavía hay casos en los que es posible que necesites preparar un documento similar a una carta. Por ejemplo, una carta de recomendación o una carta de presentación.

Entonces, aquí está una breve descripción general de la clase.

Puede generar cualquier cantidad de letras con un solo archivo de entrada. Su nombre y dirección, que suelen ser los mismos para todas las cartas, suelen especificarse en el preámbulo del documento. La dirección de retorno se declara mediante un comando `\address`, que acepta múltiples líneas separadas por `\\` (el comando de salto de línea de LaTeX) como argumento. De manera similar, el comando `\firma` acepta múltiples líneas, incluido su nombre, cargo, etc. Sin embargo, puede cambiar la dirección del remitente y la firma en cualquier momento.

Cada carta es generada por un entorno de "carta" separado que requiere el nombre y la dirección del destinatario como argumento. La carta comienza con una orden `\opening`, que produce el saludo, y termina con una orden `\closing`, que produce la frase de cierre y la firma. El cuerpo de la carta es entrada LaTeX normal.

Todos estos comandos son fáciles de usar y muy potentes ya que LaTeX se encarga automáticamente de formatear las letras. Así que no dejes que la cantidad de comandos te asuste o te confunda.

El siguiente ejemplo demuestra cómo funciona todo esto.

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![Un ejemplo de clase de documento de carta](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

Tenga en cuenta que la fecha actual también se produce automáticamente. Sin embargo, puedes redefinir el comando `\today` para cambiar la fecha en tus cartas. Así es como lo haces:

```tex
\renewcommand{\today}{01th of March of 2492}
```

Si inserta esta declaración en un determinado entorno de "carta", cambiará la fecha solo para esa carta. De lo contrario, si lo inserta en el preámbulo, estará vigente para todas las letras generadas por el archivo de entrada (a menos que se inserte en un determinado entorno de "letra").

## Opciones de clase de documento LaTeX

Ahora echemos un vistazo a las opciones del comando `\documentclass` mencionadas al principio del artículo.

### Tamaño de fuente

El tamaño de fuente se controla mediante tres opciones: 10pt, 11pt, 12pt. De forma predeterminada, está vigente 10 puntos. Estas opciones determinan el tamaño de fuente base utilizado en todo el documento, a menos que se haya cambiado en algún momento. También afectan los factores de escala para algunas dimensiones de formato.

```tex
\documentclass[12pt]{article}
```

> Estas opciones no son reconocibles por la clase `slides`.

### Tamaño del papel

"Tamaño de papel" aquí se refiere al tamaño de la hoja de papel en la que **planea** imprimir el documento. No afecta el tamaño de la representación de la página en la salida de sistemas tipográficos como **PDF TeX**. Está controlado por 6 opciones: "papel carta" (8,5 x 11 pulgadas), "papel legal" (8,5 x 14 pulgadas), "papel ejecutivo" (7,25 x 10,5 pulgadas), "papel a4" (210 mm x 297 mm), "papel a5". ` (148 mm x 210 mm) y `b5paper` (176 mm x 250 mm). El valor predeterminado es "papel de carta".

```tex
\documentclass[a4paper]{article}
```

### Orientación de la página

La opción "horizontal" formatea la salida para impresión horizontal en el tamaño de papel seleccionado. Efectivamente, hace que LaTeX intercambie las dimensiones de ancho y alto dondequiera que se utilicen durante el proceso de composición tipográfica. La opción "retrato" no tiene ese efecto y se utiliza de forma predeterminada.

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### Modo borrador

Siempre que TeX no puede hacer un salto de línea lo suficientemente bueno (tiene un algoritmo de estimación de "bondad") durante el proceso de construcción del párrafo, produce una línea que se extiende sobre el borde derecho del área de texto. También informa de estos incidentes en el archivo de transcripción (y en el terminal) con advertencias de "casillas demasiado llenas". La opción "borrador" hace que LaTeX marque dichas líneas con cuadros negros en la salida. La opción "final" no produce ningún cuadro negro y se utiliza de forma predeterminada.

### Impresión a dos caras

La opción "openany" permite que los capítulos comiencen en cualquier página, mientras que la opción "openright" hace que todos los capítulos comiencen en la página de la derecha. El valor predeterminado es "openany" en la clase "informe" y "openright" en la clase "libro". Ambas opciones no se reconocen en otras clases de documentos.

### Página para el título

Con la opción `titlepage`, LaTeX crea una página separada para el título producido por el comando `\maketitle`. También hace que el entorno "abstracto" inicie el resumen en una nueva página y haga un salto de página después. El valor predeterminado es `titlepage` para todas las clases excepto `article`, para el cual es `notitlepage`. 

> Estas opciones no son reconocidas por la clase `letra`.

### Fórmulas mostradas numeradas

La opción `leqno` hace que LaTeX coloque números o etiquetas de ecuaciones (fórmula matemática mostrada) en el lado izquierdo, en lugar del lado derecho, que es el comportamiento predeterminado.

### Alineación de fórmulas mostradas

La opción `fleqn` alinea las fórmulas mostradas a la izquierda. De lo contrario, están centrados por defecto.
