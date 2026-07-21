---
translation: true
template: /templates/_template-python-net.md
title: Suministrar el archivo de entrada TeX principal | Python 
linktitle: Otras formas de proporcionar el archivo de entrada TeX principal
weight: 14
url: /python-net/other-ways-of-main-input/
description: La solución API Aspose.TeX para Python incluye un constructor que acepta una secuencia como primer argumento, proporcionando funcionalidad de conversión.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Proporcionar el archivo de entrada principal al motor TeX mediante una secuencia

Hasta ahora, sólo hemos aprendido cómo proporcionar el [archivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motor TeX como un nombre de archivo, ya sea en su forma completa o abreviada, con o sin extensión. Sin embargo, hay [otro constructor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible en la clase [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) que acepta una secuencia como primer argumento. Esto es útil si, por alguna razón, el archivo de entrada principal no tiene la forma de un archivo en el sistema de archivos del disco. A continuación se muestra un ejemplo de cómo se puede implementar:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Tenga en cuenta que todos los archivos de salida se denominarán "texput". Esto se debe a que el motor no tiene acceso a ningún otro nombre. `texput` es el nombre del trabajo predeterminado. Puede encontrar información más detallada sobre los nombres de los trabajos [salida TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) y [Cómo configurar el nombre del trabajo](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) párrafos.

## Ingresando el archivo de entrada TeX principal a través del terminal

Hay [un constructor más](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible en la clase [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) que no nos permite especificar la entrada en absoluto. Quizás se pregunte qué procesaría un trabajo TeX de este tipo. En este caso, necesitaríamos utilizar un terminal de entrada. El motor TeX nos solicitará que ingresemos el nombre del archivo desde la terminal.

Aquí está el código:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Tan pronto como se ejecute, el motor se detendrá y esperará a que ingresemos el nombre del archivo (con o sin ruta, y con o sin extensión):


![Ventana de terminal](/tex/images/python-net/.png)

Y así es como aparecería en el terminal de salida (consola):

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```