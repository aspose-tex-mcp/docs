---
translation: true
template: /templates/_template-java.md
title: Reparación de archivos LaTeX | Aspose.TeX para Java
linktitle: Reparación de archivos LaTeX
weight: 30
url: /java/latex-repair/
description: En este artículo se describe la función de reparación de archivos LaTeX dentro de Aspose.TeX para Java con la funcionalidad de ejemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Cómo comprobar y reparar un archivo LaTeX

Si no está seguro de si un archivo de texto es un archivo LaTeX y desea componerlo, puede utilizar la función de verificación y reparación de LaTeX que ofrece la API Aspose.TeX para Java. En el siguiente ejemplo, comprobaremos y repararemos un archivo de muestra, `invalid-latex.tex`, del proyecto de ejemplo Aspose.TeX para Java.

Para empezar, es importante señalar que el archivo de muestra parece emplear la sintaxis TeX pero carece de la estructura requerida por LaTeX. Como sabrás, un archivo LaTeX debe incluir un preámbulo que comience con el comando `\documentclass`, así como un cuerpo encerrado dentro del entorno del documento, específicamente entre `\begin{document}` y `\end{document}`.

Veamos ahora el ejemplo de código Java.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

De manera similar a un trabajo TeX normal, comenzamos creando un objeto que contiene las opciones para el proceso que estamos a punto de ejecutar. La mayoría de estas opciones son las mismas que las de un trabajo TeX normal. De hecho, al llamar al método [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), especificamos el espacio desde el cual se deben leer los archivos de entrada. Sin embargo, en este ejemplo, no lo usamos aquí porque proporcionamos la ruta completa al archivo de entrada principal en el sistema de archivos y no se deben incluir archivos personalizados en el archivo de entrada principal. A continuación, llamamos al método [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) para especificar el espacio donde se deben escribir los archivos de salida. Si se llama, el método [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) hace que las opciones apunten al espacio donde puede almacenar paquetes LaTeX que no están integrados en la biblioteca Aspose.TeX. Finalmente, el método [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) se analizará más adelante.

Una vez asignadas las opciones podemos proceder a ejecutar el proceso.

Entonces, ¿cómo es el proceso de revisión y reparación? Comienza con la API buscando una aparición `\documentclass` en el archivo de entrada. Si no se encuentra, la API supone que `\documentclass{article}` debe insertarse al inicio del archivo. Esta información se registra en el archivo del informe de reparación (.log).

A continuación, el proceso comienza a escanear el archivo de entrada ajustado desde el principio. El motor TeX equipado con el formato LaTeX puede, en algún momento, generar un error que indique que `\begin{document}` aún no se ha encontrado cuando ya debería haberse encontrado. De esta manera, la posición en la que se debe insertar `\begin{document}` queda definida y reflejada en el informe.

Mientras analiza más el archivo, el motor puede encontrar comandos o entornos no definidos. En tales casos, la API puede hacer suposiciones sobre [paquetes incorporados requeridos](/tex/{{lang.url-fragment}}net/embedded-packages/) (aquellos que definen los comandos y entornos que no se definen hasta que se incluyan estos paquetes) para algunos de los comandos y entornos más comunes. Sin embargo, es posible hacer tales suposiciones externamente mediante una clase que implemente la interfaz [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). Una vez que haya desarrollado dicha clase, se debe pasar una instancia de ella al proceso llamando al método `setGuessPackageCallback()`.

Aquí hay un ejemplo básico que simplemente asigna el comando `\head` al paquete `fancyhdr`:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

En cuanto al archivo de muestra, el motor encuentra primero el comando `\chapter`, que no está definido en la clase de documento `article` pero sí en la clase de documento `book`. La API ajusta la clase de documento para que la versión final del archivo reparado comience con `\documentclass{book}`. Luego, el motor encuentra el comando `\lhead` antes mencionado y determina que `\usepackage{fancyhdr}` debe insertarse en el preámbulo. Los comandos `\href` e `\includegraphics` que aparecen más adelante en el archivo hacen que el reparador inserte `\usepackage{hyperref}` y `\usepackage{graphics}` en el preámbulo, respectivamente. Estas decisiones se toman en función de las asignaciones internas de la API. Como antes, todas estas reparaciones se registran en el archivo del informe.

Finalmente, el motor finaliza de forma anormal porque falta la conclusión adecuada de un documento LaTeX. Como resultado, el reparador agrega `\end{document}` al final del archivo e incluye esta información en el informe.

Después de crear la versión reparada del archivo original, el Reparador ejecuta un trabajo TeX para la verificación final. En nuestro ejemplo, esta ejecución no detecta ningún error crítico, por lo que la versión corregida se puede componer más o menos como se esperaba.

Aquí está el informe completo:

```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**También puede consultar nuestra aplicación web gratuita [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer), que se basa en la función implementada dentro de [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/) e implica una versión más avanzada. implementación de la interfaz `IGuessPackageCallback`.**