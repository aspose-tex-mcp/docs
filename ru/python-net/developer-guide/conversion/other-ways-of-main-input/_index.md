---
translation: true
template: /templates/_template-python-net.md
title: Иные методы предоставления входного файла TeX | Python через .NET
linktitle: Другие способы предоставления основного входного файла TeX
weight: 14
url: /python-net/other-ways-of-main-input/
description: Aspose.TeX API для Python включает в себя конструктор, который принимает поток в качестве первого аргумента, обеспечивая функциональность преобразования.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Передача основного входного файла в движок TeX с использованием потока.

До сих пор мы только узнали, как предоставить [основной входной файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) движку TeX как имя файла, в полной или сокращенной форме, с расширением или без него. Однако в классе [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) доступен [еще один конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions), который принимает поток в качестве первого аргумента. Это полезно, если по какой-то причине основной входной файл не находится в виде файла в файловой системе диска. Вот пример того, как это можно реализовать:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Обратите внимание, что все выходные файлы будут называться «texput». Это связано с тем, что у движка нет доступа ни к какому другому имени. `texput` — это имя задания по умолчанию. Более подробную информацию о названиях заданий вы можете найти в параграфах [Вывод TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) и [Как задать имя задания](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Ввод основного входного файла TeX через терминал

В классе [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) доступен [еще один конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions), который вообще не позволяет нам указывать входные данные. Вам может быть интересно, что будет обрабатывать такое задание TeX. В этом случае нам нужно будет использовать входной терминал. Движок TeX предложит нам ввести имя файла из терминала.

Вот код:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Как только он запустится, движок приостановится и будет ждать, пока мы введем имя файла (с путем или без него, с расширением или без него):


![Окно терминала](/tex/images/python-net/.png)

А вот как это будет выглядеть на выходном терминале (консоли):

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