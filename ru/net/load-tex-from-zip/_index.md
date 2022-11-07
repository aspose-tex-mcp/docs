---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Загрузка TeX из ZIP | .NET API-решение
url: /net/load-tex-from-zip/
description: "Решение .NET API для работы с TeX. Узнайте на примере, как загрузить файл TeX из ZIP с помощью нескольких строк кода C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Загрузите исходные файлы TeX из ZIP
h2: "Решение .NET API для загрузки файлов TeX из ZIP-архива"
---

{{<section overview>}}
---
p1: "TeX известен как язык набора текста. Это означает, что вы не форматируете свой текст в документе, но вводите простой текст вместе с командами. На выходе вы получите отформатированный файл нужного (заданного) формата. Чтобы лучше понять ввод и вывод TeX, изучите [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) документации."
p2: "Как известно, основная цель TeX — помочь в написании математических или технических текстов. Но перед любыми манипуляциями файл должен быть предварительно загружен. Здесь вы найдете фрагменты кода, объясняющие, как загружать исходные файлы TeX из ZIP, используя каталоги ZIP для ввода и вывода, вывода на устройство PDF, записи вывода терминала на консоль."
p3: "Для загрузки .tex файлов нам нужно:"
p4: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p5: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: "Шаги для загрузки TeX из ZIP-архива C#:"
h3: "Код C# для загрузки TeX"
item1: "Откройте поток в ZIP-архиве, чтобы использовать его в качестве входного рабочего каталога."
item2: "Откройте поток в ZIP-архиве, чтобы использовать его в качестве выходного рабочего каталога."
item3: "Создайте параметры преобразования для формата ObjectTeX по умолчанию при расширении движка ObjectTeX, используя [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метод [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Класс."
item4: "Укажите рабочий каталог ZIP-архива для ввода и/или укажите путь внутри архива. Используйте для этого конструкторы класса [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)."
item5: "Укажите рабочий каталог ZIP-архива для вывода и/или укажите путь внутри архива. Используйте для этого конструкторы класса [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
item6: "Укажите консоль в качестве выходного терминала, используя класс [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Определите параметры сохранения, используя класс [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Запустите метод задания [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) для [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Отформатируйте вывод.
---