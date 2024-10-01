---
translation: true
template: /templates/_template-java.md
title: Cómo configurar nuevas fuentes
linktitle: 6. Cómo configurar nuevas fuentes
weight: 60
url: /java/latex-fonts-setup/
keywords: látex, fuentes de látex, sustitución de fuentes de látex, configuración de fuentes de látex
description: Este artículo cubre la configuración de nuevas fuentes para usar con LaTeX y también incluye un ejemplo de definición de fuente.
lastmod: "2024-10-30"
---

{{<section overview>}}

Para configurar nuevas fuentes para usar con LaTeX, básicamente necesita llenar las tablas de selección de fuentes internas con la información necesaria para luego asociar una solicitud de fuente en un documento con el archivo externo `.tfm` que contiene información de caracteres utilizados por LaTeX. Por lo tanto, las tablas se encargan de asociar el archivo externo `cmdunh10.tfm` con la siguiente solicitud:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

Para agregar nuevas fuentes, debes invertir el proceso. Para cada nueva fuente externa, debes responder cinco preguntas:

1. ¿Cuál es la codificación de la fuente, es decir, qué caracteres se encuentran en qué posiciones?
2. ¿Cuál es su apellido?
3. ¿Cuál es su serie (peso y ancho)?
4. ¿Cuál es su forma?
5. ¿Cuál es su tamaño?



Las respuestas a estas preguntas proporcionarán la información necesaria para clasificar sus fuentes externas según las convenciones de LaTeX. En las próximas secciones, discutiremos cómo ingresar nuevas fuentes en las tablas NFSS para que puedan usarse en el texto principal. Normalmente necesitará esta información si desea utilizar nuevas fuentes, como por ejemplo crear un archivo de paquete corto para acceder a una nueva familia de fuentes. En secciones posteriores, discutiremos conceptos más complicados que son importantes si desea utilizar, por ejemplo, fuentes especiales para matemáticas en lugar de las estándar.

## 6.1. La convención de nomenclatura para fuentes externas

Un esquema de denominación de fuentes estándar de facto en el mundo TeX clasifica todos los nombres de archivos de fuentes utilizando ocho caracteres alfanuméricos, donde las mayúsculas y minúsculas no son significativas. Este límite de ocho caracteres garantiza que se puedan utilizar los mismos nombres de archivo en todas las plataformas informáticas. El principio del esquema se describe en la siguiente tabla, donde las partes entre paréntesis pueden omitirse si corresponden a un defecto. Por ejemplo, un tamaño de diseño se proporciona sólo si la fuente no tiene una escala lineal.

![La convención de nomenclatura para fuentes externas](/tex/images/java/tutorial/latex-font-selection-6-1.png)

A continuación se muestra la clasificación de las 35 fuentes PostScript "básicas" según la interfaz de fuentes de LaTeX. Para cada fuente, se proporciona el nombre completo de Adobe y el nombre corto del archivo correspondiente (en la clasificación que se analiza actualmente). Para "OT1", "T1" o "TS1", sería necesario agregar "7t", "8t" u "8c", respectivamente, para obtener el nombre completo del archivo. Por ejemplo, `putr8t` para Utopia Regular en codificación `T1`.  Esto será útil en futuras discusiones.

![Clasificación de fuentes PostScript](/tex/images/java/tutorial/latex-font-selection-6-2.png)

La convención de nomenclatura cubre nombres TeX internos para fuentes (es decir, aquellos utilizados en declaraciones `\DeclareFontShape` como se describe en la siguiente sección), nombres para fuentes virtuales y sus componentes (por ejemplo, recodificaciones particulares de fuentes físicas) y los nombres de fuentes físicas. fuentes. En el caso de las fuentes PostScript, los nombres de las fuentes físicas suelen ser diferentes de los utilizados internamente por TeX.
En el último caso, los nombres de las fuentes internas deben asignarse a las fuentes externas correspondientes cuando se ve o imprime el resultado de una ejecución de LaTeX. Por ejemplo, el controlador PostScript `dvips` utiliza archivos de mapeo (extensión predeterminada `.map`) que contienen líneas como

