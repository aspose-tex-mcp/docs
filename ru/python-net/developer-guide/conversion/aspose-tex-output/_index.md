---
translation: true
template: /templates/_template-python-net.md
title: Выходной интерфейс Aspose.TeX | Python
linktitle: Выходной интерфейс Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Вот объяснение функций преобразования решения Aspose.TeX API для Python с TeX в качестве выходного формата и примеры кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

> Формальные определения реализации ввода-вывода см. в [справочнике API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) **Aspose.TeX для Python**.

## Идея выходного каталога

Aspose.TeX определяет каталог как сопоставление имен и объемов данных, где объемами данных могут быть файлы, потоки, массивы или другие типы данных. API позволяет указывать отдельные рабочие каталоги ввода и вывода. Для вывода API предоставляет общий интерфейс [IOutputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), который пользователь может реализовать для своих конкретных нужд. Кроме того, API предоставляет готовые реализации, о которых речь пойдет ниже. Интерфейс *IOutputWorkingDirectory* расширяет [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), поскольку механизм может сначала создать и записать файл, а затем прочитать его обратно. Интерфейс включает метод [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), который возвращает поток для записи, в отличие от метода [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), который возвращает поток для чтения.

### Сохранение вывода в виде файла в файловой системе диска.

Как упоминалось [выше](/tex/{{lang.url-fragment}}net/latex-to-image/), [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) обычно устанавливается как экземпляр класса [OutputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Вот как мы это установим:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Этот конкретный вариант использования прост, поэтому нет необходимости углубляться в него дальше.

### Сохранение вывода в виде файла ZIP-архива.

Другой вариант — создать файл или поток и использовать его в качестве ZIP-архива для хранения выходных файлов. Вот пример:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

Для начала мы создаем выходной поток для ZIP-файла. Затем, после создания параметров преобразования, мы устанавливаем параметр *output_working_directory* как экземпляр класса [OutputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## Идея выходного терминала

Вывод терминала является еще одним важным аспектом вывода. Для этого **Aspose.TeX for Python** определяет общий интерфейс [IOutputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), который имеет единственное свойство, возвращающее экземпляр реализации [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). Доступные реализации будут рассмотрены ниже.

### Запись вывода терминала на консоль

Для этого нам нужно установить опцию [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) как экземпляр класса [OutputConsoleTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Еще раз: это значение параметра по умолчанию, поэтому указывать его нет необходимости. Поэтому данный раздел предоставлен исключительно в демонстрационных целях.

### Запись вывода терминала в файл

В отличие от терминала ввода, **Aspose.TeX for Python** включает реализацию интерфейса *IOutputTerminal*, который позволяет нам записывать вывод терминала в файл в указанном выходном каталоге.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

В этом случае мы указываем движку TeX записать вывод терминала в файл с именем [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, который будет расположен в том же выходном каталоге, что и остальная часть вывода. Однако это не является обязательным. Мы также можем предоставить конструктору любой другой экземпляр реализации *IOutputTerminal*.