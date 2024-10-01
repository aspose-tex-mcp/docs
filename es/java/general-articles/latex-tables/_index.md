---
translation: true
template: /templates/_template-java.md
linktitle: tablas de látex
title: Mesas de látex | Aspose.TeX para Java
weight: 50
url: /java/latex-tables/
keywords: Tablas LaTeX, entorno tabular, diseño de tablas LaTeX, formato de tablas en LaTeX, composición tipográfica de tablas en LaTeX, diseño de tablas LaTeX, espaciado de tablas LaTeX, personalización de tablas LaTeX, alineación de tablas LaTeX, varias filas y columnas en tablas LaTeX
description: Este artículo es una guía rápida para crear tablas funcionales, fáciles de leer, visualmente atractivas y profesionales en LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}

## 1. Introducción

Las tablas desempeñan un papel importante a la hora de mejorar la claridad, la organización y el atractivo visual de los documentos académicos y profesionales. Sirven como una forma poderosa de presentar datos, comparaciones y relaciones complejas en un formato estructurado y fácilmente digerible. A continuación se ofrece una breve descripción de su importancia:

1. **Resumen de datos**: las tablas proporcionan una representación condensada de información que, de otro modo, requeriría varios párrafos para explicarla. Permiten a los autores presentar grandes cantidades de datos de forma concisa, lo que facilita a los lectores la comprensión de los puntos clave.

2. **Visualización clara**: los datos complejos, como cifras estadísticas, resultados de encuestas y hallazgos experimentales, se pueden presentar de manera más efectiva mediante tablas. El formato tabular ayuda a los lectores a identificar tendencias, patrones y valores atípicos mucho más fácilmente.

3. **Análisis comparativo**: las tablas permiten realizar comparaciones en paralelo de diferentes conjuntos de datos. Ya sea comparando especificaciones de productos, desempeño financiero o variables de investigación, las tablas ayudan a los lectores a sacar conclusiones significativas de un vistazo.

4. **Organización lógica**: las tablas proporcionan una estructura lógica que segrega los datos en filas y columnas. Esta organización facilita la presentación de datos que tienen distintas categorías, lo que permite a los lectores navegar fácilmente y encontrar información específica.

5. **Integridad de los datos**: en contextos académicos y profesionales, la precisión de los datos es primordial. Las tablas permiten a los autores presentar datos sin procesar, eliminando el riesgo de mala interpretación que puede surgir cuando los datos se transmiten en forma narrativa.

6. **Referencias y citas**: cuando las tablas están bien etiquetadas y referenciadas adecuadamente, se convierten en valiosos puntos de referencia dentro de un documento. Los autores pueden consultar tablas específicas cuando discuten los hallazgos, lo que facilita a los lectores seguir el argumento.

7. **Compromiso visual**: las tablas bien diseñadas rompen la monotonía del contenido textual, atraen visualmente a los lectores y ayudan a mantenerlos interesados. Contribuyen a la estética general y al profesionalismo de un documento.

8. **Eficiencia en la comunicación**: Los profesionales e investigadores ocupados a menudo necesitan extraer información rápidamente. Las tablas les permiten ver datos y encontrar detalles específicos sin tener que leer párrafos de texto.

9. **Estandarización**: En la investigación académica, las tablas estandarizadas se utilizan con frecuencia para presentar metodologías experimentales, resultados y análisis estadísticos. Esto garantiza la coherencia entre las publicaciones y ayuda a la reproducibilidad de la investigación.

En esencia, las tablas sirven como centros de información, presentando de manera eficiente conocimientos basados ​​en datos mientras mantienen un formato estructurado y fácil de leer. Su función a la hora de transmitir detalles intrincados y al mismo tiempo garantizar la claridad y la accesibilidad los convierte en una herramienta indispensable en la comunicación tanto académica como profesional.

Pasemos ahora a LaTeX como un poderoso sistema de composición tipográfica que permite a los autores transformar sus ideas en documentos bellamente elaborados. LaTeX trasciende las limitaciones de los procesadores de texto tradicionales, ofreciendo un reino de precisión, elegancia y versatilidad que se nota mucho al procesar estructuras tabulares.
En esencia, LaTeX es más que una simple herramienta de preparación de documentos; es una forma de arte que combina la tipografía con la tecnología. Ya sea que esté creando artículos académicos, informes, presentaciones o incluso libros, LaTeX destaca por producir documentos que no sólo son estéticamente agradables sino que también transmiten información con la máxima claridad. Su dominio radica, entre otras cosas, en su perfecta integración de intrincadas estructuras tabulares, que son la columna vertebral de la representación de datos en diversos campos.

Con LaTeX, la disposición de la información dentro de las tablas va más allá de una simple cuadrícula de filas y columnas. Más bien, es una sinfonía cuidadosamente orquestada donde la alineación, el espaciado y el estilo armonizan para proporcionar una presentación refinada de los datos. Las estructuras tabulares en LaTeX se convierten en narrativas visuales que transmiten conjuntos de datos complejos, relaciones y comparaciones con elegancia y precisión.

