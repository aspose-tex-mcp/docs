---
translation: true
template: /templates/_template-java.md
linktitle: Visualización y alineación
title: 2. Visualización y alineación de ecuaciones LaTeX | LaTeX
weight: 10
url: /java/latex-structures-for-equations/
keywords: ams-latex, amsmath, opciones de amsmath, alineación de ecuaciones de látex, leqno, eqno, fleqn, etiqueta de ecuación de látex, etiqueta de ecuación de látex, ecuaciones de alineación de látex
description: Esta es una introducción a la composición tipográfica de ecuaciones LaTeX con paquetes AMS-LATEX y proporciona algunos ejemplos y sus explicaciones.
lastmod: "2024-10-30"
---

{{<section overview>}}


El paquete *amsmath* contiene varias definiciones de entornos para escribir fórmulas matemáticas mostradas. Se pueden clasificar por el número de líneas de material (únicas o múltiples) y por el número de puntos de alineación.

> En esta sección, utilizaremos el término *ecuación* de la siguiente manera: para referirnos a una parte *lógica* distinta de una representación matemática, que a menudo se numera como referencia y también se etiqueta (por ejemplo, por su número entre paréntesis). Estas etiquetas también se denominan *etiquetas*.

La siguiente lista contiene los entornos de visualización más populares. En su caso, se han destacado formas en las que no hay etiquetado de las ecuaciones.

||
|---|---|---|
| `ecuación` | `ecuación*` | Una recta, una ecuación |
| `multilínea` | `multilínea*` | Una ecuación de múltiples líneas no alineada, un número de ecuación |
| `reunir` | `reunir*` | Varias ecuaciones sin alineación |
| `alinear` | `alinear*` | Varias ecuaciones con múltiples alineamientos |
| `flaligar` | `flaign*` | Varias ecuaciones: forma extendida horizontalmente de "alinear" |
| `dividir` | | Una alineación simple dentro de una ecuación de múltiples líneas |

Todos los ejemplos de este capítulo están escritos con el material matemático centrado y los números de ecuación (etiquetas) a la derecha. Para visualizar el posicionamiento, presentamos líneas verticales azules en la salida que representan los márgenes izquierdo y derecho, así como la línea central. En el código fuente de LaTeX, utilizamos el comentario `% -----...` para separar las líneas que deben colocarse en el preámbulo del documento de las que deben colocarse en el cuerpo.

```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

Si desea colocar las matemáticas en una sangría fija desde el margen izquierdo, en lugar de centrarlas en la columna de texto, la opción `fleqn` está disponible. Puede especificar el tamaño de la sangría en el preámbulo estableciendo el valor de la longitud del caucho `\mathindent`. Su valor predeterminado es el mismo que la sangría de una lista de primer nivel. Si está satisfecho con este valor, puede omitir la configuración de la longitud `\mathindent`.

```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn,reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

No es necesario pasar la opción `reqno` aquí (ya que es la predeterminada), pero anula la configuración de la clase de documento, por lo que el número de ecuación se fuerza hacia la derecha pase lo que pase.

En LaTeX estándar, `&` y `\\` se utilizan para la separación de columnas y líneas dentro de las alineaciones mostradas. Los detalles de su uso cambian en los entornos "amsmath".

## 2.1. Comparación con LaTeX estándar

Algunos de los entornos de visualización de varias líneas le permiten alinear partes de la fórmula. En comparación con los entornos LaTeX estándar `eqnarray` y `eqnarray*`, las estructuras definidas en el paquete `amsmath` proporcionan una forma ligeramente diferente y más sencilla de marcar los puntos de alineación. En LaTeX estándar, `eqnarray*` es similar a un entorno `array` con `{rcl}` como preámbulo, lo que significa que se requieren dos caracteres `&` para indicar los dos puntos de alineación. En el paquete `amsmath`, las estructuras equivalentes tienen solo un punto de alineación (como si `array` tuviera un preámbulo `{rl}`), por lo que necesitas colocar solo un carácter `&` a la izquierda del símbolo (generalmente una relación) que debería estar alineada.

El entorno `eqnarray` produce espacio adicional en los puntos de alineación dependiendo de la configuración de los parámetros para `array`. Las estructuras "amsmath", al mismo tiempo, dan un espacio fijo. La diferencia se ilustra claramente en el siguiente ejemplo. La misma ecuación se compone utilizando los entornos `equation`, `align` y `eqnarray`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![Amsmath comparado con LaTeX estándar](/tex/images/java/tutorial/latex-ams-math-2-3.png)