```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

diciéndole que la fuente `putr8r` se puede obtener de la fuente externa `putr8a.pfb` recodificandola mediante un vector de codificación especial (`8r.enc`). Sin embargo, no encontrará ninguna referencia a ese `putr8r` en el archivo `t1put.fd`, que contiene las declaraciones `\DeclareFontShape` para la familia Utopia en la codificación `T1`. La razón es que `putr8t` es una fuente virtual (creada con la ayuda de la utilidad `fontinst`) que hace referencia a `putr8r`. Este último enlace sólo se puede encontrar en las fuentes de las fuentes virtuales.

## 6.2. Cómo declarar nuevas familias de fuentes y grupos de formas de fuentes
Cada combinación de familia/codificación debe introducirse en LaTeX con la ayuda del comando `\DeclareFontFamily`, que toma tres argumentos. Los dos primeros son el esquema de codificación y el apellido. El tercero suele estar vacío, pero puede contener opciones especiales para cargar fuentes y se explica con más detalle en este artículo. Entonces, si desea declarar una nueva familia, digamos, Computer Modern Dunhill con la antigua codificación TeX, escribiría

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

Normalmente, hay muchas fuentes individuales en una familia de fuentes. Para reducir el número de declaraciones, hay que combinar fuentes que difieran sólo en tamaño y declararlas como un grupo en lugar de anunciar a cada miembro de la familia individualmente.

Dicho grupo se ingresa en las tablas internas de LaTeX con el comando `\DeclareFontShape`, que toma seis argumentos. Los primeros cuatro argumentos son el esquema de codificación, el apellido, el nombre de la serie y el nombre de la forma bajo la cual desea acceder a estas fuentes. El quinto argumento es una lista de tamaños y nombres de fuentes externas, presentados en un formato especial que se analiza a continuación. El sexto argumento suele estar vacío y su uso se explica con más detalle en este artículo.

Por ejemplo, una entrada de la tabla NFSS para Computer Modern Dunhill medium vertical en el antiguo esquema de codificación TeX podría ingresarse como

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

suponiendo que solo esté disponible una fuente externa para el tamaño de 10 puntos. Si también tiene esta fuente disponible en 12 puntos (escala desde 10 puntos), la declaración sería

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

Si el archivo externo está disponible en todos los tamaños posibles, la declaración resulta muy sencilla. Este es el caso de las fuentes PostScript Tipo 1 (contorno), o cuando el programa controlador puede generar fuentes bajo demanda llamando a METAFONT.

Por ejemplo, Times Roman negrita vertical en el esquema de codificación LaTeX `T1` podría introducirse de la siguiente manera

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

Este ejemplo declara un rango de tamaños con dos extremos abiertos. Como resultado, se utiliza el mismo archivo externo `ptmb8t.tfm` para todos los tamaños y se escala al tamaño deseado. Si tiene más de un archivo `.tfm` para una fuente, por ejemplo, `emtt10` para tamaños de texto y `emtt12` para tamaños de visualización (máquina de escribir moderna europea), la declaración podría ser

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

En este caso, el archivo `emtt10.tfm` se usaría para tamaños menores a 12 puntos, y `emtt12.tfm` para todos los tamaños mayores o iguales a 12 puntos.

Los ejemplos anteriores demuestran que el quinto argumento del comando `\DeclareFontShape` consta de especificaciones de tamaño rodeadas por corchetes angulares entremezcladas con información de carga para los tamaños individuales (por ejemplo, nombres de fuentes). La parte dentro de los corchetes angulares se llama *información de tamaño*, y la parte que sigue al corchete angular de cierre se llama *información de fuente*.  La información de la fuente se estructura además en una *función de tamaño* (a menudo vacía) y sus argumentos. Dentro de los argumentos de `\DeclareFontShape`, los espacios en blanco se ignoran para que las entradas sean más legibles. En circunstancias inusuales, cuando es necesario ingresar un espacio real, puede usar el comando `\space`.

### Tamaños simples y rangos de tamaño.

La información de tallas se puede dividir en *tallas simples* y *rangos de tallas*. Un tamaño simple viene dado por un único número (decimal), como `<10>` o `<17.28>`, y puede tener cualquier valor positivo. Sin embargo, probablemente no encontrará valores inferiores a 4 o superiores a 120 porque el número representa un tamaño de fuente medido en puntos. Un rango de tamaño está dado por dos tamaños simples separados por un guión, para indicar un rango de tamaños de fuente que comparten la misma información de fuente. El límite inferior está incluido en el rango, mientras que el límite superior está excluido. Por ejemplo, `<5-10>` significa tamaños mayores o iguales a 5 puntos y menores a 10 puntos. Es posible omitir el número en cualquier tamaño del guión en un rango de tamaños: `<->` representa todos los tamaños posibles, `<-10>` representa todos los tamaños inferiores a 10 puntos y `<12->` representa todos los tamaños mayores o iguales a 12 puntos.
Varios tamaños simples suelen tener la misma información de fuente. En ese caso, una forma abreviada conveniente es omitir toda la información excepto la última:

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

Esto declara que la fuente Pandora medium Roman está disponible en varios tamaños, todos ellos producidos escalando a partir del mismo tamaño de diseño.

### Funciones de tamaño

Como se mencionó anteriormente, la información de la fuente se estructura en una función de tamaño y su argumento. Si aparece un `*` en la cadena de información de fuente, todo lo que está a la izquierda forma el nombre de la función y todo lo que está a la derecha es el argumento. Si no hay un asterisco, como en todos los ejemplos hasta ahora, la cadena completa se considera como argumento y el nombre de la función está *vacío*.

Las funciones de tamaño producen la especificación necesaria para que LaTeX encuentre la fuente externa y la cargue en el tamaño deseado. Este proceso se basa en el tamaño solicitado por el usuario y la información en el comando `\DeclareFontShape`. Las funciones de tamaño también son responsables de notificar al usuario sobre eventos especiales. Por ejemplo, algunas funciones sólo se diferencian en si emiten advertencias. Esta capacidad permite al mantenedor del sistema configurar LaTeX de la manera más adecuada para el sitio en particular.

El nombre de una función de tamaño consta de cero o más letras. Algunas de las funciones de tamaño pueden tomar dos argumentos: uno opcional y otro obligatorio. Un parámetro opcional debe estar entre corchetes. Por ejemplo, la siguiente especificación seleccionaría, para todos los tamaños posibles, la función de tamaño `s` con el argumento opcional `0.9` y el argumento obligatorio `cmfbi10`:

```tex
<-> s * [0.9] cmfib8
```

Las especificaciones de tamaño en `\DeclareFontShape` se inspeccionan en el orden en que se proporcionan. Cuando una información de tamaño coincide con el tamaño solicitado, se ejecuta la función de tamaño correspondiente. Si este proceso produce una fuente válida, no se inspeccionan más entradas. De lo contrario, la búsqueda continúa con la siguiente entrada. Las funciones de tamaño estándar se enumeran a continuación.

**La función "vacía"** La función vacía carga la información de fuente exactamente en el tamaño solicitado si es un tamaño simple. Si hay un rango de tamaño y el tamaño solicitado por el usuario está dentro de ese rango, carga la fuente exactamente en el tamaño del usuario.
Por ejemplo, si el usuario solicitó "14.4", entonces la especificación

```tex
<-> panr10
```

cargaría el archivo `panr10.tfm` en 14.4pt. Todos los valores en el archivo `.tfm` están escalados en 1,44 porque esta fuente fue diseñada para 10 puntos.

Es posible que en ocasiones desees cargar una fuente con un tamaño ligeramente diferente al solicitado por el usuario. Este ajuste puede ser necesario cuando las fuentes de una familia parecen demasiado grandes en comparación con las fuentes de otras familias utilizadas en el mismo documento. Para este propósito, la función de tamaño vacío permite un argumento opcional para especificar un factor de escala que se multiplica por el tamaño solicitado para obtener el tamaño real que se cargará.

De este modo, 

```tex
<-> [0.95] phvr8t
```

siempre cargaría el archivo `phvr8t.tfm` (Helvetica en la codificación `T1`) al 95% del tamaño solicitado. Si se utiliza el argumento opcional, la función de tamaño vacío emitirá una advertencia para notificar al usuario que la fuente no se está cargando en el tamaño deseado.

**La función "s"** La función `s` hace lo mismo que la función vacía, excepto que no se generará ningún mensaje en el terminal. Los mensajes se seguirán escribiendo en el archivo de transcripción, para que puedas saber qué fuentes se utilizaron si algo sale mal.

**La función "gen"** Los nombres de fuentes externas a menudo se crean agregando el tamaño de fuente a una cadena que representa el tipo de letra. Por ejemplo, "cmtt8", "cmtt9" y "cmtt10" son los nombres externos de las fuentes Computer Modern Typewriter en 8, 9 y 10 puntos, respectivamente. Con los nombres de fuentes organizados según dicho esquema, puede utilizar la función "gen" para acortar la entrada. Esta función combina la información de la fuente y el tamaño solicitado para generar los nombres de las fuentes externas. Así, si escribes

```tex
<8> <9> <10> gen * cmtt
```

esto sería una abreviatura de
```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

