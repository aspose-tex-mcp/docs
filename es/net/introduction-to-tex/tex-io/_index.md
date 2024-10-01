---
translation: true
template: /templates/_template-net.md
title: E/S TeX | Solución API Aspose.TeX para .NET
linktitle: E/S de texto
weight: 12
url: /net/tex-io/
description: Fundamentos de trabajar con TeX como formato de salida o entrada dentro de la API Aspose.TeX. El trabajo TeX se ejecuta en un archivo especificado explícitamente.
lastmod: "2024-10-30"
---

{{<section overview>}}

## archivo tex

Técnicamente, cualquier archivo puede ser un archivo TeX. Ni siquiera necesita tener la extensión *.tex*. Un motor TeX lee la entrada byte a byte tratando de reconocer los comandos que conoce (es decir, aquellos que están en su estado interno). Simplemente informa errores sobre comandos no reconocidos y/o solicita correcciones en el terminal (si se está ejecutando en [modo interactivo](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)). Pero si espera ver algo así como un documento bien compuesto, la entrada debe seguir la sintaxis TeX e, idealmente, contener sólo comandos conocidos por el motor.

## entrada de texto

Un trabajo TeX se ejecuta en un archivo TeX especificado explícitamente. Entonces, incluimos este archivo en la entrada de un determinado trabajo TeX. Además, TeX tiene cuatro primitivas relacionadas con la entrada auxiliar:

* `\input<nombre de archivo>` requiere un nombre de archivo y comienza a procesar ese archivo tan pronto como el procesamiento del archivo que lo contiene llega al comando `\input`. Una vez que se llega al final del archivo auxiliar, el procesamiento regresa al archivo que contiene el comando `\input`.
* `\openin<número de 4 bits>=<nombre de archivo>` también requiere un nombre de archivo, pero simplemente abre un archivo y lo asigna a un número del 0 al 15.
* `\read<número> a <secuencia de control>` requiere el número al que está asignado un archivo y lee una línea a la vez para que `<secuencia de control>` corresponda a la lista de tokens leídos.
* `\closein<número de 4 bits>` cierra el archivo asignado al número.

Los archivos cuyos nombres se pasan a los comandos `\input` y `\openin` también se incluyen en la entrada TeX, y los llamaremos archivos *entrada auxiliar* o *dependencias*, mientras que el archivo especificado para el trabajo lo llamaremos el archivo *entrada principal*.

Los cuatro comandos pueden ocurrir en el archivo de entrada principal o en un archivo de entrada auxiliar. Pero tenga cuidado con las dependencias circulares.

Cuando se ejecuta en un [modo interactivo](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), en caso de cualquier error, el motor TeX solicita una corrección en el terminal. En este punto, es posible que desees reemplazar el comando erróneo por uno nuevo. Y esta será otra y última forma de proporcionar entrada a TeX que llamaremos *entrada de terminal*.

## salida de texto

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/tex-io/#tex-input), un trabajo TeX se ejecuta en un archivo especificado explícitamente. Es posible que el archivo no contenga ningún dato para componer. Puede que sólo haya secuencias de control que no produzcan caracteres para escribir. Pero normalmente contendrá dichos datos, de modo que obtendremos un archivo en el formato de destino que debería contener nuestro texto tipográfico (o cualquier otra cosa permitida por el motor y el formato, si se amplían para adaptarse a características adicionales de un determinado formato de destino). . El archivo tendrá el mismo nombre que el archivo especificado como entrada. Llamaremos a este archivo el archivo *salida principal*. Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex), para el TeX original, este será un archivo en formato DVI. Llamaremos al nombre de los archivos de entrada y de salida sin extensión *nombre del trabajo*.

Además, TeX tiene tres primitivas relacionadas con la salida auxiliar:

* `\openout<número de 4 bits>=<nombre de archivo>` requiere un nombre de archivo, abre un archivo y lo asigna a un número del 0 al 15.
* `\write<número>{lista de tokens}` requiere el número al que está asignado un archivo y escribe la `lista de tokens` en el archivo.
* `\closeout<número de 4 bits>` cierra el archivo asignado al número.
 
Los archivos cuyos nombres se pasan a los comandos `\openout` también se incluyen en la salida TeX, y los llamaremos archivos de *salida auxiliar*.

A medida que el motor TeX ejecuta la entrada, puede generar información de depuración en el archivo *log* o *trascript*. Incluiremos este archivo en la salida TeX.
Simultáneamente con la escritura en el archivo de registro, el motor TeX puede enviar información menos detallada al terminal. Y esta es la última forma en que el motor TeX escribe la salida que llamaremos *salida de terminal*.

## Modos de interacción TeX

Un trabajo TeX puede estar ejecutándose en uno de los cuatro modos de interacción en un momento dado. Estos modos se cambian mediante las siguientes primitivas TeX:

* `\modo por lotes`. El motor omite todas las paradas y omite la salida del terminal y, por lo tanto, no requiere el terminal ni para la entrada ni para la salida.
* `\modo sin parar`. El motor omite todas las paradas y, por lo tanto, requiere la terminal sólo para la salida.
* `\modo de desplazamiento`. El motor omite paradas por error y requiere el terminal tanto para entrada como para salida.
* `\modoparadaerror`. El motor se detiene en cada oportunidad de interactuar.

Aspose.TeX nos permite especificar el modo de interacción como una opción de trabajo TeX cuando se crea su objeto. Este modo se establecerá en el estado interno del motor inmediatamente después de cargar el formato TeX (si se supone que se carga algún formato) y cambiará a otro modo tan pronto como el motor encuentre uno de los cuatro comandos. El valor predeterminado de esta opción preservará el modo de interacción definido por el formato TeX. Cuando no se carga ningún formato, el modo de interacción es el mismo que el establecido por el comando `\errorstopmode`.