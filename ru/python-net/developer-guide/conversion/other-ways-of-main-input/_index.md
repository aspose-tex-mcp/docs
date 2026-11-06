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

Укажите выходной каталог в `ASPOSE_TEX_OUTPUT_DIR` (по умолчанию `output`). Предварительно примените лицензию. [Licensing](/tex/ru/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Закодируйте полный документ LaTeX в двоичный поток `BytesIO` и передайте его в `TeXJob` с `TeXConfig.object_latex`. Сохраняйте поток открытым во время задания. Результат: `texput.xps` и `texput.log`.

Обратите внимание, что все выходные файлы будут называться «texput». Это связано с тем, что у движка нет доступа ни к какому другому имени. `texput` — это имя задания по умолчанию. Более подробную информацию о названиях заданий вы можете найти в параграфах [Вывод TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) и [Как задать имя задания](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Ввод основного входного файла TeX через терминал

В классе [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) доступен [еще один конструктор](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions), который вообще не позволяет нам указывать входные данные. Вам может быть интересно, что будет обрабатывать такое задание TeX. В этом случае нам нужно будет использовать входной терминал. Движок TeX предложит нам ввести имя файла из терминала.

Вот код:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Сохраните следующий текст plain TeX как `hello-world.tex` в `ASPOSE_TEX_INPUT_DIR` (по умолчанию `input`). Пример использует `TeXConfig.object_tex()`. При запросе введите `hello-world.tex` и нажмите Enter либо передайте имя через стандартный ввод. Результат: `hello-world.xps` и `hello-world.log`.

```tex
Hello, World!
\end
```