Al ofrecer muchas herramientas y paquetes adaptados al diseño tabular, LaTeX transforma los datos en una narración visual. Desde controlar el ancho de las columnas hasta ajustar los bordes de las celdas y el sombreado, el nivel de personalización de LaTeX garantiza que cada tabla se alinee perfectamente con el propósito de su documento. Para quienes trabajan con contenido matemático, técnico o científico, la perfecta inclusión de ecuaciones y símbolos dentro de las celdas de la tabla de LaTeX eleva la comunicación de ideas complejas.

Sin embargo, el poder de LaTeX va más allá de la mera estética. Introduce eficiencia a través de mecanismos de referencias cruzadas, convirtiendo las tablas en puntos de referencia de navegación dentro de su documento. Además, los paquetes de LaTeX permiten la creación de diseños complejos que abarcan múltiples filas o columnas, acomodando las presentaciones de datos más exigentes.

Cuanto más profundizas en el mundo de LaTeX, más características matizadas exploras; las características que hacen de LaTeX una herramienta indispensable para científicos, profesionales e investigadores por igual. Se sumergirá en el arte de diseñar tablas que capten la atención, presenten información de manera persuasiva y contribuyan al impacto general de su documento.

## 2. Conceptos básicos de las tablas en LaTeX

El concepto fundamental de tablas en LaTeX gira en torno al entorno "tabular", donde se definen columnas, filas y su contenido para organizar y presentar datos en un formato estructurado y visualmente agradable.

La estructura básica de una tabla en LaTeX involucra los siguientes componentes:

1. **Comience el entorno `tabular`**: Para crear una tabla, incluya el contenido de la tabla dentro de un entorno `tabular`. Este entorno especifica el diseño y la estructura de la tabla.

2. Especificación de columnas: dentro del entorno "tabular", usted define el número de columnas y su alineación utilizando especificadores de columnas. Los especificadores comunes incluyen "l" para columnas alineadas a la izquierda, "c" para columnas centradas y "r" para columnas alineadas a la derecha. También puede especificar qué columnas LaTeX debe separar con líneas verticales y qué bordes exteriores verticales deben dibujarse.

3. **Contenido de la fila**: cada fila de la tabla se crea especificando el contenido de cada celda dentro de la fila. Las celdas están separadas por el símbolo `&` y cada fila termina con el comando `\\`.

4. **Líneas horizontales**: Puede agregar líneas horizontales para separar filas, así como bordes exteriores horizontales, usando el comando `\hline`. Esto mejora la estructura visual de la mesa.

### Ejemplos simples

Aquí hay un ejemplo básico de una tabla LaTeX:

```tex
\begin{tabular}{|c|c|c|}                             \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
\end{tabular}
```

En este ejemplo, el entorno `tabular` se utiliza para crear una tabla con tres columnas, cada una centrada (`c`). El resultado de la composición tipográfica se muestra a continuación:

<a href="/tex/images/java/tutorial/latex-tables-1.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-1.jpg)</a>

El siguiente ejemplo muestra cómo crear una tabla con columnas alineadas a la izquierda y a la derecha.

```tex
\begin{tabular}{|l r||}
  \hline
  Company & Income \\            \hline \hline
  Pinapple Computer & \$150M \\
  Megasoft & \$210M \\
  General Waters Ltd. & \$98M \\
  Alphamet & \$2117M \\           \hline
\end{tabular}
```

El borde exterior derecho está doble, el encabezado también está separado de la tabla por una línea doble, no hay una línea vertical que separe las columnas.

<a href="/tex/images/java/tutorial/latex-tables-2.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-2.jpg)</a>

También puedes dibujar líneas horizontales que no abarquen toda la tabla de izquierda a derecha.

```tex
\begin{tabular}{|r|l|}         \hline
  9D5 & hexadecimal \\
  4725 & octal \\              \cline{2-2}
  1001 1101 0101 & binary \\   \hline \hline
  2517 & decimal \\            \hline
\end{tabular}
```

Aquí, el comando `\cline{i-j}` le dice a LaTeX que dibuje una línea desde la columna i<sup>ésima</sup> hasta la columna j<sup>ésima</sup>.

<a href="/tex/java/latex-tables/latex-tables-3.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](latex-tables-3.jpg)</a>

Las columnas de una tabla pueden tener un ancho fijo, en cuyo caso se denominan columnas de *párrafo*. Para crear este tipo de columnas, utilice el especificador `p` seguido del ancho de la columna entre llaves. Considere el siguiente ejemplo:

```tex
\begin{tabular}{|p{3cm}|p{2cm}|}            \hline
  A short text. & A very very long text. \\ \hline
  A very very long text. \newline And some more text in a new line. & A short text. \\ \hline
\end{tabular}
```

Tenga en cuenta el uso del comando `\newline`.

