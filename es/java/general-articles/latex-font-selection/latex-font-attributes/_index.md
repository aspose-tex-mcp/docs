---
translation: true
template: /templates/_template-java.md
linktitle: 2. Características de la fuente
title: Características de la fuente
weight: 20
url: /java/latex-font-attributes/
keywords: látex, fuentes de látex, codificaciones de fuentes de látex, nfss
description: Este artículo cubre las clasificaciones de fuentes LaTeX con respecto a diversas características de fuentes. También menciona el concepto de codificaciones de fuentes LaTeX.
lastmod: "2024-10-30"
---

{{<section overview>}}

Las fuentes se pueden dividir en clases individuales superpuestas en función de diversas características. A menudo resulta útil conocer estas características cuando necesitamos decidir qué familia de fuentes utilizar en un contexto específico. Consulte también el artículo de documentación de [Aspose.Font](https://products.aspose.com/font/) sobre [diferentes tipos de fuentes](/font/net/what-is-font/font-types/).

## 2.1. Fuentes proporcionales y monoespaciadas

Las fuentes pueden ser proporcionales o monoespaciadas. En una fuente proporcional, los glifos tienen diferentes anchos según su forma.  Al mismo tiempo, en una fuente monoespaciada, todos los glifos tienen el mismo ancho. Los espacios adicionales alrededor de los glifos de las fuentes monoespaciadas hacen que sea más difícil reconocer los límites de las palabras y, por lo tanto, hacen que el texto escrito en dichas fuentes sea menos legible. Por el contrario, las fuentes proporcionales (o *tipográficas*) suelen permitir colocar más palabras en una página y son más legibles que las fuentes monoespaciadas. Vea la figura a continuación:

![Fuentes proporcionales y monoespaciadas](/tex/images/java/tutorial/latex-font-selection-2-1.png)
 
Aunque las fuentes monoespaciadas parecen menos legibles, aún tienen su utilidad. Un ejemplo son las tablas o listados de programas donde es importante la alineación adecuada del contenido. Siempre encontrará programas de computadora mostrados en fuente monoespaciada en cualquier computadora desde el libro. Esto distingue fácilmente los programas del texto circundante.

Incluso puede elegir una fuente monoespaciada como fuente base para un documento completo porque dicha fuente parece hecha a mano cuando se usa con párrafos no justificados, lo que le da un sabor a máquina de escribir.

## 2.2. Fuentes serif y sans serif

En algunas fuentes, los glifos tienen *serifas*, mientras que en otras no. Este hecho nos lleva a otra clasificación útil. Las serifas son pequeños trazos horizontales en los extremos de los glifos. Originalmente, se producían con cincel cuando los capiteles romanos se grababan en piedra. Es por eso que las fuentes serif a menudo se denominan fuentes *romanas*.

![Fuentes serif y sans serif](/tex/images/java/tutorial/latex-font-selection-2-2.png)
 
Durante mucho tiempo se pensó que las fuentes serif eran más legibles porque daban al ojo más pistas para la identificación. Pero investigaciones dedicadas han demostrado que la velocidad de lectura no se ve sustancialmente afectada por la ausencia de serifas.

## 2.3. Familias de fuentes y sus atributos

Aparte de las clasificaciones burdas que comentamos anteriormente, las fuentes se agrupan en familias de fuentes. Los miembros de una familia tipográfica comparten principios de diseño comunes y se distinguen por variaciones en tamaño, peso, ancho y forma.

### Formas de fuente

Casi todas las familias de fuentes tienen una forma llamada forma *vertical*. La fuente que estás leyendo ahora tiene forma vertical. Esta forma de fuente se utiliza normalmente para escribir texto normal.

Otra forma importante incluida en la mayoría de las familias es la forma *cursiva*, que parece

![Texto en cursiva](/tex/images/java/tutorial/latex-font-selection-2-3.png)
 
Los glifos en cursiva están inclinados hacia la derecha y las letras se dibujan de manera diferente a sus contrapartes verticales, como se muestra en la siguiente figura:

![Comparación de formas verticales, cursivas y cursivas](/tex/images/java/tutorial/latex-font-selection-2-4.png)
 
La primera línea muestra letras de la familia Computer Modern Serif en forma vertical y la tercera línea muestra las mismas letras en cursiva. Para hacer más evidente la diferencia en el dibujo, la segunda línea muestra las letras en cursiva sin la inclinación habitual. En otras palabras, son letras en cursiva en posición vertical.

Las familias de fuentes san serif a menudo carecen de una forma de cursiva adecuada; en cambio, tienen una forma *inclinada* en la que los caracteres verticales regulares se inclinan hacia la derecha. Estas fuentes también suelen denominarse *oblicuas* o *inclinadas*.
Otra forma de fuente común es la forma de *versalitas*, en la que las letras minúsculas se representan como mayúsculas con una altura reducida. Si la forma de versalitas no está disponible para una fuente específica, los tipógrafos a veces usan mayúsculas verticales de tamaños más pequeños, pero esto no produce la misma calidad que una fuente de versalitas bien diseñada. Las versales verdaderas tienen diferentes anchos y pesos que las letras mayúsculas de la misma fuente que se han reducido a la altura de las versales diseñadas. En la figura siguiente se puede ver que los trazos de las mayúsculas falsas son demasiado finos.

![Comparación de versalitas verdaderas y falsas](/tex/images/java/tutorial/latex-font-selection-2-5.png) 

### Peso y ancho

Las fuentes de una determinada forma dentro de una familia pueden diferir en *peso*. Esta característica está relacionada con el grosor de los trazos utilizados para dibujar las formas individuales. Algunos fabricantes de fuentes llaman *libro* a los pesos de fuente destinados a ser utilizados en texto normal, mientras que otros los llaman *medio*. Para los trazos finos, el nombre *claro* es común, mientras que los trazos más gruesos generalmente se llaman *negrita*. En familias de fuentes más grandes, a veces encontramos un rango que comienza con *ultra light*, pasando por *extra light*, *light*, *semi light*, etc., y termina con *ultra negrita* en el otro extremo. Pero a menudo en algunas familias sólo se dispone de unas pocas pesas. La familia Computer Modern Roman, por ejemplo, sólo tiene pesos medios y negritas.

El *ancho* de la fuente es otro atributo importante. Se refiere a la cantidad de expansión o contracción con respecto al ancho normal o medio de la familia. Computer Modern Roman tiene fuentes en negrita en *ancho medio* y *ancho extendido*. Las fuentes condensadas se utilizan a menudo en títulos y encabezados, donde las fuentes de ancho medio, cuando se usan en tamaños grandes, consumirían demasiado espacio.

### Tamaños de fuente

La unidad de medida para los tamaños de fuente es un punto de impresión (pt). Hay 72,27 puntos en una pulgada. El tamaño de fuente no hace referencia a ninguna característica en particular, sino que es un valor elegido por el diseñador de fuentes para guiar al usuario. Por ejemplo, en una fuente de 10 puntos, las letras del alfabeto suelen tener menos de 10 puntos de altura y sólo los caracteres como los paréntesis tienen aproximadamente esta altura.

La apariencia de una fuente depende de muchos factores, como la altura de las letras minúsculas (la *altura x*), el ancho del trazo y la profundidad de las letras descendentes (la parte de las letras debajo de la línea base, como en el letra 'q'). Es por eso que es posible que dos fuentes del mismo tamaño no combinen bien entre sí.

En el mundo LaTeX, las fuentes suelen estar disponibles en tamaños que son potencias de 1,2, lo que significa que siguen una progresión geométrica. Esta disposición facilita la producción de una copia maestra ampliada que luego puede reducirse fotográficamente, aumentando así efectivamente la resolución de salida final. Hoy en día, las fuentes suelen estar vectorizadas y, por tanto, se pueden escalar a voluntad. Como consecuencia, muchas familias de fuentes comerciales se ofrecen en un solo tamaño de diseño.

El uso de fuentes escaladas en lugar de fuentes diseñadas para un tamaño específico suele dar resultados menos satisfactorios. Esto se debe al hecho de que las fuentes no se escalan de forma lineal según el ojo humano. Puedes ver la diferencia en la siguiente figura:

![Fuentes reales de 10 puntos y magnificadas de 5 puntos](/tex/images/java/tutorial/latex-font-selection-2-6.png)
 
Los glifos en fuentes hechas a mano de tamaños más grandes suelen ser más estrechos que las fuentes ampliadas de un tamaño más pequeño de la misma familia. Siempre que sea posible, se deben utilizar fuentes diseñadas para el tamaño deseado, aunque es aceptable escalar las fuentes dentro de un rango de tamaño pequeño si es necesario.

## 2.4. Codificaciones de fuentes

Como mencionamos en la introducción, TeX se refiere a los glifos de una fuente direccionándolos mediante códigos. Esta asignación se denomina *codificación de fuentes*. En LaTeX, se supone que dos fuentes que tienen la misma codificación son intercambiables en el sentido de que, dada la misma entrada, producen los "mismos" glifos en la página impresa.
Al clasificar las fuentes por sus codificaciones, es posible modificar otras características, como la familia o la serie de fuentes, y aun así garantizar que el resultado tipográfico siga siendo comprensible.

Originalmente, las distribuciones TeX incluían fuentes que tenían solo 128 glifos por fuente. Por lo tanto, esas fuentes no incluyen caracteres acentuados como glifos individuales. Todos estos glifos tuvieron que construirse utilizando la primitiva `\accent` de TeX o mediante métodos similares. Como resultado, LaTeX no puede dividir automáticamente cualquier palabra que contenga signos diacríticos, y el kerning (corrección del espacio entre ciertas letras en la fuente) no se puede aplicar automáticamente. La codificación de estas fuentes se llama "OT1". Aunque sigue siendo la codificación predeterminada para LaTeX, no es recomendable utilizar "OT1" para idiomas distintos del inglés.

La comunidad de usuarios de TeX definió una codificación de 256 caracteres llamada "T1" que permite a TeX componer correctamente en más de 30 idiomas según el alfabeto latino. Por lo tanto, se recomienda encarecidamente el uso de la codificación `T1` ya que, hoy en día, casi todas las familias de fuentes que se pueden utilizar con LaTeX están disponibles en esta codificación. De hecho, algunos *sólo* están disponibles en la codificación `T1`. Al especificar `\usepackage[T1]{fontenc}` después del comando `\documentclass`, `\documentclass` hace que `\T1` sea la codificación predeterminada dentro de un documento.