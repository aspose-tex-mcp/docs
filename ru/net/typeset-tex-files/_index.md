---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Функциональность набора текста TeX | .NET API
url: /net/typeset-tex-files/
description: "Решение .NET API для работы с TeX. Узнайте на примере, как создавать наборы TeX с помощью нескольких строк кода C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Набор файлов TeX
h2: "Наберите файл TeX, используя собственный формат TeX C# .NET"
---

{{<section overview>}}
---
p1: "TeX известен как один из языков разметки данных и/или язык набора текста одновременно. Это означает, что вы не форматируете свой текст в документе, но вводите простой текст вместе с командами. На выходе вы получите отформатированный файл нужного (заданного) формата. [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) является центральным ядром системы набора публикаций (компьютерного набора)."
p2: "Чтобы лучше понять верстку TeX, изучите [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) документации. И на этой странице вы найдете фрагменты кода, объясняющие, как набирать файл TeX, используя собственный формат TeX."
p3: "Для запуска примеров нам понадобится:"
p4: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p5: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: Шаги по набору TeX с помощью C#.
h3: "Код C# для верстки TeX"
item1: "Создайте поставщика формата с помощью класса [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Создайте параметры преобразования для пользовательского формата в расширении движка ObjectTeX, используя [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метод [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Класс."
item3: "Укажите рабочий каталог ввода, если основной ввод не предоставляется в виде потока. Для этого используйте класс [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item4: "Укажите рабочий каталог файловой системы для вывода. Для этого используйте класс [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Запустите метод задания [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) для [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Отформатируйте вывод.
---