<a href="/tex/java/latex-tables/latex-tables-4.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-4.jpg)</a>

Con el paquete `array` incluido, hay dos opciones más disponibles para columnas de ancho fijo: `m{width}` - igual que `p{width}`, pero alinea verticalmente el contenido de la celda en el medio;
`b{ancho}`: igual que `p{ancho}`, pero alinea verticalmente el contenido de la celda en la parte inferior.

En el raro caso de que sea necesario incluir una tabla en el texto de un párrafo, puede especificar la posición de la tabla en relación con la línea base de la línea de texto adjunta. Para este propósito, use la opción `t`, `c` (predeterminada) o `b` para alinear la línea base con la parte superior, central o inferior de la tabla. Por ejemplo,

```tex
This is the text of the paragraph
\begin{tabular}[t]{|r|l|}     \hline
  9D5 & hexadecimal \\
  4725 & octal \\             \cline{2-2}
  1001 1101 0101 & binary \\  \hline \hline
  2517 & decimal \\           \hline
\end{tabular}
that include a table.
```

Aquí le decimos a LaTeX que la línea base debe alinearse con la parte inferior de la tabla.

<a href="/tex/java/latex-tables/latex-tables-5.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-5.jpg)</a>

### Definición de varias columnas

Cuando su tabla contiene columnas idénticamente alineadas, puede definirlas todas usando la sintaxis `*{num}{format}`. Esto es especialmente útil cuando su tabla tiene muchas columnas.

```tex
\begin{tabular}{l*{7}{c}r}
  Employee   & Sun & Mon & Tue & Wed & Thu & Fri & Sat & Total \\ \hline
  John Doe   &     &  x  &     &     &     &  x  &     &   2   \\
  Dean Jones &  x  &     &  x  &     &  x  &     &     &   3   \\
  Chris Cross&     &     &     &  x  &     &     &     &   1   \\
  Pete Brad  &     &     &     &     &     &     &  x  &   1
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-6.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-6.jpg)</a>

### Especificación de columna usando `>{\commmand}` y `<{\command}`

Otra forma de especificar columnas es usar `>{\command}` para comandos ejecutados justo *antes* de cada elemento de columna y `<{\command}` para comandos ejecutados justo *después* de cada elemento de columna. Esto está disponible cuando tiene el paquete `array` incluido en el preámbulo del documento. En el siguiente ejemplo, usamos esta sintaxis para centrar cada una de las dos columnas y escribir la primera en negrita.

```tex
\begin{tabular}{>{\centering\textbf\bgroup}p{3.5cm}<{\egroup}>|{\centering}p{3.5cm} }
  History & Geometry
  \tabularnewline \hline
  Ancient & Elementary
  \tabularnewline
  Medieval & Affine 
  \tabularnewline
  Modern & Analytic
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-7.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-7.jpg)</a>

## 3. Personalización del diseño de la mesa

En las tablas de LaTeX, ajustar el espacio es crucial para garantizar que la tabla parezca bien estructurada y visualmente atractiva. El espaciado adecuado mejora la legibilidad y evita la acumulación de contenido. A continuación se muestran algunos aspectos clave del ajuste de espaciado en tablas LaTeX:

### Espaciado entre columnas

LaTeX agrega automáticamente algo de espacio entre columnas. Para ajustar el espacio entre columnas, puede usar el comando `\setlength{\tabcolsep}{value}` antes del entorno tabular. Aumentar el valor aumenta el espacio entre columnas. El valor predeterminado es "6 puntos".

### Espacio entre filas

Para aumentar el espacio entre filas, puede usar el comando `\renewcommand{\arraystretch}{value}` antes del entorno `tabular`. Al aumentar el valor, se separan las filas, mejorando el espaciado vertical de la tabla. El valor predeterminado es "1,0".

También puede especificar el salto después de una línea explícitamente usando pegamento después del terminador de línea.

```tex
\begin{tabular}{cl} \hline
  Level & Complexity \\ [1cm]
  1 & Simple \\
  2 & Intermediate \\
  3 & Complex \\ \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-8.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-8.jpg)</a>

### Usar expresiones `@` y `!`
Al tener el paquete `array` incluido en el preámbulo del documento, puede especificar separadores de columnas con las construcciones `@{...}` o `!{...}`.

Por lo general, toman algo de texto como argumento y, cuando lo agregan a una columna, insertan automáticamente ese texto en cada celda de esa columna antes y/o después de los datos reales de esa celda. El comando `@{...}` reemplaza el espacio entre columnas con el contenido especificado como argumento. Al dejar el argumento vacío, puede suprimir los espacios entre columnas.

Tomemos una tabla básica especificada por el siguiente código:

```tex
\begin{tabular}{|l|l|}
  \hline
  1.1 & 1.2 \\ \hline
  2.1 & 2.2 \\
  \hline
