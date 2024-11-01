---
translation: true
template: /templates/_template-java.md
linktitle: 5. Interfaz de bajo nivel
title: La interfaz de bajo nivel | API para Java
weight: 50
url: /java/latex-fonts-low-level/
keywords: látex, fuentes de látex, sustitución de fuentes de látex, familias de fuentes de látex, series de fuentes de látex, formas de fuentes de látex
description: Este artículo cubre la interfaz de fuentes de bajo nivel LaTeX que se utiliza principalmente en las definiciones de comandos.
lastmod: "2024-10-30"
---

{{<section overview>}}

A diferencia de los comandos de fuentes de alto nivel, que están pensados ​​para su uso en un documento, los comandos de bajo nivel sirven principalmente para definir nuevos comandos en paquetes o en el preámbulo del documento. Para aprovechar al máximo dichos comandos, resulta útil comprender la organización interna de las fuentes en el esquema de selección de fuentes (NFSS) de LaTeX.

Por un lado, el objetivo del esquema de selección de fuentes de LaTeX es permitir una selección racional de fuentes con algoritmos guiados por los principios del marcado genérico. Para ello, sería deseable permitir cambios independientes en tantos atributos de fuente como sea posible. Por otro lado, las familias de fuentes en la vida real normalmente contienen sólo un subconjunto de las innumerables combinaciones de atributos de fuentes imaginables. Por lo tanto, permitir cambios independientes en demasiados atributos da como resultado demasiadas combinaciones para las cuales no hay una fuente externa real disponible y se debe sustituir por una predeterminada.

Internamente, LaTeX realiza un seguimiento de cinco atributos de fuente independientes: la *codificación actual*, la *familia actual*, la *serie actual*, la *forma actual* y el *tamaño actual*. El atributo de codificación se introdujo en la versión 2 de NFSS cuando quedó claro que el soporte para múltiples idiomas no sería posible sin mantener el esquema de codificación de caracteres independientemente de los otros atributos de fuente.

Los valores de estos atributos determinan la fuente actualmente en uso. LaTeX también mantiene un gran conjunto de tablas que se utilizan para asociar combinaciones de atributos con fuentes externas (es decir, archivos `.tfm` que contienen los datos necesarios para que LaTeX haga su trabajo). La selección de fuentes se realiza entonces en dos pasos:

1. Se cambian varios atributos de fuente usando los comandos de bajo nivel `\fontencoding`, `\fontfamily`, `\fontseries`, `\fontshape` y `\fontsize`.

2. La fuente correspondiente a estas nuevas configuraciones de atributos se selecciona llamando al comando `\selectfont`.

El segundo paso consta de varias acciones. Primero, LaTeX verifica si el sistema conoce la fuente correspondiente a la configuración de atributos deseada (es decir, el archivo `.tfm` ya está cargado) y, de ser así, se selecciona esta fuente. De lo contrario, se buscan las tablas internas para encontrar el nombre de fuente externa asociado con estas configuraciones. Si se encuentra dicho nombre de fuente, el archivo `.tfm` correspondiente se lee en la memoria y luego se selecciona la fuente para la composición tipográfica. Si no se encuentra el nombre de la fuente, LaTeX intenta encontrar una fuente alternativa, como se explica más adelante en este artículo.


## 5.1. Configuración de atributos de fuente individuales

Hay un comando para cada atributo de fuente para cambiar su valor actual. Todos estos comandos aceptan más o menos cualquier cadena de caracteres como argumento, pero sólo unos pocos valores tienen sentido. Estos valores no están integrados en NFSS, sino que son convenciones establecidas en las tablas internas. Las siguientes secciones presentan las convenciones de nomenclatura utilizadas en la configuración estándar de LaTeX, pero cualquiera puede cambiar esta configuración agregando nuevas declaraciones de fuentes en las tablas internas. Normalmente, cualquiera que configure nuevas fuentes para usar con LaTeX debería tratar de respetar estas convenciones siempre que sea posible porque sólo una convención de nomenclatura coherente puede garantizar que se seleccionen las fuentes apropiadas en un documento genéricamente marcado.