que guarda ocho caracteres en las tablas internas de NFSS. Esta función combina ambas partes literalmente, por lo que no debes usarla con tamaños decimales como `14.4`. También debe asegurarse de que los dígitos en el nombre de la fuente externa realmente representen el tamaño del diseño (por ejemplo, "cmr17" es en realidad Computer Modern Roman en 17,28 puntos).

En todos los demás aspectos, la función `gen` se comporta como la función vacía. Es decir, el argumento opcional, si se especifica, representa un factor de escala y, si se utiliza, genera un mensaje de información.

**La función "sgen"** La función `sgen` es la versión silenciosa de la función gen. Escribe cualquier mensaje sólo en el archivo de transcripción.

**La función "genb"** Esta función de tamaño es similar a gen, pero está destinada a fuentes en las que el tamaño está codificado en el nombre de la fuente en centipuntos, como las fuentes EC. En consecuencia, una línea como 

```tex
<9> <10> <10.95> <12> genb * ecrm
```

actúa como una taquigrafía

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

Un argumento opcional, si está presente, tendrá el mismo efecto que tendría con la función vacía.

**La función "sgenb"** La función `sgenb` es la versión silenciosa de la función `genb`. Escribe cualquier mensaje sólo en el archivo de transcripción.

**La función "sub"** La función "sub" se utiliza para sustituir un grupo de formas de fuente diferente si no existe una fuente externa para el grupo de formas de fuente actual. En este caso, el argumento no es un nombre de fuente externo sino una combinación diferente de familia, serie y forma separada por barras. Por ejemplo, Computer Modern Sans no tiene forma de cursiva, solo una forma inclinada. Por tanto, es razonable declarar la forma inclinada como sustituto de la cursiva:

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

Sin esta declaración, el mecanismo de sustitución automática de LaTeX sustituiría la forma predeterminada, Computer Modern Sans vertical.

Hay otros buenos usos para la función `sub`. Mira el siguiente código:

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

Esta declaración establece que para tamaños inferiores a 8 puntos, LaTeX debe buscar en la declaración de forma de fuente `OT1/cmss/m/n`. Estas sustituciones pueden encadenarse. Por ejemplo, no existe una fuente Computer Modern Sans de menos de 8 puntos, por lo que el grupo de formas de fuente sustituidas probablemente contendrá otra entrada de sustitución. Sin embargo, usar este método tiene la ventaja de que cuando obtiene una fuente adicional, solo tiene que cambiar una declaración de grupo de forma de fuente; otras declaraciones que usan esta fuente se beneficiarán automáticamente.

**La función "ssub"** La función `ssub` tiene la misma funcionalidad que la función secundaria pero no produce advertencias en pantalla (la primera 's' significa "silenciosa").

**La función "subf"** La función `subf` carga fuentes de la misma manera que la función vacía, pero genera una advertencia de que esta operación se realizó como una sustitución porque la forma de fuente solicitada no está disponible. Esta función se puede utilizar para sustituir algunas fuentes externas sin la necesidad de declarar un grupo de formas de fuente separado para ellas, como en el caso de la función "sub". Por ejemplo, 

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

advertiría al usuario que la combinación solicitada no está disponible y, por lo tanto, que en su lugar se cargó la fuente `ptmb7t`. Dado que esto es menos informativo que usar la función "sub", se debe preferir esta última.

**La función "ssubf"** La versión silenciosa de `subf`, esta función escribe sus mensajes solo en el archivo de transcripción.

**La función "fija"** Esta función ignora el tamaño solicitado y en su lugar carga la fuente externa proporcionada como argumento. Si está presente, el argumento opcional indica el tamaño (en puntos) en el que se cargará la fuente. Por lo tanto, esta función le permite especificar rangos de tamaño para los cuales se cargará una fuente en un tamaño fijo.

**La función "sfixed"** La versión silenciosa de `fixed`. Esta función se utiliza, por ejemplo, para cargar la fuente que contiene los símbolos matemáticos grandes, que a menudo está disponible solo en un tamaño.

### Opciones de carga de fuentes
Como se mencionó anteriormente, cada familia de fuentes debe declararse usando el comando `\DeclareFontFamily`. El argumento de este comando, así como el sexto argumento de `\DeclareFontShape`, se pueden utilizar para especificar operaciones especiales que se llevan a cabo cuando se carga una fuente. De esta manera, puede cambiar los parámetros asociados con una fuente en su conjunto.

Además de la información sobre cada carácter, TeX mantiene para cada fuente externa un conjunto de dimensiones globales y otros valores asociados con la fuente. Por ejemplo, cada fuente tiene su propio "carácter de guión", el carácter que se inserta cuando TeX divide una palabra con guiones. Otro ejemplo es el ancho normal y la capacidad de ampliación del espacio en blanco entre palabras; Se mantiene un valor para cada fuente y se cambia cada vez que TeX cambia a una nueva fuente. Al cambiar estos valores en el momento en que se carga la fuente, se pueden lograr efectos especiales.