\end{tabular}
```

Al variar la descripción de la columna, obtenemos los siguientes resultados:

<a href="/tex/java/latex-tables/latex-tables-9.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-9.jpg)</a>

Para preservar el espacio inicial, puede utilizar `!{...}`.

<a href="/tex/java/latex-tables/latex-tables-10.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-10.jpg)</a>

Y aquí hay un ejemplo de una columna de números de punto flotante alineados con el punto decimal:

```tex
\begin{tabular}{r@{.}l}
  3 & 14159 \\
  16 & 2 \\
  123 & 456 \\
\end{tabular}

```

<a href="/tex/java/latex-tables/latex-tables-11.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-11.jpg)</a>

### Usando el paquete `dcolumn`

Es posible centrar una columna en el separador decimal usando el paquete `dcolumn`, que proporciona un nuevo especificador de columna para números de punto flotante. La forma sencilla de utilizar este paquete se demuestra en el siguiente ejemplo:

```tex
\usepackage{dcolumn}
................................................
\newcolumntype{d}[1]{D{.}{\cdot}{#1} } %the argument for d specifies the maximum number of decimal places
\begin{tabular}{l r c d{1} }
  Left&Right&Center&\mathrm{Decimal}\\
  1&2&3&4\\
  11&22&33&44\\
  1.1&2.2&3.3&4.4\\
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-12.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-12.jpg)</a>

Tenga en cuenta que una columna alineada con decimales se escribe en modo matemático, de ahí el uso de `\mathrm` para el encabezado de la columna en el ejemplo anterior. Además, el texto de una columna con alineación decimal (por ejemplo, el encabezado) se alineará a la derecha antes del separador decimal (suponiendo que no haya ningún separador decimal en el texto). Si bien esto puede estar bien para textos muy cortos o encabezados de columnas numéricas, parece engorroso en el ejemplo anterior. Una solución a esto es utilizar el comando `\multicolumn` que se describe a continuación, especificando una sola columna y su alineación. Por ejemplo, para centrar el encabezado *Decimal* sobre su columna en el ejemplo anterior, la primera línea de la tabla en sí sería `Izquierda&Derecha&Centro&\multicolumn{1}{c}{Decimal}\\`.

## 4. Fusionar celdas

Se puede obtener una tabla un poco más compleja fusionando celdas horizontal y/o verticalmente.

### Celdas que abarcan varias columnas

La forma general del comando que hace que una celda abarque varias columnas es: `\multicolumn{num_cols}{alignment}{contents}`. Aquí, `num_cols` es el número de columnas que se fusionarán; `alineación` es `l`, `c`, `r` o, para ajustar el texto, `p{ancho}`. Y el "contenido" son los datos que desea colocar en esa celda.

Aquí está el ejemplo sencillo:

```tex
\begin{tabular}{|l|l|}
  \hline
  \multicolumn{2}{|c|}{Available currencies} \\
  \hline
  CNY & Chinese Yuan \\
  JPY & Japanese Yen \\
  GBP & Great Britain Pound \\
  USD & US Dollar \\
  CAD & Canadian Dollar \\
  EUR & Euro \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-13.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-13.jpg)</a>

### Celdas que abarcan varias filas

Para hacer que una celda abarque varias filas, deberá incluir el paquete "multirow". El paquete proporciona el siguiente comando: `\multirow{num_rows}{width}{contents}`.

Aquí, `num_rows` es el número de filas que se fusionarán; `width` es el ancho de la celda (`*` para el ancho natural del contenido) y `contents` son los datos reales que se van a componer en la celda.

```tex
\begin{tabular}{|l|l|l|}
  \hline
  \multicolumn{3}{ |c| }{Available currencies} \\
  \hline
  South America & BRL & Brazilian Real \\ \hline
  \multirow{3}{*}{Asia} & CNY & Chinese Yuan \\
   & JPY & Japanese Yen \\
   & HKD & Hong Kong Dollar \\ \hline
  \multirow{3}{*}{Europe} & EUR & Euro \\
   & GBP & Great Britain Pound \\
   & CHF & Swiss Franc \\ \hline
  Oceania & AUD & Australian Dollar \\ \hline
  \multirow{2}{*}{North America} & USD & US Dollar \\
   & CAD & Canadian Dollar \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-14.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-14.jpg)</a>

Debe recordar que cuando utilice el comando `\multirow`, debe insertar una entrada en blanco para cada celda apropiada en cada fila posterior que se va a abarcar.

### Abarcando celdas en ambas direcciones.

El siguiente ejemplo demuestra cómo abarcar celdas en ambas direcciones simultáneamente y dibujar los bordes correctamente:

```tex
\begin{tabular}{cc|c|c|c|c|l}
  \cline{3-6}
  & & \multicolumn{4}{ c| }{Primes} \\ \cline{3-6}
  & & 2 & 3 & 5 & 7 \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{504} & 3 & 2 & 0 & 1 & \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{540} & 2 & 3 & 1 & 0 & \\ \cline{1-6}
  \multicolumn{1}{ |c }{\multirow{2}{*}{Powers} } &
    \multicolumn{1}{ |c| }{gcd} & 2 & 2 & 0 & 0 & min \\ \cline{2-6}
  \multicolumn{1}{ |c }{} &
    \multicolumn{1}{ |c| }{lcm} & 3 & 3 & 1 & 1 & max \\ \cline{1-6}
\end{tabular}
```

