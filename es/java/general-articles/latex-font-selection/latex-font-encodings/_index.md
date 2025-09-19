---
translation: true
template: /templates/_template-java.md
linktitle: Entrada y salida
title: 1. Codificaciones de entrada y salida.
weight: 10
url: /java/latex-font-encodings/
keywords: LaTeX, fuentes de LaTeX, codificaciones de fuentes de LaTeX, nfss
description: Este artículo explica brevemente los conceptos de codificaciones de entrada y salida en LaTeX. También menciona el nuevo esquema de selección de fuentes.
lastmod: "2024-10-30"
---

{{<section overview>}}

Si pulsamos una tecla de un teclado se generará algún código numérico que representa un determinado carácter. Una codificación de entrada asigna un carácter a su código correspondiente. Por ejemplo, en un teclado alemán, los caracteres acentuados (como el carácter 'diéresis') pueden asignarse a diferentes códigos en diferentes sistemas operativos.

Un documento almacenado en un archivo de computadora contiene solo códigos de caracteres, pero la información sobre la codificación de entrada no se incluye explícitamente. Por lo tanto, si transfiere un archivo a un entorno diferente, como por ejemplo de los Estados Unidos al Reino Unido, es posible que los signos de dólar en su documento se interpreten repentinamente como símbolos de libra cuando vea su archivo con algún programa que haga la suposición errónea sobre la codificación de entrada.

El paquete `inputenc`, desarrollado por el equipo del proyecto LaTeX, tenía como objetivo ayudar con los problemas de codificación de entrada. Permite a los usuarios especificar explícitamente la codificación de entrada utilizada para documentos o partes de documentos. Este mecanismo hace que sea seguro transferir documentos de una instalación de LaTeX a otra logrando resultados impresos idénticos.

El paquete `inputenc` interpreta códigos de caracteres en el archivo y los asigna a una *representación interna de LaTeX*, que cubre de forma única todos los caracteres representables en LaTeX. Durante el procesamiento posterior, como la escritura en algún archivo auxiliar, LaTeX utiliza esta representación interna, evitando así cualquier mala interpretación.

Sin embargo, tarde o temprano, LaTeX tiene que asociar estas representaciones de caracteres internos con *glifos* (formas de caracteres en ciertas fuentes), por lo que se requiere otra asignación. Hay como máximo 256 glifos en cualquier fuente TeX. Estos glifos no se denominan por su nombre, sino por números de 8 bits que representan las posiciones de los glifos en la fuente. Esto significa que tenemos que mapear desde un gran espacio de nombres único a varios espacios pequeños, y estas posiciones de glifos pueden variar ampliamente, lo cual no es sorprendente.

Entonces, aunque preservamos el significado del signo de dólar desde el archivo externo hasta el interno de LaTeX, aún podríamos encontrar formas incorrectas en el papel si seleccionamos una fuente para imprimir que tenga un glifo inesperado en la posición que asumimos que estaba reservada para un dólar. firmar. Una de las tareas de **NFSS** (el **Nuevo esquema de selección de fuentes** de LaTeX) es asegurarse de que cualquier representación interna de caracteres de LaTeX se represente correctamente o, si eso es imposible por algún motivo, que el usuario reciba una mensaje de error adecuado.

Si una fuente contiene caracteres acentuados como glifos individuales, en lugar de solo caracteres base más acentos (a partir de los cuales TeX construye caracteres acentuados internamente), entonces es preferible usar estos glifos ya que generalmente tienen una mejor apariencia. Otra razón (técnica) para usar estos glifos compuestos es que la primitiva `\accent` suprimirá la separación de palabras.

Para adaptarse a diferentes casos, un comando como `\'e` (la representación interna de LaTeX para el carácter 'e-acute') a veces tiene que iniciar acciones complicadas que involucran la primitiva `\accent` y, a veces, simplemente informa al creador de párrafos que necesita el glifo de una determinada *ranura* (posición) en la fuente actual.

Todo esto se logra a través del concepto de *codificaciones de salida*, que son asignaciones de las representaciones internas de caracteres de LaTeX a posiciones de glifos apropiadas o a acciones de construcción de glifos, dependiendo de los glifos reales disponibles en la fuente utilizada para la composición tipográfica.

Los siguientes artículos analizan la versión 2 de NFSS, que pasó a formar parte del estándar LaTeX en 1994.