Normalmente, los cambios se aplican a toda una familia; por ejemplo, es posible que desee prohibir la separación de palabras en todas las palabras escritas en la familia de máquinas de escribir. En este caso, se debe utilizar el tercer argumento de `\DeclareFontFamily`. Si los cambios deben aplicarse solo a un grupo de formas de fuente específico, debe usar el sexto argumento de `\DeclareFontShape`. En otras palabras, cuando se carga una fuente, NFSS primero aplica el argumento de `\DeclareFontFamily` y luego el sexto argumento de `\DeclareFontShape`, de modo que pueda anular las opciones de carga especificadas para toda la familia si es necesario.

Con `\hyphenchar\font=<número>`, TeX especifica el carácter utilizado para la separación de palabras. El `<número>` representa la posición de este carácter dentro del esquema de codificación. El valor predeterminado es el valor de `\defaultyphenchar`, que es `45`, que representa la posición del carácter '-' en la mayoría de los esquemas de codificación. Si establece este número en "-1", se suprime la separación de palabras. Por lo tanto, al declarar

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

puede suprimir la separación de palabras para todas las fuentes de la familia `cmtt` con el esquema de codificación `OT1`. Las fuentes con codificación `T1` tienen un guión alternativo en la posición 127, por lo que puedes configurar, por ejemplo,

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

lo que hace que el carácter de guión sea diferente del guión de palabra compuesta ingresado en palabras como "so-llamado". TeX no separa palabras que ya contienen guiones explícitos (excepto justo después del guión), lo que puede ser un problema en idiomas en los que la longitud promedio de las palabras es mucho mayor que en inglés. Con la configuración anterior, este problema se puede resolver.

Cada fuente TeX tiene un conjunto de dimensiones asociado, que se cambian mediante asignaciones del formulario `\fontdimen<número>\font=<dimen>`, donde `<número>` es el número de referencia para la dimensión y `<dimen> ` es el valor a asignar. Los valores predeterminados se recuperan del archivo `.tfm` cuando se carga la fuente. Cada fuente tiene al menos siete de estas dimensiones:* `\fontdimen1` Especifica la inclinación por punto de los caracteres. Si el valor es cero, la fuente está vertical.

* `\fontdimen2` Especifica el ancho normal de un espacio utilizado entre palabras (espacio entre palabras).

* `\fontdimen3` Especifica la capacidad de extensión adicional del espacio entre palabras, que es la cantidad adicional de espacio en blanco que TeX puede agregar al espacio entre palabras para producir líneas justificadas en un párrafo. En caso de emergencia, TeX puede agregar más espacio que este valor permitido; en ese caso se informará una *casilla insuficientemente llena*.

* `\fontdimen4` Especifica la capacidad de reducción permitida del espacio entre palabras, que es la cantidad de espacio que TeX puede restar del espacio entre palabras normal (\fontdimen2) para producir líneas justificadas en un párrafo. TeX nunca reducirá el espacio entre palabras a menos de este mínimo.

* `\fontdimen5` Especifica la *altura x*. Define la dimensión orientada a fuente `1ex`.

* `\fontdimen6` Especificó el ancho *quad*. Define la dimensión orientada a fuente `1em`.

* `\fontdimen7` Especifica la cantidad prevista como espacio adicional que se agregará después de ciertos caracteres de puntuación al final de la oración cuando `\nonfrenchspacing` esté vigente. Siempre se ignora o más bien se reemplaza por el valor `\xspaceskip` cuando ese valor es distinto de cero.



Cuando cambia el espacio entre palabras asociado con una fuente, no puede usar un valor absoluto porque dicho valor debe poder usarse para todos los tamaños dentro de un grupo de formas. Por lo tanto, debes definir el valor utilizando algún otro parámetro que dependa de la fuente. Se podría decir, por ejemplo,

```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

Esta declaración reduce el espacio normal entre palabras al 70% de su valor original. De manera similar, se podrían cambiar la capacidad de estiramiento y la capacidad de contracción.

Algunas fuentes en fórmulas necesitan más de siete dimensiones de fuente. Es decir, las fuentes de símbolos llamadas "símbolos" y "símbolos grandes". TeX no podrá componer una fórmula si estas fuentes tienen menos de 22 y 13 parámetros `\fontdimen`, respectivamente. Los valores de estos parámetros se utilizan para posicionar los caracteres en una fórmula matemática.

Hay una optimización desafortunada en el sistema TeX: TeX carga cada archivo `.tfm` solo una vez para un tamaño determinado. Por lo tanto, es imposible definir un grupo de formas de fuente (con el comando `\DeclareFontShape`) para cargar alguna fuente externa - digamos, `cmtt10` - y usar otro comando `\DeclareFontShape` para cargar la misma fuente externa, esta vez cambiando algunos de los parámetros `\fontdimen` o algún otro parámetro asociado con la fuente. Un intento de hacerlo cambia los valores de ambos grupos de formas de fuente.

Por ejemplo, supongamos que intenta definir una forma de fuente con un espacio reducido reduciendo el espacio entre palabras:

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

Esta declaración no funcionará. El espaciado entre palabras para la forma mediana cambiará cuando la forma estrecha se cargue con los valores especificados allí, y esto no es lo que se espera. La mejor manera de manejar esta situación es definir una fuente virtual que contenga los mismos caracteres que la fuente original pero que difiera en la configuración de las dimensiones de la fuente. Otra posible solución es cargar la fuente en un tamaño ligeramente diferente, como en la siguiente declaración:

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

Este método las convierte en fuentes diferentes para TeX con parámetros `\fontdimen` separados. Alternativamente, en este caso particular, puede controlar el espacio entre palabras configurando `\spaceskip`, anulando así los valores de fuente.

## 6.3. Cómo modificar familias de fuentes y grupos de formas de fuentes

Si se necesita una declaración de forma de fuente no estándar para un documento en particular, esta declaración privada debe colocarse en un paquete o en el preámbulo del documento. Sobrescribirá cualquier declaración existente para la combinación de forma de fuente. Sin embargo, es importante que el uso de `\DeclareFontFamily` prevenga una carga posterior del archivo `.fd` correspondiente (que se analiza más adelante en este artículo). Además, esta nueva declaración no tiene ningún efecto sobre las fuentes que ya están cargadas.

## 6.4. Cómo declarar un nuevo esquema de codificación de fuentes

Los cambios de fuente que implican alteraciones en el esquema de codificación requieren ciertas precauciones. En la codificación `T1`, por ejemplo, la mayoría de las letras acentuadas tienen sus propios glifos, mientras que en la codificación de texto tradicional TeX (`OT1`), las letras acentuadas deben generarse a partir de letras y acentos usando la primitiva `\accent`. Si es necesario combinar los dos enfoques, tal vez porque una fuente está disponible solo en una de las codificaciones, la definición de un comando como `\"` debe comportarse de manera diferente dependiendo de la codificación de fuente actual.