El comando `\multicolumn{1}{` se utiliza para dibujar los bordes verticales izquierdo y derecho. Aunque se combina con `\multirow{2}{*}{...}`, aún dibuja bordes verticales que solo abarcan la primera fila. Para compensar eso, agregamos `\multicolumn{1}{` en las siguientes filas abarcadas por `mutltirow`.

<a href="/tex/java/latex-tables/latex-tables-15.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-15.jpg)</a>

## 5. Tamaño de la mesa

El paquete `graphicx` proporciona el comando `\resizebox{width}{height}{object}` que se puede usar con el entorno `tabular` para estirar o reducir una tabla a un ancho y alto específicos. En el siguiente ejemplo, cambiaremos el tamaño de la tabla a 12 cm de ancho manteniendo la relación de aspecto.

```tex
\resizebox{12cm}{!} {
  \begin{tabular}{|c|c|c|}                           \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
}
```

<a href="/tex/java/latex-tables/latex-tables-16.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-16.jpg)</a>

También puedes usar `\scalebox{ratio}{object}` de la misma manera, pero con proporciones en lugar de tamaño fijo:

```tex
\scalebox{0.7}{
  \begin{tabular}...
  \end{tabular}
}
```

## 6. Mesas de posicionamiento

Puede colocar fácilmente una tabla en una página si la coloca dentro de un entorno de "tabla".

```tex
\begin{table}[positioning_option]
  \centering
  \begin{tabular}{...}
    ...
  \end{tabular}
\end{table}
```

Las opciones de posicionamiento disponibles son:

`h` - colocará la tabla *aquí* aproximadamente.

`t`: coloca la tabla en la *parte superior* de la página.

`b`: coloca la tabla en la *parte inferior* de la página.

`p`: coloca la tabla en una página especial (solo para tablas).

`!` - anula los parámetros internos de LaTeX.

`H`: coloca la mesa en esta ubicación precisa (muy parecido a `h!`).

Para centrar una tabla horizontalmente, puede preceder el entorno "tabular" con el comando "\centering" dentro de un entorno "tabla".

## 7. Títulos, etiquetas y referencias

Puedes subtitular una tabla con algún texto. En la salida, el texto tendrá el prefijo *Table N.*, donde *N* es el número de tabla apropiado que LaTeX rastrea automáticamente. Para hacerlo, use el comando `\caption`. También es posible asignar una etiqueta a una tabla para que se pueda hacer referencia a ella desde cualquier lugar del documento. El par de comandos correspondiente es `\label` y `\ref`. Considere el siguiente ejemplo:

```tex
Table \ref{table:1} is an example of a referenced \LaTeX{} element.

\begin{table}[h!]
  \centering
  \begin{tabular}{|c|c|c|} \hline
    Header 1 & Header 2 & Header 3 \\                \hline
    Row 1, Cell 1 & Row 1, Cell 2 & Row 1, Cell 3 \\ \hline
    Row 2, Cell 1 & Row 2, Cell 2 & Row 2, Cell 3 \\ \hline
  \end{tabular}
  \caption{A caption for the table.}
  \label{table:1}
\end{table}
```

Aquí, la referencia en la primera línea se reemplazará automáticamente con el número establecido por el comando `\label`.

<a href="/tex/java/latex-tables/latex-tables-17.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-17.jpg)</a>

## 8. Tablas para colorear

### Modificación de colores en filas de la tabla

El paquete `xcolor` proporciona los comandos necesarios para producir tablas con colores de fila alternativos. El paquete debe cargarse con la opción de tabla: `\usepackage{table]{xcolor}`.
El comando `\rowcolors{starting_row}{odd_color}{even_color}` debe ocurrir antes de que se inicie el entorno `tabular`.

```tex
\begin{center}
  \rowcolors{2}{green}{pink}

  \begin{tabular}{lll}
    \multicolumn{3}{c}{The header} \\
    odd & odd & odd \\
    even & even & even\\
    \hiderowcolors odd & odd & odd \\
    \showrowcolors even & even & even\\
     even & even & even\\
  \end{tabular}
\end{center}
```

El comando `\hiderowcolors`, proporcionado por el paquete `xcolor`, desactiva el resaltado desde la fila en la que aparece hasta el final de la tabla. Para reactivar el resaltado, utilice el comando `\showrowcolors`.

<a href="/tex/java/latex-tables/latex-tables-18.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-18.jpg)</a>

### Colorear células individuales

Con el paquete `xcolor`, también puedes especificar el color de una celda en particular.