Si desea seleccionar una fuente específica usando esta interfaz, por ejemplo, Computer Modern Dunhill negrita condensada cursiva 14 puntos, el conocimiento de las convenciones de la interfaz por sí solo no es suficiente, ya que no existe una fuente externa para cada combinación de valores de atributos. Podría intentar especificar algo como lo siguiente:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Este código sería correcto según las convenciones de nomenclatura, como veremos a continuación. Sin embargo, debido al hecho de que esta combinación de atributos no corresponde a una fuente real, LaTeX tendría que sustituirla por una fuente diferente. El mecanismo de sustitución puede elegir una fuente bastante diferente a la deseada, por lo que deberás consultar las tablas de fuentes para comprobar si la combinación deseada está disponible. Aquí hay más detalles sobre el [proceso de sustitución de fuentes](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Elegir la familia de fuentes

La familia de fuentes se selecciona con el comando `\fontfamily`. Como argumento toma una cadena de caracteres que hace referencia a una familia tipográfica declarada en las tablas internas. La cadena de caracteres se definió cuando se configuraron estas tablas y suele ser una secuencia de letras corta, por ejemplo, "cmr" para la familia Computer Modern Roman. Los apellidos no deben tener más de cinco letras porque se combinarán posiblemente con tres letras más para formar un nombre de archivo, que en algunos sistemas puede tener como máximo ocho letras.

### Elegir la serie de fuentes

El comando `\fontseries` cambia el atributo de la serie. La serie combina un peso y un ancho en su argumento, lo que significa que es imposible cambiar el ancho de la fuente actual independientemente de su peso. Esto es aceptable porque es poco probable que sea necesario cambiar el peso o el ancho individualmente. Por el contrario, un cambio de peso suele ir acompañado de un cambio de anchura en las especificaciones del diseñador. Esto no es una gran sorpresa ya que los cambios de peso alteran la apariencia horizontal de las letras y, por lo tanto, requieren ajustes en la expansión (ancho) para producir una apariencia bien equilibrada.

Los nombres tanto del peso como del ancho se abrevian en los nombres de las series, de modo que cada combinación es única. Estas convenciones de nomenclatura se muestran en la siguiente tabla. Se omite cualquier instancia de "m" (que significa peso o ancho medio), excepto cuando tanto el peso como el ancho son medianos, en cuyo caso se utiliza una sola "m". Por ejemplo, negrita expandida sería "bx", mientras que mediana expandida sería "x" y negrita mediana sería "b".

![Convenciones de nomenclatura de series de fuentes](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Elegir la forma de la fuente

El comando `\fontshape` cambia el atributo de forma. Para las formas estándar, se utilizan abreviaturas de una y dos letras. Estas formas se enumeran en la siguiente tabla:

![Convenciones de nomenclatura de formas de fuente](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Elegir el tamaño de fuente

El comando `\fontsize{<size>}{<skip>}` cambia el tamaño de fuente. Se necesitan dos argumentos: el `<tamaño>` al que cambiar y la línea base `<skip>` (la distancia entre las líneas base para este tamaño). Los tamaños de fuente normalmente se miden en puntos, por lo que, por convención, se omite la unidad. Lo mismo ocurre con el segundo argumento. Sin embargo, si el salto de línea base debe ser una longitud de goma, deberá especificar una unidad. Por lo tanto, un cambio de talla válido podría ser solicitado por

```tex
\fontsize{14.4}{17}\selectfont
```

Incluso si dicha solicitud es válida, es posible que no exista una fuente externa correspondiente en este tamaño. En tal caso, LaTeX intentará encontrar un tamaño cercano si sus tablas internas permiten la corrección del tamaño o informará un error en caso contrario.

Si utiliza fuentes existentes en tamaños arbitrarios, puede seleccionar el tamaño que desee, por supuesto:

```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Elegir la codificación

El comando `\fontencoding` se utiliza para cambiar la codificación. El argumento es el nombre interno de la codificación deseada. LaTeX debe conocer este nombre, ya sea como una de las codificaciones predefinidas (cargadas por el kernel) o como declarado con el comando `\DeclareFontEncoding`. Aquí hay más información sobre [declarar codificaciones de fuentes](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). Los nombres de codificación de fuentes estándar se enumeran en la siguiente tabla:

![Nombres de codificación de fuentes estándar](/tex/images/java/tutorial/latex-font-selection-5-3.png)
NFSS se basa en el supuesto de que la mayoría (o mejor, todas) las fuentes del texto están disponibles en la misma codificación siempre que se utilicen para componer en el mismo idioma. En otras palabras, los cambios de codificación deberían ser necesarios sólo si cambia de un idioma a otro. En este caso, normalmente se supone que los paquetes de soporte de idiomas (por ejemplo, del sistema `babel`) se encargan de las codificaciones detrás de escena.

En el siguiente ejemplo, cambiamos la codificación manualmente definiendo un entorno `Cyr` para escribir en cirílico. En este entorno, tanto la codificación de fuente como la codificación de entrada se cambian localmente. Por supuesto, para lograr un soporte lingüístico adecuado, se requeriría trabajo adicional, como cambiar las reglas de separación de palabras. Las codificaciones se declaran en LaTeX cargándolas con el paquete `fontenc`. `T2A` especifica una de las codificaciones cirílicas estándar. `T1` se convierte en la codificación predeterminada desde que se carga por última vez.

![Código fuente de ejemplo de envolventes](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Salida del ejemplo de envolventes](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Desafortunadamente, "T1" no se puede implementar completamente para la mayoría de las fuentes PostScript. Es probable que cinco caracteres en el siguiente ejemplo se muestren como manchas de tinta, lo que indica que faltan glifos en la fuente. Tenga en cuenta que los símbolos 'por mil' y 'por diez mil' en realidad se forman uniendo un signo de porcentaje y uno o dos ceros pequeños adicionales; sólo falta el último glifo.

```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 para fuentes PostScript](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Configurar múltiples atributos de fuente

Al diseñar estilos de página o comandos orientados al diseño, a menudo desea seleccionar una fuente en particular, es decir, necesita especificar valores para todos los atributos. Para ello, LaTeX proporciona el comando `\usefont`, que toma cuatro argumentos: la codificación, la familia, la serie y la forma. El comando actualiza esos atributos y luego llama a `\selectfont`. Si también desea especificar el tamaño y el salto de línea base, coloque un comando `\fontsize` antes de `\usefont`. Por ejemplo,

```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

produciría el mismo resultado que los siguientes comandos:

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

LaTeX también proporciona la declaración `\DeclareFixedFont`, que puede usarse para definir nuevos comandos que cambian a una fuente completamente fija. Estos comandos son muy rápidos porque no tienen que buscar ninguna tabla interna. Por lo tanto, son muy útiles en definiciones de comandos que tienen que alternar entre fuentes. Por ejemplo, si queremos declarar un comando para componer cierto texto en tamaño script, podemos hacerlo de la siguiente manera:

```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

Puedes ver que `\DeclareFixedFont` tiene seis argumentos. El nombre del comando a definir va seguido de los cinco atributos de fuente en las clasificaciones NFSS. En lugar de pasar valores fijos (excepto el tamaño), se utilizan los ganchos integrados que describen la fuente del documento principal. Por lo tanto, en el ejemplo anterior `\ScriptSizeFont` todavía depende del diseño general del documento. Sin embargo, una vez que se ejecuta la definición, su significado se congela, por lo que los cambios posteriores a los valores predeterminados no cambiarán la fuente `\ScriptSizeFont`.

## 5.3. Sustitución automática de fuentes.

Cuando no se puede realizar una solicitud de cambio de fuente porque LaTeX no conoce la combinación, intenta recuperarla utilizando una fuente con atributos similares. Esto es lo que sucede en detalle: si la combinación de esquema de codificación, familia, serie y forma no se declara, LaTeX intenta encontrar una combinación conocida cambiando primero el atributo de forma a un valor predeterminado. Si aún se desconoce la combinación resultante, intenta cambiar la serie a la predeterminada. Como último recurso, cambia la familia a un valor predeterminado. Finalmente, busca la entrada de la tabla interna para encontrar el tamaño solicitado. Por ejemplo, si solicita `\ttfamily\bfseries\itshape`, una fuente de máquina de escribir en negrita y cursiva (que generalmente no existe), obtendrá una fuente de máquina de escribir en serie mediana y forma vertical porque LaTeX primero restablece la forma antes de restablecer la serie. En tal caso, si prefiere una fuente de máquina de escribir con forma de cursiva, debe anunciar sus preferencias a LaTeX usando la función `sub`, que se explica en el artículo [Cómo configurar nuevas fuentes](/tex/{{lang.url-fragment}}java/latex-fonts-setup/).

El proceso de sustitución nunca cambia el esquema de codificación porque cualquier alteración puede producir caracteres incorrectos en la salida. Como recordará, el esquema de codificación define cómo interpretar los caracteres de entrada, mientras que los otros atributos definen cómo debe verse la salida. Por lo tanto, no sería apropiado si, por ejemplo, el signo de libra fuera reemplazado por el signo de dólar en un contrato sólo porque el software intentara ser inteligente.

Por lo tanto, cada esquema de codificación debe tener una familia, serie y forma predeterminadas, y al menos la combinación que consta del esquema de codificación junto con los valores predeterminados correspondientes debe tener una definición dentro de LaTeX.

## 5.4. Cómo utilizar comandos de bajo nivel en el documento

Los comandos de bajo nivel descritos en las secciones anteriores están destinados a usarse en las definiciones de comandos de alto nivel, ya sea en archivos de clase de documento o de paquete, o en el preámbulo del documento.

Si puede utilizar comandos de alto nivel como `\textsf`, debe evitar utilizar comandos de bajo nivel directamente en el documento siempre que sea posible. La razón es que los comandos de bajo nivel son instrucciones muy precisas para cambiar a una fuente particular, mientras que los comandos de alto nivel se pueden personalizar usando paquetes o declaraciones en el preámbulo. Supongamos que ha seleccionado Computer Modern Sans en su documento usando `\fontfamily{cmss}\selectfont`. Si luego decide componer todo el documento con fuentes del paquete PSNFSS (por ejemplo, Times), aplicar un paquete cambiaría sólo aquellas partes del documento que no contienen comandos explícitos `\fontfamily`.