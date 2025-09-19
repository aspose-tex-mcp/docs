---
translation: true
template: /templates/_template-java.md
linktitle: Cómo utilizar fuentes LaTeX en texto
title: 3. Cómo utilizar fuentes LaTeX en texto
weight: 30
url: /java/latex-text-fonts/
keywords: LaTeX, fuentes de LaTeX, comandos de fuente de texto de LaTeX, LaTeX grande, tamaño de fuente de LaTeX
description: Este artículo cubre los comandos de fuentes LaTeX que cambian de forma independiente diferentes atributos de fuente para su uso en texto normal.
lastmod: "2024-10-30"
---

{{<section overview>}}

Cuando escribe un documento LaTeX, las etiquetas de marcado utilizadas para estructurar el documento eligen automáticamente las fuentes apropiadas. Por ejemplo, para el encabezado de una sección, los atributos de fuente como tamaño grande y negrita se definen por la clase de documento y se aplican cuando se utiliza el comando `\section`. Por lo tanto, rara vez será necesario especificar los atributos de fuente directamente.

Pero a veces es necesario. Por ejemplo, es posible que desees elegir una familia de fuentes diferente (u otro atributo de fuente general) para el texto principal. Esta modificación a menudo puede realizarse de forma tan sencilla como especificar un paquete apropiado.

Otro caso es cuando desea marcar ciertos fragmentos del documento como especiales, por ejemplo, para indicar siglas, ejemplos o nombres de empresas. Si elige utilizar, digamos, una fuente sans serif para estos fragmentos, puede hacerlo rodeando los nombres de las empresas con `\textsf{...}`. Pero la mejor práctica es definir un nuevo comando (por ejemplo, `\Company`) para este propósito. Definir comandos individuales para cosas lógicamente diferentes hace que sea más fácil cambiar el formato más adelante de manera consistente.

También es posible que desees componer una tabla en un tamaño más pequeño para que quepa en una página. Dado que las clases de documentos pueden formatear documentos automáticamente sólo hasta cierto punto, este deseo es legítimo. De ello se deduce que el formateo manual, al igual que la inserción de saltos de página, suele ser necesario para crear una versión final. Desafortunadamente, el formato explícito hace que el uso posterior del documento sea difícil y propenso a errores. Por lo tanto, se debe minimizar el uso directo de comandos de cambio de fuente en un documento. Esto también es válido para todos los comandos de formato visual.


## 3.1. Cómo usar comandos de fuentes en LaTeX estándar

La fuente utilizada para el texto principal de un documento se denomina *fuente principal*, *fuente del cuerpo* o *fuente normal*. Se selecciona automáticamente al principio del documento y en determinadas construcciones, como notas a pie de página y figuras. Los encabezados de sección y otras etiquetas de marcado lógico cambian automáticamente a un tipo de letra o tamaño diferente, según la clase de documento. Por lo tanto, introducir el marcado lógico correcto es la única acción que se requiere del autor. Sin embargo, a veces puede resultar conveniente resaltar manualmente determinadas partes del texto eligiendo un tipo de letra adecuado. Esto se hace con los comandos que se describen a continuación.

Hay dos formas para la mayoría de los comandos de cambio de fuente: un comando con un argumento, como `\textbf{...}`, y una declaración, como `\bfseries`. La forma declarativa no toma argumentos sino que le indica a LaTeX que de ahora en adelante (hasta el final del grupo actual de llaves o entornos) debe comportarse de una manera especial. Esto significa que no debes escribir algo como `\bfseries{...}`, porque esto pondría todo en negrita desde este punto hasta el final del entorno actual.

Es mejor utilizar los comandos de fuentes con un argumento para cambiar las fuentes de palabras individuales o frases cortas dentro de su documento. Para fragmentos más largos, debe utilizar la forma de entorno de la declaración, como se muestra en el siguiente ejemplo:

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![La forma del entorno de \bfseries](/tex/images/java/tutorial/latex-font-selection-3-1.png)

Las formas declarativas en sí mismas suelen ser mejores para definir nuevos entornos o comandos.

> También es importante que los comandos de fuente con un argumento no permitan saltos de párrafo en sus argumentos.

### La fuente principal del documento.

Usando el comando `\textnormal` o la declaración `\normalfont`, puede cambiar a la fuente del documento principal. Por lo general, ocurren solo en las definiciones de comandos o entornos cuando es importante definir una manera de escribir siempre con la misma fuente, independientemente de las condiciones del entorno. Por ejemplo, el comando para escribir nombres de comandos LaTeX tendría el siguiente aspecto:

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