```tex
\begin{tabular}{|l|l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  \cellcolor{red} odd & odd & odd \\
  \hline
  even & \cellcolor{red} even & even\\
  \hline
  odd & odd & \cellcolor{red} odd \\
  \hline
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-19.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-19.jpg)</a>

### Usando el paquete `colortbl`

El paquete `colortbl` proporciona el comando `\columncolor` para especificar el color de la columna en el preámbulo de un entorno tabular dentro de la construcción `>{...}`. Esto significa que también debes tener incluido el paquete `array`. (No olvide incluir también el paquete `xcolor`).

```tex
\begin{tabular}{|>{\columncolor{green}}l|>{\color{white}\columncolor{red}}c|}
  one & two\\
  three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-20.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-20.jpg)</a>
El comando `\rowcolor` se puede utilizar para especificar los colores de las filas. Debe usarse al inicio de la fila. El comando tiene la misma sintaxis que `\columncolor`.

```tex
\begin{tabular}{l|c|}
  \rowcolor{green} one & two\\
  \rowcolor{red} three & four
\end{tabular}
```

<a href="/tex/java/latex-tables/latex-tables-21.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-21.jpg)</a>

También puedes colorear reglas verticales. Por ejemplo, 

```tex
\setlength{\arrayrulewidth}{2pt}
\begin{tabular}{!{\color{blue}\vline} l !{\color{blue}\vline} l !{\color{blue}\vline}
    l !{\color{blue}\vline}}
  \multicolumn{3}{c}{The header} \\
  odd & odd & odd \\
  even & even & even\\
  odd & odd & odd \\
\end{tabular}
```

resultará en

<a href="/tex/java/latex-tables/latex-tables-22.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-22.jpg)</a>

Tenga en cuenta el uso de `\setlength{\arrayrulewidth}{2pt}` para cambiar el grosor de la regla.

Sin embargo, colorear `\hline` y `\cline` es un poco más complicado y está disponible con comandos adicionales (que luego se aplican también a las reglas verticales). El comando `\arrayrulecolor` se puede utilizar globalmente o dentro de una tabla. En ambos casos, afecta a todas las reglas posteriores. Por lo tanto, si desea un color diferente para las reglas verticales, deberá especificarlo en el preámbulo de la tabla. Por ejemplo,

```tex
\setlength\arrayrulewidth{2pt}
%\arrayrulecolor{blue} % to set the color for all rules
\begin{tabular}{|l!{\color{green}\vline}l|l|}
  \multicolumn{3}{c}{The header} \\
  \hline
  odd & odd & odd \\
  \arrayrulecolor{blue} \hline
  even & even & even\\
  \hline
  odd & odd & odd \\ \arrayrulecolor{red}
  \hline
\end{tabular}
```

resultará en

<a href="/tex/java/latex-tables/latex-tables-23.jpg" style="display:inline-block;width:100%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-23.jpg)</a>

## 9. Construyendo mesas largas

El entorno "tabular" tiene una desventaja importante. Produce tablas que no se pueden dividir entre páginas con el algoritmo de división de páginas integrado de TeX. Por lo tanto, si su tabla es larga, simplemente se extenderá debajo de la parte inferior de la página.

Afortunadamente, existe el paquete "longtable", que hoy en día se proporciona en la mayoría de las distribuciones, que define el entorno "longtable" para manejar tablas tan largas. En la mayoría de los aspectos, este entorno funciona de la misma manera que el entorno "tabular". Sin embargo, existen algunas diferencias.

Demostraremos la mayoría de las características de "longtable" en el siguiente ejemplo, donde también puede encontrar notas de uso y diferencias con respecto al entorno "tabular". (El ejemplo también utiliza el paquete `verbatim` para algunos formatos de texto, por lo que también debe incluirse).