Tenga en cuenta que los espacios en el entorno `eqnarray` resultan demasiado anchos para los estándares convencionales de composición tipográfica matemática.
Como en LATEX estándar, las líneas en una pantalla `amsmath` están marcadas con `\\` (o el final del entorno). Debido a que el salto de línea en una visualización matemática generalmente requiere una comprensión profunda de la estructura de la fórmula, comúnmente se considera que está más allá de las capacidades del software actual.

## 2.2. Una sola ecuación en una línea

El entorno de "ecuaciones" puede producir una sola ecuación. Automáticamente se genera una etiqueta que se coloca en el extremo izquierdo o derecho según la opción en uso. El entorno `ecuación*` produce la misma ecuación sin etiqueta. LaTeX estándar también tiene "ecuación", pero no "ecuación*", ya que esta última es similar al entorno matemático mostrado estándar.

Un hecho destacable es que la presencia de la etiqueta no afecta al posicionamiento del contenido. La etiqueta se moverá hacia arriba o hacia abajo en caso de que no haya suficiente espacio para ella en una línea: a la línea anterior cuando las etiquetas de ecuación están a la izquierda y a la línea siguiente cuando las etiquetas están a la derecha.

```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![Una sola ecuación en una línea](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. Una sola ecuación en varias rectas sin alineación

Una variación del entorno de "ecuación" es el entorno "multilínea". Se utiliza sólo para ecuaciones que no caben en una sola línea. El carácter `\\` debe usarse para marcar los saltos de línea, ya que no se encuentran automáticamente.

La primera línea de la "línea múltiple" se alineará en una sangría del margen izquierdo y la última en la misma sangría del margen derecho. El valor de la longitud `\multlinegap` define el tamaño de esta sangría.

Cada línea, excepto la primera y la última, se centra individualmente dentro del ancho de visualización (a menos que se utilice la opción `fleqn`). Sin embargo, si agrega el comando `\shoveleft` o `\shoveright` dentro de una línea, esa línea se forzará hacia la izquierda o hacia la derecha.

Un entorno "multilínea" tiene una sola etiqueta, ya que lógicamente es una sola ecuación. Por lo tanto, ninguna de las líneas individuales se puede cambiar mediante el uso de `\tag` o `\notag`. La etiqueta, si está presente, se coloca al ras a la derecha/izquierda en la última/primera línea cuando se usa la opción `reqno`/`leqno`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![Una sola ecuación en varias rectas](/tex/images/java/tutorial/latex-ams-math-2-5.png)

El siguiente ejemplo muestra cómo `\multlinegap` afecta el resultado. En el primer caso, los "*dy*" se alinean, lo que parece como si faltara una etiqueta en la primera línea de la ecuación. Cuando `\multlinegap` se establece en `0`, el espacio a la izquierda de la segunda línea no cambia debido a la etiqueta, mientras que la primera línea se desplaza hacia el margen izquierdo, dejando claro que se trata de una ecuación única. .

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![El efecto \multilinegap](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. Una sola ecuación en varias rectas con alineación.

Cuando necesite alinear una sola ecuación multilínea, el entorno "dividido" está a su servicio. Simplemente use un único carácter `&` en cada línea para marcar los puntos de alineación.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![Una sola ecuación con alineación simple](/tex/images/java/tutorial/latex-ams-math-2-7.png)

Una "división" en sí misma no crea una etiqueta de ecuación (por lo que la variante destacada no es necesaria), porque siempre se usa como contenido de una única ecuación. Para ello, puede colocarlo en un entorno exterior.

De forma predeterminada, la etiqueta (así como cualquier parte de la ecuación fuera del "dividido") se centra verticalmente en la altura total del material del entorno "dividido". Este comportamiento corresponde a la opción `centertags`. Cuando especifica la opción `tbtags`, la etiqueta se coloca en la última línea de `split` cuando la etiqueta está a la derecha y en la primera línea cuando la etiqueta está a la izquierda.

```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![Una sola ecuación con alineación simple y la etiqueta en la última línea](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. Grupos de ecuaciones sin alineación

Cuando necesite colocar dos o más ecuaciones en una sola pantalla sin alineación entre las ecuaciones, puede utilizar el entorno "reunir". También centra por separado cada ecuación dentro del ancho de la pantalla y se equipa con una etiqueta individual, si es necesario. Cada línea de un "reunión" es lógicamente una única ecuación.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Grupo de ecuaciones sin alineación](/tex/images/java/tutorial/latex-ams-math-2-9.png)