Es por eso que cada codificación de fuente debe introducirse formalmente en LaTeX con un comando `\DeclareFontEcnoding`, que requiere tres argumentos. El primer argumento es el nombre de la codificación, que luego se usará para acceder a la codificación con el comando `\fontencoding`. La lista de [esquemas de codificación estándar](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding) y sus nombres internos se proporciona en la tabla de la sección 5.1.

El segundo argumento contiene cualquier código (como definiciones) que se ejecutará cada vez que LaTeX cambie de una codificación a otra usando el comando `\fontencoding`. El último argumento contiene código que se utilizará cada vez que se acceda a la fuente como un alfabeto matemático. Por tanto, estos tres argumentos se pueden utilizar para redefinir comandos que dependen de las posiciones de los caracteres en la codificación.

El proyecto LaTeX3e se reserva el uso de codificaciones que comiencen con las siguientes letras:

* `T`: codificaciones de texto estándar con 256 caracteres.
* `TS`: símbolos diseñados para ampliar la codificación `T` correspondiente.
* `X`: codificaciones de texto que no cumplen con los requisitos estrictos para las codificaciones `T`.
* `M`: codificaciones matemáticas estándar con 256 caracteres.
* `S`: otras codificaciones de símbolos.
* `A` - otras aplicaciones especiales.
* `OT`: codificaciones de texto estándar con 128 caracteres.
* `OM`: codificaciones matemáticas estándar con 128 caracteres.



La letra "O" enfatiza que las codificaciones de 128 caracteres son antiguas y *obsoletas*. Idealmente, estas codificaciones serán reemplazadas por estándares definidos por el grupo de usuarios de TeX, de modo que en el futuro será necesario un cambio de codificación sólo si uno cambia de un idioma a otro.

Al declarar sus propias codificaciones privadas, debe elegir nombres que comiencen con `L` para "local" o `E` para "experimental". Las codificaciones que comienzan con "U" son para codificaciones "Desconocidas" o "Sin clasificar", es decir, para fuentes que no se ajustan a un patrón de codificación común. La convención de nomenclatura introducida garantiza que los archivos que utilizan codificaciones oficiales sean portátiles.

El comando `\DeclareFontEncoding` almacena el nombre de la codificación recién declarada en el comando `\LastDeclaredEncoding`. A veces esto resulta útil cuando se declara otra información de codificación relacionada y se utiliza, por ejemplo, en los archivos de declaración de codificación para los idiomas cirílicos.

Además, como mencionamos en la discusión sobre la sustitución de fuentes en el artículo anterior, es posible que los valores predeterminados de familia, serie y forma deban ser diferentes para diferentes codificaciones. Para tal caso, NFSS proporciona el comando `\DeclareFontSubstitution`, que toma la codificación como primer argumento. Los siguientes tres argumentos son los valores predeterminados (asociados con esta codificación) para la familia, la serie y la forma que se utilizarán en el proceso de sustitución automática. Es importante que estos tres argumentos formen una forma de fuente válida. En otras palabras, existe una declaración `\DeclareFontShape` para ellos. De lo contrario, se emitirá un mensaje de error cuando NFSS verifique sus tablas internas en `\begin{document}`.

## 6.5. Organización de archivos internos
Las familias de fuentes se pueden declarar cuando se genera un archivo de formato, se declaran en el preámbulo del documento o se cargan bajo demanda cuando un comando de cambio de fuente en el documento solicita una combinación que aún no se ha utilizado. La primera forma conduce a consumir memoria interna en cada ejecución de LaTeX, incluso si no se utiliza la fuente. Las dos últimas opciones toman un poco más de tiempo durante el formateo del documento porque las definiciones de fuentes deben leerse en tiempo de ejecución. Sin embargo, estas últimas soluciones son preferibles para la mayoría de los grupos de formas porque le permiten componer una amplia variedad de documentos con un único formato LaTeX.

Cuando se genera el archivo de formato, LaTeX lee un archivo llamado `fonttext.ltx`, que contiene el conjunto estándar de definiciones de familias de fuentes y algunas otras declaraciones relacionadas con las fuentes de texto.

Todas las demás definiciones de familias de fuentes deben declararse en archivos externos cargados bajo demanda: ya sean archivos de paquete o archivos de definición de fuentes (`.fd`).  Si las definiciones de familias de fuentes se colocan en un archivo de paquete, debe cargar explícitamente este paquete después del comando `\documentclass`. Sin embargo, existe una tercera posibilidad: cada vez que NFSS recibe una solicitud para una familia de fuentes `foo` en un esquema de codificación `BAR`, y no sabe nada acerca de esta combinación, intentará cargar un archivo llamado `barfoo.fd`. Si este archivo existe, se supone que contiene definiciones de grupos de formas de fuentes para la familia `foo` en el esquema de codificación `BAR`, es decir, declaraciones de la forma

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

Así es como es posible declarar una gran cantidad de familias de fuentes para LaTeX sin llenar la memoria valiosa con información que probablemente casi nunca se utilice.

