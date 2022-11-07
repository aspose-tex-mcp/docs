---
translation: true
template: /_templates/_customize-input-net.md
title: Создать пользовательский ввод TeX | .NET API-решение
url: /net/customize-input/
description: "Решение .NET API для работы с TeX. Узнайте на примере, как создать пользовательский ввод для файла TeX с помощью нескольких строк кода C#."
keywords: пользовательский ввод tex net api, C# API для настройки tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Настроить ввод
h2: "Решение .NET API для настройки ввода файлов TeX"
---

{{<section overview>}}
---
p1: "TeX известен как язык набора текста. Это означает, что вы не форматируете свой текст в документе, а вводите простой текст вместе с командами. Как описано в статье [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) документации, задание TeX выполняется с явно указанным файлом TeX. Итак, мы включаем этот файл во входные данные определенного задания TeX."
p2: "На этой странице вы найдете пример кода, объясняющий, как настроить ввод исходных файлов TeX с учетом того, что ввод должен следовать синтаксису TeX и, в идеале, содержать только команды, известные движку."
p3: "Для настройки ввода файлов .tex нам потребуется:"
p4: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p5: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: "Шаги по настройке ввода TeX C#:"
h3: "Код C# для настройки ввода TeX"
item1: "Используя [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метод [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Класс, создайте параметры движка TeX без формата при расширении движка ObjectTeX."
item2: "С помощью класса [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) укажите рабочий каталог файловой системы для ввода."
item3: "С помощью метода [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) создайте настраиваемый формат."
---