El uso de `\normalfont` evita que los nombres de los comandos aparezcan en cursiva incluso dentro del texto escrito en cursiva.

### Familias de fuentes estándar

De forma predeterminada, LaTeX mantiene tres familias de fuentes: una fuente de texto serif, a la que se accede con el comando `\textrm`; una fuente de texto sans serif, a la que se accede mediante `\textsf`; y una fuente de máquina de escribir (monoespaciada), a la que se accede mediante `\texttt`. Las formas de declaración de estos comandos son `\rmfamily`, `\sffamily` y `\ttfamily`, respectivamente.

Los nombres exactos de las familias de fuentes externas a las que acceden estos comandos dependen de la clase de documento, pero se pueden cambiar en el preámbulo o por paquetes. Como valor predeterminado de instalación, la familia de fuentes serif es **Computer Modern Roman**, la familia sans serif es **Computer Modern Sans** y la familia de máquinas de escribir es **Computer Modern Typewriter**. Si utiliza una configuración diferente, debe tener cuidado de definir estas familias de fuentes predeterminadas para que las fuentes se puedan mezclar sin conflictos visuales. También es importante asegurarse de que las fuentes externas estén disponibles en la resolución correcta para el dispositivo de salida de destino.

La mayoría de las clases de documentos establecen la fuente serif, a la que se accede mediante `\textrm`, como la fuente principal del documento, por lo que el comando `\textrm` no se usa con frecuencia. Pero si un diseñador de documentos ha elegido una fuente sans serif como tipo de letra principal, `\textrm` sería la familia de fuentes serif alternativa.

### Serie de fuentes estándar

En LaTeX, la *serie* es una combinación de dos atributos: ancho y peso (negrita). LaTeX permite cambiar la serie con dos comandos: `\textmd` y `\textbf`. Las declaraciones correspondientes son `\mdseries` y `\bfseries`, respectivamente. El primer comando selecciona una fuente con valores medios para el ancho y el peso, mientras que el último cambia a una serie más audaz. Nuevamente, los valores reales dependen de la clase de documento y sus opciones o paquetes posteriores. En una configuración predeterminada, `\textbf` cambia a una versión extendida en negrita del tipo de letra actual, mientras que `\textmd` regresa a la versión de ancho y peso medio del tipo de letra actual.

### Formas de fuente estándar

La *forma* del tipo de letra actual es el tercer atributo de fuente que se puede cambiar independientemente de los demás. La forma predeterminada para la mayoría de los documentos es la forma vertical, a la que se puede acceder con el comando `\textup` o la declaración `\upshape` si es necesario.

Los comandos más utilizados parecen ser `\textit` y `\textsc`, que cambian a cursiva o versalitas, respectivamente. Las declaraciones correspondientes son `\itshape` y `\scshape`.

El comando `\textsl` (su forma de declaración es `\slshape`) cambia a la forma inclinada. Una familia de fuentes a menudo contiene solo una forma en cursiva o inclinada, aunque Computer Modern Roman contiene ambas.

En el punto en el que se cambia de inclinado a vertical, los caracteres suelen acercarse demasiado, especialmente si el último carácter inclinado tiene un ascendente. La cantidad adecuada de espacio adicional que se debe agregar en este límite se denomina **corrección en cursiva**. El ancho exacto de este espacio depende del carácter individual y se almacena en el archivo `.tfm`. Los comandos de fuente con argumentos agregan automáticamente la corrección de cursiva, pero cuando se emplean declaraciones, se debe insertar manualmente usando `\/`. Para una fuente vertical, la corrección de cursiva de los caracteres suele ser nula o muy pequeña, aunque existen algunas excepciones. El siguiente ejemplo muestra cómo utilizar correctamente declaraciones de cambio de forma que cambian a formas inclinadas.

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![La corrección en cursiva](/tex/images/java/tutorial/latex-font-selection-3-2.png)
A veces se utilizan versalitas en los títulos o para dar formato a los nombres. Para el último caso, puede, por ejemplo, definir el comando `\name` de la siguiente manera:

```tex
\newcommand\name[1]{\textsc{#1}}
```

Alternativamente, puede utilizar dos declaraciones:

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

