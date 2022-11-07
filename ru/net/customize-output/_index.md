---
translation: true
template: /_templates/_customize-output-net.md
title: Создать пользовательский вывод TeX | .NET API-решение
url: /net/customize-output/
description: "Решение .NET API для работы с TeX. Прочтите пример, как создать собственный вывод для файла TeX с помощью нескольких строк кода C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Настроить вывод
h2: "Решение .NET API для настройки вывода файлов TeX"
---

{{<section overview>}}
---
p1: "TeX известен как язык набора текста. Это означает, что вы не форматируете свой текст в документе, но вводите простой текст вместе с командами."
p2: "Статья [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) Документации учит нас, что файл TeX может не содержать никаких данных для набора, а только управляющие последовательности. Но  обычно он содержит такие данные, а файл в целевом формате имеет набранный текст. Файл также будет иметь то же имя, что и файл, указанный в качестве входных данных, и является основным выходным файлом. Для оригинального TeX это файл в формате DVI. Мы будем называть имя как входного, так и выходного файлов без расширения имени задания."
p3: "На этой странице вы найдете пример кода, объясняющий создание пользовательского файла формата TeX, где вы можете увидеть, как настроить вывод файлов TeX. Для настройки вывода файлов .tex нам потребуется:"
p4: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p5: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: "Шаги по настройке вывода TeX C#:"
h3: "Код C# для настройки вывода TeX"
item1: "С помощью метода [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метода [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class, создайте параметры механизма TeX без формата при расширении механизма ObjectTeX."
item2: "Используйте класс [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), чтобы указать рабочий каталог файловой системы для ввода."
item3: "Используйте класс [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), чтобы указать рабочий каталог файловой системы для вывода."
item4: "Для создания нового формата используйте метод [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Отформатируйте вывод.
---