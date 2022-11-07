---
translation: true
template: /_templates/_create-custom-tex-net.md
title: кастомные файлы TeX | .NET API-решение
url: /net/create-custom-tex/
description: "Решение .NET API для работы с TeX. Включает в себя функциональность для создания пользовательских форматов TeX. Примеры функций C# для настройки TeX."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Создать собственный формат TeX
h2: "Создайте файл пользовательского формата TeX через C# .NET"
---

{{<section overview>}}
---
p1: "TeX известен как один из языков разметки данных. Это основное ядро ​​системы набора публикаций (компьютерного набора). Сомнительно рассматривать [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) как формат файла, потому что это язык программирования. А с другой стороны, это интерпретатор, который понимает этот язык. В любом случае, вкратце, его основная цель — помочь в создании математического или технического текста. На основе ΤeX создано множество различных пакетов. Они предназначены для облегчения обработки документов, особенно когда в них есть формулы или математические уравнения."
p2: "Решение Aspose.TeX API, помимо других функций, позволяет создавать собственные файлы TeX. Здесь вы найдете информацию, объясняющую, как создавать файлы такого индивидуального формата. Такой файл будет иметь настроенные параметры движка. Для этого нам нужно:"
p3: "Aspose.TeX for .NET API — многофункциональный, мощный и простой в использовании API для работы с документами и преобразования для платформы C#."
p4: "Откройте диспетчер пакетов NuGet, найдите Aspose.TeX и установите. Вы также можете использовать следующую команду из консоли диспетчера пакетов."
---

{{<section feature1>}}
---
title: Действия по созданию пользовательского файла TeX C#.
h3: "Код C# для настройки файлов TeX"
item1: "Используя [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) метод [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Класс, создайте параметры движка TeX без формата при расширении движка ObjectTeX."
item2: "С помощью класса [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) укажите рабочий каталог файловой системы для ввода."
item3: "Используйте класс [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/), чтобы указать рабочий каталог файловой системы для вывода."
item4: "Создайте формат, используя метод [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Отформатируйте вывод.
---