Cada archivo `.fd` debe contener todas las definiciones de fuentes para una familia de fuentes en un esquema de codificación. En el archivo, debe haber una o más declaraciones `\DeclareFontShape` y exactamente una declaración `\DeclareFontFamily`. No deberían aparecer otras definiciones en el archivo, excepto quizás una declaración `\ProvidesFile` o algunas declaraciones `\typeout` que informen al usuario sobre la carga de la fuente. En lugar del comando `\typeout`, puede usar el comando TeX simple `\wlog`, que escribe su argumento solo en el archivo de transcripción. Todos los archivos `.fd` que se utilizan en producción deben generar información detallada en el archivo de transcripción porque mirar esta transcripción ayudará a detectar errores al proporcionar información sobre los archivos y sus versiones utilizadas en un trabajo en particular. Si se utilizan los comandos `\typeout` o `\wlog`, es importante recordar que los espacios y las líneas vacías en un archivo `.fd` se ignoran. Por lo tanto, es necesario utilizar el comando `\space` en el argumento de `\typeout` o `\wlog` para obtener un espacio en blanco en la pantalla y el archivo de transcripción.

No se pueden introducir nuevos esquemas de codificación mediante el mecanismo `.fd`. NFSS rechazará cualquier solicitud para cambiar a un esquema de codificación que no haya sido declarado explícitamente en el formato LaTeX (es decir, `fonttext.ltx`), en un archivo de paquete o en el preámbulo del documento.

## 6.6. Cómo declarar nuevas fuentes para usar en matemáticas

### Cómo especificar tamaños de fuente

Para cada tamaño de texto, NFSS mantiene [tres tamaños que se utilizan para componer fórmulas matemáticas](/tex/{{lang.url-fragment}}java/latex-math-fractions-binomial-styles/): el tamaño en el que escribir la mayoría de los símbolos (seleccionados por `\textstyle` o `\displaystyle`); el tamaño de los subíndices y superíndices de primer orden (`\scriptstyle`); y el tamaño de los subíndices y superíndices de orden superior (`\scriptscriptstyle`). Si cambia a un nuevo tamaño de texto para el cual aún no se conocen los tamaños matemáticos correspondientes, NFSS intenta calcularlos como fracciones del tamaño del texto. Si no desea que NFSS calcule estos tamaños, puede especificar los valores correctos usted mismo mediante `\DeclareMathSizes`. Esta declaración toma cuatro argumentos: el tamaño del texto exterior y los tres tamaños matemáticos para este tamaño de texto. Por ejemplo, la siguiente declaración define los tamaños matemáticos para el tamaño de 14 puntos (encabezado) como 14 puntos, 10 puntos y 7 puntos, respectivamente:

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

Otra declaración a continuación (para títulos de un nivel superior) informa a NFSS que no se necesitan tamaños matemáticos para un tamaño de texto de 36 puntos. Esto puede ayudar a evitar la carga innecesaria de muchas fuentes.

```tex
\DeclareMathSizes{36}{}{}{}
```

### Cómo agregar nuevos símbolos

Ya hemos discutido cómo usar [comandos del alfabeto matemático](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) para producir letras con formas especiales en una fórmula. Aquí, mostraremos cómo agregar fuentes que contienen símbolos especiales, llamadas *fuentes de símbolos*, y cómo hacer que dichos símbolos sean accesibles en las fórmulas.

Agregar nuevas fuentes de símbolos es similar a la declaración de un nuevo identificador de alfabeto matemático: `\DeclareSymbolFont` define los valores predeterminados para todas las versiones matemáticas, `\SetSymbolFont` anula los valores predeterminados para una versión particular.

Se puede acceder a las fuentes de símbolos matemáticos mediante un nombre simbólico. Por ejemplo, si desea instalar la fuente AMS `msbm10` (consulte el cuadro de glifos a continuación), primero debe hacer que NFSS conozca el tipo de letra utilizando las declaraciones descritas en las secciones anteriores.

![gráfico de glifos msbm10](/tex/images/java/tutorial/latex-font-selection-6-3.png)

Estas instrucciones se verían así

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

y generalmente se colocan en un archivo `.fd`. Luego, debes declarar esa fuente de símbolo para todas las versiones matemáticas mediante el siguiente comando:

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

Hace que el grupo de formas de fuente `U/msb/m/n` esté disponible como fuente de símbolo bajo el nombre `AMSb`. Si hubiera una serie en negrita en esta familia de fuentes (de hecho, no la hay), posteriormente podría cambiar la configuración de la versión matemática en negrita diciendo

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

Después de ocuparse de las declaraciones de fuentes, puede usar esta fuente de símbolo en modo matemático. Pero, ¿cómo decirle a NFSS que, por ejemplo, el comando `\lessdot` en modo matemático debería producir el símbolo correspondiente en la salida? Para hacerlo, necesita introducir sus propios nombres de símbolos en NFSS usando `\DeclareMathSymbol`:

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

El primer argumento es el nombre del comando que elija. El segundo argumento es uno de los comandos que se muestran en la siguiente tabla y determina la naturaleza del símbolo, que, a su vez, determina la cantidad de espacio que LaTeX coloca alrededor del símbolo cuando aparece en una fórmula.

![Tipos de objetos matemáticos](/tex/images/java/tutorial/latex-font-selection-6-4.png)

Por cierto, a excepción de `\mathalpha`, estos comandos se pueden usar en fórmulas matemáticas como funciones con un argumento, en cuyo caso espacian su argumento (posiblemente complejo) como si fuera del tipo correspondiente.

El tercer argumento identifica la fuente del símbolo de la que se debe obtener el símbolo, es decir, el nombre simbólico definido por el comando `\DeclareSymbolFont`. El cuarto argumento proporciona la posición del símbolo en la codificación de fuente, ya sea como valor decimal, octal o hexadecimal. Puede encontrar fácilmente las posiciones de todos los glifos en esta fuente en el cuadro de glifos de arriba. Por ejemplo, `\lessdot` se puede declarar como

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

En lugar de un nombre de comando, puede utilizar un solo carácter como primer argumento. Por ejemplo, el paquete `eulervm` tiene varias declaraciones del formato

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