El primer comando simplemente cambia a la forma de versalitas, mientras que el segundo formulario inicialmente restablece todos los atributos de fuente a sus valores predeterminados. La opción a elegir depende de las fuentes disponibles y del tipo de documento. Con Computer Modern, solo las familias Roman y Typewriter contienen formas de versalitas, por lo que la segunda definición podría preferirse en ciertas aplicaciones porque usará versalitas (aunque con serifa) incluso en un contexto `\sffamily`. El primer comando solicitaría una fuente con forma de serie mediana, versalitas y de la familia Computer Modern Sans. Esta fuente no está disponible, por lo que LaTeX intentaría encontrar un sustituto cambiando primero el atributo de forma a su valor predeterminado. Como resultado, no obtendría pequeñas capitalizaciones.

Otro comando de forma especial de LaTeX es el comando `\emph`, que enfatiza fragmentos en texto normal. Su forma declarativa es `\em`. Como tradición, las palabras enfatizadas en el texto se ponen en cursiva; pero si se desea enfatizar un fragmento del texto que ya está en cursiva, generalmente se vuelve a la fuente vertical. El comando `\emph` soporta esta convención al cambiar a la forma `\itshape` si la fuente actual está vertical, y a la forma `\upshape` si la fuente actual ya está inclinada (es decir, si la forma es `\itshape ` o `\slshape`). Por lo tanto, el usuario no tiene que preocuparse por el estado actual del texto cuando usa el comando `\emph` o la declaración `\em`.

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![Enfatizando fragmentos de texto](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### Tamaños de fuente estándar

Hay 10 comandos de cambio de tamaño en LaTeX. Estos comandos no tienen formas de comando correspondientes con un argumento, ya que los cambios de tamaño de fuente normalmente se usan solo en las definiciones de los comandos.

![Tamaños de fuente estándar](/tex/images/java/tutorial/latex-font-selection-3-4.png)

El tamaño seleccionado por estos comandos depende de la configuración de la clase de documento y posiblemente de las opciones (por ejemplo, `11pt`) especificadas con ella. En general, `\normalsize` corresponde al tamaño principal del documento, y los comandos de cambio de tamaño forman una secuencia ordenada que comienza con `\tiny` como el tamaño más pequeño y llega hasta `\Huge` como el tamaño más grande. Puede ocurrir que más de un comando haga referencia al mismo tamaño. Por ejemplo, cuando se elige un `\normalsize` grande, `\Huge` puede ser lo mismo que `\huge`. Pero el orden siempre se respeta.

Los comandos de cambio de tamaño para los tamaños de texto principales (es decir, `\normalsize`, `\small` y `\footnotesize`) normalmente afectan el espaciado entre listas y visualizaciones. Por lo tanto, para cambiar su comportamiento, no se debe simplemente reemplazar su definición con una llamada a `\fontsize`, sino comenzar desde su definición original, como se documenta en `classes.dtx`.

## 3.2. Cómo combinar comandos de fuentes estándar

Como ya se mostró, los comandos y declaraciones estándar de cambio de fuente se pueden combinar, lo que da como resultado la selección de un tipo de letra que coincida con la combinación de atributos de fuente. Vea el ejemplo a continuación:

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![Combinaciones de comandos de fuentes LaTeX](/tex/images/java/tutorial/latex-font-selection-3-5.png)

Internamente, el comando `\sffamily` cambia a la familia predeterminada sans serif, luego `\bfseries` cambia a la serie en negrita predeterminada en esta familia y, finalmente, `\large` selecciona un tamaño grande pero deja todos los demás atributos sin cambios. El interlineado parece no haber cambiado porque el alcance de "\large" termina antes del final del párrafo. Los archivos de métricas de fuentes se cargan para todos los tipos de letra intermedios, incluso si estas fuentes nunca se utilizan. En el ejemplo anterior, serían "sans serif medium 10pt" después de `\sffamily`, luego "sans serif negrita extendida 10pt" después de `\bfseries` y, finalmente, "sans serif negrita extendida 14pt", que es la fuente que realmente se utiliza. Por lo tanto, estos comandos de alto nivel pueden forzar la selección de fuentes de LaTeX para cargar innecesariamente fuentes que nunca se utilizan. Sólo hay una pequeña pérdida de velocidad de procesamiento cuando se utiliza una combinación determinada por primera vez. Pero si tiene muchas combinaciones diferentes de este tipo, debería considerar definirlas en términos de [declaraciones primitivas de cambio de fuente](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/).

## 3.3. Comparación de declaraciones y comandos de fuentes

Todos los comandos de cambio de fuente con argumentos comienzan con `\text...` (excepto `\emph`) para enfatizar que están destinados a usarse en texto normal. El uso de dichos comandos en lugar de las formas declarativas tiene la ventaja de mantener la coherencia con otras construcciones de LaTeX. Están destinados a componer fragmentos cortos de texto en una familia, serie o forma específica. La siguiente tabla muestra el efecto de estos comandos.

![Comandos y declaraciones](/tex/images/java/tutorial/latex-font-selection-3-6.png)

Otra ventaja de estos comandos es que insertan automáticamente cualquier corrección en cursiva necesaria a ambos lados de su argumento. Por lo tanto, no tiene que preocuparse por perder correcciones en cursiva al cambiar las fuentes.

La corrección en cursiva insertada automáticamente es incorrecta en muy pocas situaciones. Generalmente se recomienda omitir la corrección de cursiva si un pequeño carácter de puntuación (una coma o un punto) sigue directamente al cambio de fuente. Puedes definir en qué casos se debe suprimir la corrección en cursiva. Esto se hace especificando los caracteres que deben cancelar una corrección en cursiva anterior en la lista `\nocorrlist`. La definición predeterminada para este comando es

```tex
\newcommand{\nocorrlist}{,.}
```

También es posible suprimir la corrección en cursiva en casos individuales. Para ello, se proporciona el comando `\nocorr`. Tenga en cuenta que debe colocar `\nocorr` en el extremo izquierdo o derecho dentro del argumento de los comandos `\text...`, dependiendo de qué lado del fragmento necesita la supresión de la corrección en cursiva.

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![La corrección en cursiva](/tex/images/java/tutorial/latex-font-selection-3-7.png)

Por el contrario, los formularios de declaración suelen ser más adecuados para definir sus propios comandos o entornos.

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![La lista con elementos en negrita](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. Cómo acceder a todos los caracteres de una fuente

Incluso si existe un carácter en una fuente, a veces es imposible ingresarlo desde el teclado. Se puede acceder a muchos caracteres útiles mediante comandos como `\ss` o `\AE`. Algunos caracteres pueden generarse implícitamente a partir de secuencias de letras como `ffi`, que produce la ligadura "ffi", y `---`, que produce el guión largo en las fuentes TeX estándar.

Además, el comando `\symbol` le permite acceder a cualquier carácter de una fuente proporcionando su número en el esquema de codificación actual como número decimal, octal (precedido por `'`) o hexadecimal (precedido por `"`). .

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![El comando \symbol](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. Cómo cambiar las fuentes de texto predeterminadas

Si desea modificar fácilmente la apariencia general de un documento, puede utilizar los ganchos integrados de LaTeX que modifican el comportamiento de los comandos de cambio de fuente de alto nivel discutidos anteriormente. Los valores de estos enlaces se pueden establecer en archivos de paquete o en el preámbulo de un documento usando `\renewcommand`. Aquí está la lista de los ganchos:

![Los ganchos para el cambio de fuente de alto nivel](/tex/images/java/tutorial/latex-font-selection-3-10.png)
Por ejemplo, si escribe en el preámbulo

```tex
\renewcommand\familydefault{cmss}
```

saldría un documento completo en Computer Modern Sans, porque esta redefinición cambia la familia de fuentes para la fuente principal utilizada por LaTeX. En detalle, la fuente del documento principal está determinada por los valores de `\encodingdefault`, `\familydefault`, `\seriesdefault` y `\shapeefault`. Esto significa que debe asegurarse de que estos comandos estén definidos de tal manera que su combinación apunte a una forma de fuente existente en las tablas internas de LaTeX.

El valor predeterminado de `\encodingdefault` (`OT1`) en realidad sirve para la compatibilidad. Esto significa que LaTeX supone que la mayoría de las fuentes utilizan la codificación original. En la mayoría de las circunstancias, es mejor utilizar la codificación "T1" porque contiene muchos glifos adicionales que no están disponibles con "OT1" y permite la separación de palabras adecuada para palabras con caracteres acentuados. Hoy en día, algunas fuentes no son compatibles con "OT1" en absoluto, ya que están diseñadas para usarse con "T1".

Es importante recordar que no todas las fuentes se pueden utilizar como valor predeterminado para la codificación de documentos. Un requisito previo es que la codificación incluya la mayoría de las letras ASCII visibles en sus posiciones estándar. El `\encodingdefault` se puede cambiar cargando el paquete `fontenc` con una o más opciones.

La configuración inicial de `\familydefault` significa que cambiar `\rmdefault` implícitamente cambiará `\familydefault` al nuevo valor, siempre y cuando no se defina una configuración especial para `\familydefault`. Pero si se cambia `\familydefault`, `\rmdefault` no se ve afectado.