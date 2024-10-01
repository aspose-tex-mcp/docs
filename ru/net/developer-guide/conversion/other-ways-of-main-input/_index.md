---
translation: true
template: /templates/_template-net.md
title: Другие способы предоставления основного входного файла TeX | .СЕТЬ
linktitle: Другие способы предоставления основного входного файла TeX
weight: 14
url: /net/other-ways-of-main-input/
description: Функциональность преобразования решения Aspose.TeX API для .NET имеет конструктор, который принимает поток в качестве первого аргумента. Вот несколько примеров кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Предоставление основного входного файла движку TeX в виде потока.

До этого момента мы знали только, как передать [основной входной файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) в движок TeX как имя файла, полностью заданное или в краткой форме, с расширением или без него. Но есть еще один [конструктор](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) класса TeXJob, который принимает поток в качестве первого аргумента. Это удобно, если по каким-то причинам основной входной файл у нас имеет форму, отличную от файла файловой системы диска. Вот как это можно реализовать:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-InputStream.cs" >}}

Обратите внимание, что все выходные файлы будут иметь имя *texput*. Это потому, что движок нигде не может получить другого имени. *texput* — это имя задания по умолчанию. [Здесь](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) и [здесь](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) — подробная информация об именах должностей.

## Ввод основного входного файла TeX из терминала

Есть еще один [конструктор](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) класса TeXJob, который вообще не позволяет нам указывать входные данные. Вы можете задаться вопросом, что же будет обрабатывать такое задание TeX? На этот раз нам понадобится входной терминал. Движок TeX попросит нас ввести имя файла из терминала.

Вот код:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-MainInputTerminal.cs" >}}

Как только он запускается, движок зависает, ожидая, пока мы введем имя файла (с путем или без него, с расширением или без него):


![Окно терминала](/tex/images/net/Conversion-MainInputTerminal.png)

А вот как это будет выглядеть на выходном терминале, который является консолью:

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