para especificar de dónde obtener los dígitos.

El comando `\DeclareMathSymbol` especifica una posición en alguna fuente de símbolo. Por lo tanto, es importante que todas las fuentes externas asociadas con esta fuente de símbolo mediante los comandos `\DeclareSymbolFont` y `\SetSymbolFont` tengan el mismo carácter en esa posición. La forma más sencilla de garantizar esto es utilizar solo fuentes con la misma codificación (a menos que sea la codificación "U", o desconocida, ya que no es necesario que dos fuentes en esta codificación contengan los mismos caracteres).

En el gráfico de glifos de arriba, también puede encontrar letras en "negrita de pizarra" (ABC... comenzando desde la posición `'101`). Si desea utilizar estas letras como alfabeto matemático, puede definirlas usando `\DeclareMathAlphabet`. Sin embargo, si esta fuente de símbolo ya está cargada, es mejor utilizar un acceso directo para acceder a símbolos individuales:

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

Es decir, usted proporciona el nombre de su identificador del alfabeto matemático y el nombre simbólico de la fuente del símbolo previamente declarada.
Una razón importante para no cargar fuentes dos veces innecesariamente es que existe un límite superior de 16 fuentes matemáticas que pueden estar activas en un momento dado en TeX. Al calcular este límite, cada fuente de símbolo cuenta; Los alfabetos matemáticos cuentan sólo si realmente se utilizan en el documento y cuentan localmente en cada versión matemática. Por lo tanto, si se declaran ocho fuentes de símbolos, puede utilizar como máximo ocho (posiblemente diferentes) identificadores de alfabeto matemático dentro de cada versión.

Como breve resumen: para introducir nuevas fuentes de símbolos, debe emitir una pequeña cantidad de declaraciones `\DeclareSymbolFont` y `\SetSymbolFont` y una cantidad potencialmente grande de declaraciones `\DeclareMathSymbol`. Por lo tanto, es mejor agregar dichas fuentes en un archivo de paquete.

### Cómo introducir nuevas versiones matemáticas

