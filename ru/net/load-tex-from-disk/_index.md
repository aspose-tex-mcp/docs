---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Загрузка TeX с диска | .NET API-решение
url: /net/load-tex-from-disk/
description: "Решение .NET API для работы с TeX. Узнайте на примере, как загрузить файл TeX с диска с помощью нескольких строк кода C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Загрузить исходные файлы TeX с диска
h2: "Решение .NET API для загрузки файлов TeX/LaTeX с диска"
---

{{<section overview>}}
---
p1: "TeX известен как язык набора текста. Это означает, что вы не форматируете свой текст в документе, но вводите простой текст вместе с командами. На выходе вы получите отформатированный файл нужного (заданного) формата. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) является центральным ядром системы набора публикаций (компьютерного набора). Задание TeX выполняется с явно указанным файлом TeX. Чтобы лучше понять ввод и вывод TeX, изучите [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) документации."
p2: "Как известно, основная цель TeX — помочь в написании математических или технических текстов. Но перед любыми манипуляциями файл должен быть предварительно загружен. Здесь вы найдете фрагменты кода, объясняющие, как загружать исходные файлы TeX с диска, используя каталоги файловой системы для ввода и вывода, вывод на устройство XPS, запись вывода терминала на консоль."
p3: "Для запуска примеров нам понадобится:"
p4: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p5: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: Шаги по загрузке TeX с диска C#.
h3: "Код C# для загрузки TeX"
item1: "Создайте параметры преобразования для пользовательского формата в расширении движка ObjectTeX, используя [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метод [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Класс."
item2: "Укажите рабочий каталог файловой системы для ввода. Для этого используйте класс [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item3: "Укажите рабочий каталог файловой системы для вывода с помощью класса [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Укажите консоль в качестве выходного терминала, используя класс [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "При необходимости укажите терминал памяти в качестве выходного терминала. Для этого используйте класс [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Запустите метод задания [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) для [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Отформатируйте вывод.
---