```tex
\begin{longtable}{|r||p{1in}|}
  \caption[An optional table caption ...]{A long table\label{long}}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of the table}\\
  \textsc{First}&\textsc{Second}\\
  \hline\hline
  \endfirsthead % Everything above this command will appear at the beginning of the table, in the first page.

  \caption[]{(continued)}\\
  \hline\hline
  \multicolumn{2}{|c|}{This part appears at the top of every other page}\\
  \textbf{First}&\textbf{Second}\\
  \hline\hline
  \endhead % Whatever you put before this command and below \endfirsthead will be displayed at the top of the table in every page except the first one.

  \hline
  This goes at the&bottom.\\
  \hline
  \endfoot % What you put after \endhead and before this command will appear at the bottom of the table in every page except the last one.

  \hline
  These lines will&appear\\
  in place of the & usual foot\\
  at the end& of the table\\
  \hline
  \endlastfoot % The elements after \endfoot and before this command will be displayed at the bottom of the table but only in the last page where the table appears.

  \texttt{longtable} columns are specified& in the \\
  same way as in the \texttt{tabular}& environment.\\
  \verb!|r||p{1in}|! & inthis case. \\
  Each row ends with a & \verb|\\| command. \\
  The \verb|\\| command has an & optional \\
  argument, just as in & the \\
  \texttt{tabular} & environment. \\ [10pt]
  See the effect of \verb|\\[10pt]| & ? \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Also \verb|\hline| may be used, & as in \texttt{tabular}. \\
  \hline
  That was a \verb|\hline| & . \\
  \hline\hline
  That was a \verb|\hline\hline| & . \\
  \multicolumn{2}{||c||}
    {This is a \texttt{\textbackslash multicolumn\{2\}\{||c||\}}} \\
  If a page break occurs at a \verb|\hline| then & a line is drawn \\
  at the bottom of one page and at the & top of the next. \\
  \hline
  The \texttt{[t] [b] [c]} argument of \texttt{tabular} & cannot be used. \\
  The optional argument may be one of & \texttt{[l] [r] [c]} \\
  to specify whether the table should be & adjusted \\
  to the left, right, & or centrally. \\
  \hline\hline
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Lots of lines & like this. \\
  Some lines may take up a lot of space, like this: &
  \raggedleft This last column is a ``p'' column so this ``row'' of the table can take
  up several lines. Note however that \TeX will never break a page within such a row.
  Page breaks only occur between rows of the table or at \verb|\hline| commands.
  \tabularnewline
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  Lots of lines & like this.\\
  \hline
  Lots of lines& like this.\\
  Lots of lines& like this.\\
\end{longtable}
```

Esto dará como resultado dos páginas:

<a href="/tex/java/latex-tables/latex-tables-24.jpg" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-24.jpg)</a>

<a href="/tex/java/latex-tables/latex-tables-25.jpg" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-25.jpg)</a>

No se confunda si no obtiene el mismo resultado después de la primera ejecución de TeX. Debido a las limitaciones técnicas de TeX, es posible que sean necesarias algunas ejecuciones para obtener la tabla que ves en las imágenes.

## 10. Un ejemplo de tabla compleja

Proporcionaremos otro ejemplo bastante complejo de una tabla que combina muchas de las características anteriores.

