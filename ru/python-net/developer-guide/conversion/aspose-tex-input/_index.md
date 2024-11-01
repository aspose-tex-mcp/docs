---
translation: true
template: /templates/_template-python-net.md
title: Интерфейс ввода Aspose.TeX | Python
linktitle: Входной интерфейс Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: Функциональность преобразования решения Aspose.TeX API для Python с TeX в качестве входного формата объясняется здесь с примерами кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

> Формальные определения реализации ввода-вывода в **Aspose.TeX для Python** см. в [справочнике API](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## Идея входного каталога

Учитывая, что примитивы ввода-вывода языка TeX могут обрабатывать только имена файлов, **Aspose.TeX for Python** определяет каталог как сопоставление между именами и наборами данных. Этими коллекциями данных могут быть файлы, потоки, массивы или любой другой тип. API позволяет отдельно указывать входные и выходные рабочие каталоги. Он предоставляет общий класс [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), который пользователи могут реализовать для своих конкретных нужд. Кроме того, API предоставляет встроенные реализации, которые будут обсуждаться позже. Интерфейс включает метод [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), который извлекает поток данных и определяет полное имя файла на основе заданного имени, которое служит ключом сопоставления.

### Получение входных файлов из файловой системы диска

Вот какой подход мы бы выбрали:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Этот конкретный вариант использования довольно прост, поэтому мы можем двигаться дальше.

### Получение ввода файла из ZIP-архива

Другой вариант — сохранить входные файлы в ZIP-архиве и использовать его как входной каталог. В таком случае следует выполнить следующие шаги:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

Для начала мы создаем поток, содержащий ZIP-файл. Впоследствии, после создания параметров преобразования, мы присваиваем экземпляр класса [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) свойству [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). Второй параметр конструктора представляет базовый путь внутри архива. Если мы хотим, чтобы весь архив функционировал как входной каталог, мы должны предоставить в качестве аргумента пустую строку.

## Идея входного терминала

Теперь давайте рассмотрим концепцию терминального ввода. **Aspose.TeX для Python** определяет общий интерфейс [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) специально для этой цели, который включает в себя одно свойство, возвращающее экземпляр реализации [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). Доступные реализации будут обсуждаться позже.

### Получение терминального ввода с консоли

Для этого нам нужно назначить экземпляр класса [InputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) опции [terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

Однако, честно говоря, это значение параметра по умолчанию, поэтому нет необходимости явно указывать его. Учитывая отсутствие других реализаций, этот раздел предназначен исключительно для демонстрационных целей.

Теоретически, если у нас есть интерактивный файл (или сценарий) TeX с предсказуемым поведением, может быть желательно реализовать версию входного терминала, включающую соответствующий сценарий для ответа на запросы движка TeX. Не стесняйтесь попробовать, когда у вас будет возможность!