Es posible que necesites suprimir el número de ecuación de una línea determinada. El comando `\notag`, colocado en la línea lógica, es la respuesta. El entorno `gather` no etiqueta ecuaciones en absoluto.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Grupo de ecuaciones con etiquetas omitidas](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. Grupos de ecuaciones con alineación simple.

Cuando necesita componer más de una ecuación en una sola pantalla y alinearlas verticalmente, el entorno "alinear" viene al rescate. En el caso más simple, utiliza un único `&` en cada línea para marcar el punto de alineación.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![Grupos de ecuaciones con alineación simple](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. Múltiples alineaciones

Un entorno de "alineación" puede definir múltiples puntos de alineación. El diseño contiene tantos pares de columnas como sea necesario y es similar a una `matriz` con el preámbulo similar a `{rlrl...}`. Suponiendo que consta de *n* pares de columnas `rl`, el número de `&` por línea será *2n - 1*: uno para la alineación dentro de cada par de columnas, lo que da *n*; y *n - 1* `&` para separar los pares de columnas.

El entorno "alinear" distribuye el material uniformemente a lo largo del ancho de la pantalla. Si hay espacio adicional, se distribuye equitativamente entre los pares de columnas adyacentes y los dos márgenes de visualización.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![Múltiples alineamientos](/tex/images/java/tutorial/latex-ams-math-2-12.png)

El diseño de `flalign` es similar, pero no hay espacios en los márgenes. En el siguiente ejemplo, puedes ver que la ecuación (3) cabe en una sola línea debido a este hecho (mientras que la ecuación (2) todavía no).

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![flaligar](/tex/images/java/tutorial/latex-ams-math-2-13.png)

En ambos casos, el espacio mínimo entre pares de columnas se puede establecer cambiando `\minalignsep`. El valor predeterminado es `10pt` y se puede cambiar con `\renewcommand`, ya que es un comando macro en lugar de un parámetro de longitud. El siguiente ejemplo demuestra el efecto de cambiar `\minalignsep`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![\minalignsep efecto](/tex/images/java/tutorial/latex-ams-math-2-14.png)

El siguiente ejemplo ilustra un uso muy común de "alinear". Tenga en cuenta el uso de `\text` para producir texto normal dentro del material matemático.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![El uso de \text](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. Visualizaciones interrumpidas: `\intertext`

Es posible que desee colocar un pequeño fragmento de texto entre las líneas de una alineación de visualización. Esto se hace con el comando `\intertext`. Es muy importante que todas las propiedades de alineación no se vean afectadas por el texto, mientras que el texto en sí se compone como un párrafo normal ajustado al ancho de visualización. La alineación no funcionará si simplemente finaliza la visualización y luego comienza una nueva después del texto. Este comando siempre debe seguir inmediatamente a un comando `\\` o `\\*`.

``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![El comando \intertext](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> Las palabras "y finalmente" están fuera de la alineación, en el margen izquierdo, pero las tres ecuaciones están alineadas.

## 2.9. Numeración de ecuaciones y etiquetas.

En LaTeX, las etiquetas para las ecuaciones generalmente se generan automáticamente y son esencialmente una representación impresa de la "ecuación" del contador LaTeX. LaTeX hace esto en tres pasos: establecer el valor del contador de "ecuaciones"; formatear la etiqueta; e imprimirlo en la posición correcta.

Los primeros dos pasos están estrechamente relacionados, porque el valor del contador de "ecuación" aumenta solo cuando la etiqueta correspondiente se imprime automáticamente. Echemos un vistazo a un entorno de visualización que tiene formas destacadas y no destacadas. Sólo la forma sin asterisco cambia el valor del contador de "ecuaciones", ya que etiqueta automáticamente cada ecuación lógica, mientras que la forma con asterisco no lo hace.
Cuando necesite suprimir la configuración de una etiqueta para una determinada ecuación lógica dentro del formato sin asterisco, coloque `\notag` (o `\nonumber`) *antes* de `\\`. También puede reemplazar las etiquetas predeterminadas con unas de su propio diseño usando el comando `\tag` *antes* de `\\`. El argumento de este comando puede ser texto normal arbitrario escrito, entre paréntesis, como etiqueta para esa ecuación.

Tenga en cuenta que el incremento del valor del contador también se suprime cuando se utiliza `\tag`. Esto significa que la configuración de etiqueta predeterminada sólo es visualmente igual a `\tag{\theequation}`; no son equivalentes. La forma destacada, `\tag*`, escribe el texto en su argumento sin paréntesis (y sin ningún otro elemento que de otro modo podría agregarse con una clase de documento en particular).

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\tag, \tag*, \notag, \label y \ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Observe cómo se utilizan los comandos `\label` y `\ref` para proporcionar algún tipo de "numeración relativa" para las ecuaciones.

## 2.10. Secuencias de numeración subordinadas

El paquete *amsmath* también soporta la llamada "subnumeración de ecuaciones". El entorno de `subecuaciones` produce etiquetas de la forma (2a), (2b), (2c), etc. Este esquema de numeración se basa en dos contadores LaTeX normales: `parentequation` y `equation`. Todas las ecuaciones etiquetadas dentro de un entorno de "subecuaciones" utilizan este esquema.

El siguiente ejemplo muestra que la etiqueta se puede redefinir hasta cierto punto, pero tenga en cuenta que la redefinición de `\theequation` debe colocarse en el entorno `subequations`.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}

\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![Secuencias de numeración subordinadas](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> El entorno `subequations` debe aparecer *fuera* de las pantallas a las que afecta. Tampoco debe estar anidado dentro de sí mismo. El contador de ecuaciones "principales" se incrementa con cada uso de este entorno. Un comando `\label` dentro del entorno `subequations` pero fuera de cualquier ecuación individual (lógica) producirá un `\ref` al número padre (por ejemplo, a 2 en lugar de 2i).

## 2.11. Restablecer el contador de ecuaciones

Es una práctica común tener ecuaciones numeradas dentro de secciones o capítulos con etiquetas de la forma (1.1), (1.2), ..., (2.1), (2.2), .... El paquete `amsmath` proporciona una manera fácil de configurar esto con la declaración `\numberwithin`.

Por ejemplo, para obtener etiquetas de ecuación que incluyan el número de sección, con el contador de ecuación restableciéndose automáticamente para cada sección, coloque esta declaración en el preámbulo: `\numberwithin{ecuación}{sección}`.

## Apéndice A. Representación de ecuaciones LaTeX con la API Aspose.TeX

Ahora veremos la forma en que la API Aspose.TeX le permite obtener ecuaciones LaTeX como figuras independientes.

Digamos que necesita obtener una ecuación como una imagen rasterizada para poder usarla en alguna publicación que no sea TeX (una página web, por ejemplo). Usando la API Aspose.TeX, puedes hacerlo de la siguiente manera:


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

Como puede ver, la API también es capaz de convertir una ecuación LaTeX en un archivo SVG. Y ese fue un ejemplo del uso de Aspose.TeX para .NET. A continuación se muestra el código equivalente para la versión Java.


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.aspose.tex.PngMathRendererOptions options = new com.aspose.tex.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.aspose.tex.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

Puede encontrar detalles sobre el uso de opciones de renderizado en el artículo sobre renderizado de fórmulas matemáticas de LaTeX con [Aspose.TeX para .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) o [Aspose.TeX para Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/). Pero uno de ellos es importante para nosotros aquí. Con esta opción, puede especificar el preámbulo del documento LaTeX que necesitaría para obtener el resultado que desea. (A partir de ahora, presentaremos sólo la versión C# del código fuente).


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

También puede usar esta opción cuando necesite disponer una ecuación en un área más estrecha que la que LaTeX `\textwidth` define de forma predeterminada. Tienes dos opciones para lograr este objetivo:


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

En la API Aspose.TeX, el siguiente preámbulo se usa de forma predeterminada, por lo que, a menos que necesite pasar opciones al paquete `amsmath` o cambiar el `\textwidth` predeterminado o algo más, no es necesario especificar el preámbulo en las opciones del renderizador. :

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Apéndice B. Representación de ecuaciones LaTeX con la aplicación web Aspose LaTeX Equation

También existe la [aplicación web LaTeX Equation Editor](https://products.aspose.app/tex/equation-editor) que le permite editar y ver ecuaciones LaTeX. Puede ingresar su ecuación en el campo de texto y hacer clic en el botón *Ver* para ver el resultado. O puede usar el panel de control encima del campo para crear la ecuación seleccionando una categoría de subexpresión, luego una subexpresión y luego editando el argumento, si corresponde. Puede encontrar el preámbulo y otras opciones debajo del campo *Fórmula*.