```tex
\documentclass{article}
  \usepackage{dcolumn}
  \usepackage{verbatim}
  \usepackage{colortbl}
  \usepackage[table]{xcolor}
  \usepackage{longtable}
\begin{document}
  \hbox{}\vspace{100pt} % To make the table break between pages

  \newcolumntype{A}{>{\color{white}\columncolor{red}[.5\tabcolsep]\raggedright}
    p{2cm}}
  \newcolumntype{B}{>{\columncolor{blue}[.5\tabcolsep]\color{yellow}\raggedright}
    p{3cm}}
  \newcolumntype{C}{>{\columncolor{yellow}[.5\tabcolsep]}D{.}{\cdot}{-1}}
  \newcolumntype{E}{>{\large\bfseries \columncolor{cyan}[.5\tabcolsep]}c}
  \newcolumntype{F}{>{\color{white} \columncolor{magenta}[.5\tabcolsep]}c}
  \newcolumntype{G}{>{\columncolor[gray]{0.8}[.5\tabcolsep][\tabcolsep]}l}
  \newcolumntype{H}{>{\columncolor[gray]{0.8}}l}
  \newcolumntype{I}{>{\columncolor[gray]{0.8}[\tabcolsep][.5\tabcolsep]}D{.}{\cdot}
    {-1}}
  \setlength\minrowclearance{2pt} %Before starting give a little space

  \begin{longtable}{ABC}
    \multicolumn{3}{E}{A long table example} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endfirsthead

    \multicolumn{3}{E}{A long table example (continued)} \\
    \multicolumn{2}{F}{First two columns} & \multicolumn{1}{F}{Third column} \\
    \multicolumn{2}{F}{p-type} & \multicolumn{1}{F}{D-type (\textsf{dcolumn})}
    \endhead

    \multicolumn{3}{E}{Continued\ldots}
    \endfoot

    \multicolumn{3}{E}{The End}
    \endlastfoot

    P-column & and another one & 12.34 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6}\\
    Some long text in the first column & bbb & 1.2 \\
    aaa & and some long text in the second column & 1.345 \\
    \multicolumn{1}{G}{Total} & \multicolumn{1}{H}{(wrong)} &
      \multicolumn{1}{I}{100.6} \\
    aaa&bbb & 1.345 \\
    Note that the colored rules in all columns stretch to accommodate large entries
      In one column. & bbb & 1.345 \\
    aaa & bbb & 100 \\
    aaa & Depending on your driver you may get unsightly gaps or lines
      where the `screens' used to produce different shapes interact
      badly. You may want to cause adjacent panels of the same color by
      specifying a larger overhang or by adding some negative space (in a
      \verb|\noalign| between rows. & 12.4 \\
    aaa & bbb & 45.3 \\
  \end{longtable}
\end{document}
```

Antes del entorno `longtable`, definimos los tipos de columnas con el comando `\newcolumntype` proporcionado por el paquete `dcolumn`. Dentro de los argumentos, usamos la notación `>{...}` para definir formatos de columna. Las definiciones de columnas, a su vez, utilizan comandos que especifican colores, alineación, fuentes y anchos de columna. El entorno "longtable" en sí es otra característica empleada. Dentro del entorno, usamos el comando `\multicolumn` para fusionar celdas horizontalmente junto con los tipos de columnas previamente definidos.

El resultado de todos los esfuerzos está a continuación:

<a href="/tex/java/latex-tables/latex-tables-26.jpg" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-26.jpg)</a>

<a href="/tex/java/latex-tables/latex-tables-27.jpg" style="display:inline-block;width:49%;">![Salida de ejemplo](/tex/images/java/tutorial/latex-tables-27.jpg)</a>

## 11. Mejores prácticas y consejos

Componer tablas en LaTeX puede ser una tarea matizada, pero seguir las mejores prácticas y consejos puede ayudarle a crear tablas claras, estéticamente agradables y de aspecto profesional. A continuación se presentan algunas prácticas recomendadas y consejos valiosos para componer tablas en LaTeX:
1. **Utilice encabezados de columna significativos:**
   - Proporcione encabezados claros y descriptivos para cada columna para guiar a los lectores en la comprensión del contenido.
   
2. **Alinear datos numéricos con el punto decimal:**
   - Al presentar datos numéricos, alinee los números con el punto decimal para mejorar la legibilidad. Puede utilizar el paquete `dcolumn` para este propósito.
   
3. **Evite las enredaderas verticales**:
   - En publicaciones profesionales, se suele recomendar evitar el uso de líneas verticales para separar columnas. Utilice líneas horizontales con moderación para mayor claridad.

4. **Mantenga la coherencia:**
   - Mantenga un formato coherente en todo el documento, incluidas las fuentes, los tamaños de fuente y la alineación dentro de las tablas.
   
5. **Minimizar el contenido de la celda:**
   - Evitar sobrecargar las celdas con contenido excesivo. Si una celda contiene demasiado texto, considere dividirla en varias filas o columnas.
   
6. **Agregar títulos y etiquetas:**
   - Incluya títulos informativos encima o debajo de sus tablas y use el comando `\label` para habilitar las referencias cruzadas dentro de su documento.

7. **Emplee `multifila` y `multicolumna` con moderación:**
    - Si bien `multirow` y `multicolumn` son útiles para fusionar celdas, evite el uso excesivo ya que puede hacer que las tablas sean complejas y difíciles de leer.

8. **Evite tablas demasiado complejas:**
    - Si sus datos son demasiado complejos para una sola tabla, considere dividirlos en varias tablas más pequeñas o utilizar otras ayudas visuales como gráficos o tablas.
    
9. **Utilice el espacio horizontal con cuidado:**
    - Ajuste el espacio entre columnas usando `\setlength{\tabcolsep}{value}` y el espacio entre filas usando `\renewcommand{\arraystretch}{value}` para optimizar el diseño de la tabla.

10. **Revisa tus tablas:**
    - Revise cuidadosamente y verifique si hay errores en sus tablas, incluida la precisión, el formato y la alineación de los datos.
    
Al implementar estas mejores prácticas y consejos, puede crear tablas LaTeX que no solo comuniquen sus datos de manera efectiva, sino que también mejoren la calidad general y el profesionalismo de sus documentos.

## 12. Conclusión

Hemos viajado por el intrincado mundo de las estructuras de las tablas en LaTeX, descubriendo la notable versatilidad y precisión que ofrece este sistema tipográfico. La capacidad de LaTeX para integrar perfectamente tablas en documentos permite a los usuarios comunicar datos, comparaciones y relaciones complejas con gracia y claridad.

Desde los conceptos fundamentales del entorno "tabular" hasta técnicas avanzadas que involucran paquetes "multirow" y "longtable", hemos explorado las herramientas y estrategias que hacen de LaTeX una potencia para crear tablas. Hemos aprendido cómo LaTeX no sólo embellece nuestras tablas sino que también agiliza la presentación de datos, ayudando a una comunicación efectiva. 

Hemos enfatizado la importancia de las mejores prácticas: encabezados de columna significativos, alineación, espaciado adecuado y coherencia. Estas prácticas nos permiten crear mesas que no sólo son funcionales sino también visualmente atractivas y profesionales.

A medida que continúe explorando LaTeX, recuerde que dominar las estructuras de las tablas es tanto un arte como una ciencia. Es una habilidad que puede mejorar significativamente el impacto de sus trabajos, informes y presentaciones académicos. 

Entonces, armado con el conocimiento de las capacidades de las tablas de LaTeX, lleve sus documentos al siguiente nivel. Experimente, perfeccione e innove en el ámbito de las estructuras de tablas y deje que LaTeX sea su compañero confiable en la elaboración de documentos que transmitan información de manera efectiva, hermosa y profesional.