Ya hemos [mencionado](/tex/{{lang.url-fragment}}java/latex-math-fonts/#83-math-formula-versions) que la configuración estándar declara automáticamente dos versiones matemáticas: normal y negrita. Para introducir versiones adicionales, puede utilizar la declaración `\DeclareMathVersion`, que toma un argumento: el nombre de la nueva versión matemática. Todas las fuentes de símbolos y todos los alfabetos matemáticos declarados previamente están disponibles automáticamente en esta versión matemática; se les asignan las fuentes predeterminadas, es decir, las fuentes que ha especificado con `\DeclareMathAlphabet` o `\DeclareSymbolFont`.

Luego puede cambiar la configuración de su nueva versión emitiendo los comandos `\SetMathAlphabet` y `\SetSymbolFont` apropiados para la versión matemática en negrita, como se mostró anteriormente en esta sección y en el artículo sobre [fuentes en matemáticas](/tex/{{lang.url-fragment}}java/latex-math-fonts/) . Nuevamente, la introducción de una nueva versión matemática normalmente se realiza en un archivo de paquete.


### Cómo cambiar la configuración de la fuente del símbolo

Hemos visto cómo agregar nuevas fuentes de símbolos para acceder a más símbolos. Los mismos comandos se pueden utilizar para modificar una configuración existente. Esta capacidad puede resultar interesante si decide utilizar fuentes especiales en algunas o todas las versiones matemáticas.

A continuación se muestran las configuraciones predeterminadas de LaTeX:

```tex
\DeclareMathVersion{normal} \DeclareMathVersion{bold}
\DeclareSymbolFont{operators} {OT1}{cmr}{m} {n}
\DeclareSymbolFont{letters} {OML}{cmm}{m}{it}
\DeclareSymbolFont{symbols} {OMS}{cmsy}{m}{n}
\DeclareSymbolFont{largesymbols} {OMX}{cmex}{m}{n}

% Special bold fonts only for these:
\SetSymbolFont {operators}{bold}{OT1}{cmr}{bx}{n}
\SetSymbolFont {letters} {bold}{OML}{cmm}{b}{it}
```

En la configuración estándar, los dígitos y el texto producidos por operadores como `\log` y `\max` se toman de la fuente de símbolo llamada `operadores`. Para cambiar esto para que estos elementos se combinen bien con la fuente del texto principal (por ejemplo, Computer Modern Sans en lugar de Computer Modern Roman), puede ejecutar los siguientes comandos:

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

Las fuentes de símbolos con nombres "símbolos" y "símbolos grandes" desempeñan un papel único en TeX. Es por eso que requieren una cantidad especial de parámetros `\fontdimen` asociados con ellos. Por lo tanto, sólo se pueden utilizar fuentes especialmente preparadas como estas dos fuentes de símbolos. En principio, se pueden agregar dichos parámetros a cualquier fuente en el momento de la carga utilizando el tercer parámetro de `\DeclareFontFamily` o el sexto parámetro de `\DeclareFontShape`.

## 6.7. Cómo definir su propio archivo `.fd` (ejemplo)

Si desea configurar fuentes (PostScript) y crear el archivo `.fd` requerido, debe seguir el procedimiento descrito anteriormente en este artículo. Si se utiliza `fontinst` para generar los archivos de métricas de fuentes requeridos, los archivos `.fd` correspondientes también se generan automáticamente. Sin embargo, es fácil escribir a mano un archivo `.fd` para una sola familia de fuentes, siempre que sepa qué codificación de fuente se utiliza. Como ejemplo, estudiemos el archivo de declaración `t1bch.fd` para *Bitstream Charter* en la codificación `T1`:

```tex
\ProvidesFile{t1bch.fd}[2001/06/04 font definitions for T1/bch.]
% Primary declarations
\DeclareFontFamily{T1}{bch}{}
\DeclareFontShape{T1}{bch}{m}{n}{<-> bchr8t}{}
\DeclareFontShape{T1}{bch}{m}{sc}{<-> bchrc8t}{}
\DeclareFontShape{T1}{bch}{m}{sl}{<-> bchro8t}{}
\DeclareFontShape{T1}{bch}{m}{it}{<-> bchri8t}{}
\DeclareFontShape{T1}{bch}{b}{n}{<-> bchb8t}{}
\DeclareFontShape{T1}{bch}{b}{sc}{<-> bchbc8t}{}
\DeclareFontShape{T1}{bch}{b}{sl}{<-> bchbo8t}{}
\DeclareFontShape{T1}{bch}{b}{it}{<-> bchbi8t}{}
% Substitutions
\DeclareFontShape{T1}{bch}{bx}{n}{<->ssub * bch/b/n}{}
\DeclareFontShape{T1}{bch}{bx}{sc}{<->ssub * bch/b/sc}{}
\DeclareFontShape{T1}{bch}{bx}{sl}{<->ssub * bch/b/sl}{}
\DeclareFontShape{T1}{bch}{bx}{it}{<->ssub * bch/b/it}{}
\endinput
```

La primera línea es una *línea de identificación*. Luego sigue la declaración de la familia de fuentes y la codificación (`bch` y `T1`) usando `\DeclareFontFamily`. El argumento de este comando debe corresponder al nombre del archivo `.fd`, excepto que la codificación en el nombre del archivo está en minúsculas. A continuación, cada combinación de serie y forma se asigna al nombre de un archivo ".tfm". Estas fuentes se escalarán al tamaño deseado (observe `<->`). La segunda parte del archivo establece algunas sustituciones para combinaciones para las que no hay ninguna fuente disponible (es decir, reemplazando la serie extendida en negrita por la serie en negrita).
Suponiendo que tiene las fuentes *Charter* adicionales (Black y BlackItalic), es posible que desee agregar las definiciones correspondientes al archivo `.fd`. Por supuesto, primero deberá proporcionar las fuentes virtuales adecuadas para emular el juego de caracteres "T1". Afortunadamente, muchas fuentes se pueden descargar de Internet.

Otra posible razón para crear sus propios archivos `.fd` podría surgir de la necesidad de combinar fuentes de diferentes familias e introducirlas en LaTeX como una única familia de fuentes nueva. Por ejemplo, existe la familia de fuentes *Aldus* diseñada como complemento del tipo de letra *Palatino* (que fue diseñado originalmente como un tipo de letra de visualización). Como Aldus no tiene una serie audaz, Palatino es una elección natural para usar como sustituto audaz. En el siguiente ejemplo, combinamos Aldus en su serie mediana con Palatino negrita, llamando a la familia de fuentes compuestas "zasj". Sólo se presenta un fragmento de un archivo `.fd` completo, que es suficiente para ilustrar la idea.

```tex
\ProvidesFile{t1zasj.fd}
   [2003/10/12 font definitions for T1 Aldus/Palatino mix.]
\DeclareFontFamily{T1}{zasj}{}
% Medium series
\DeclareFontShape{T1}{zasj}{m}{n} {<->pasr9d}{}
\DeclareFontShape{T1}{zasj}{m}{sc}{<->pasrc9d}{}
\DeclareFontShape{T1}{zasj}{m}{it}{<->pasri9d}{}
\DeclareFontShape{T1}{zasj}{m}{sl}{<->ssub * pasj/m/it}{}
% Bold series
\DeclareFontShape{T1}{zasj}{b}{n}{<-> pplb8t}{}
\DeclareFontShape{T1}{zasj}{b}{sc}{<->pplbc8t}{}
\DeclareFontShape{T1}{zasj}{b}{sl}{<->pplbo8t}{}
\DeclareFontShape{T1}{zasj}{b}{it}{<->pplbi8t}{}
```

Para acceder a esta "pseudofamilia", tenemos que seleccionar `zasj` en la codificación `T1`. También debemos asegurarnos de que `\textbf` cambie a negrita, no a negrita extendida, ya que nuestro archivo `.fd` no proporciona ninguna sustitución. Todo esto puede ser proporcionado automáticamente por un pequeño paquete como este:

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

Entonces, al cargar el paquete `fontmix`, obtenemos Aldus y Palatino Bold para los titulares. Es posible que una combinación de fuentes de este tipo no mejore el texto con frecuencia, por lo que este ejemplo no sugiere crear combinaciones aleatorias.

## 6.8. El orden de las declaraciones.

El NFSS requiere que usted proporcione todas las declaraciones en un orden específico, para poder verificar si ha especificado toda la información necesaria. Si declara objetos en el orden incorrecto, se quejará. Aquí están las dependencias que debes honrar:

* `\DeclareFontFamily` comprueba que el esquema de codificación se haya declarado previamente con `\DeclareFontEncoding`.
* `\DeclareFontShape` comprueba que la familia de fuentes fue declarada como disponible en la codificación solicitada (`\DeclareFontFamily`).
* `\DeclareSymbolFont` asegura que el esquema de codificación sea válido.
* `\SetSymbolFont` garantiza adicionalmente que se declaró la versión matemática solicitada (`\DeclareMathVersion`) y que se declaró la fuente del símbolo solicitada (`\DeclareSymbolFont`).
* `\DeclareSymbolFontAlphabet` comprueba que se puede utilizar el nombre del comando para el identificador del alfabeto y que se declaró la fuente del símbolo.
* `\DeclareMathAlphabet` comprueba que se pueda utilizar el nombre del comando elegido y que se haya declarado el esquema de codificación.
* `\SetMathAlphabet` verifica que el identificador del alfabeto haya sido declarado previamente con `\DeclareMathAlphabet` o `\DeclareSymbolFontAlphabet` y que se conozcan la versión matemática y el esquema de codificación.
* `\DeclareMathSymbol` se asegura de que el nombre del comando pueda usarse (es decir, no esté definido o haya sido declarado previamente como un símbolo matemático) y que la fuente del símbolo haya sido declarada previamente.
* Cuando se alcanza el comando `\begin{document}`, NFSS realiza algunas comprobaciones adicionales. Por ejemplo, verifica que los valores predeterminados de sustitución para cada esquema de codificación apunten a declaraciones de grupos de formas de fuentes conocidas.

