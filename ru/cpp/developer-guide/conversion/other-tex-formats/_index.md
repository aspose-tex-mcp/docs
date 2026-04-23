---
translation: true
template: /templates/_template-cpp.md
title: Другие выходные форматы преобразования TeX | С++
linktitle: Другие форматы TeX
weight: 18
url: /cpp/other-tex-formats/
description: Функциональность преобразования решения Aspose.TeX API для C++ позволяет конвертировать файлы LaTeX и ваши собственные файлы TeX. Вот несколько примеров кода.
lastmod: "2026-04-20"
---

{{<section overview>}}

Крайне маловероятно, что вы сейчас захотите конвертировать файл TeX, написанный в любом другом формате, кроме LaTeX. Но это возможно, если вы по какой-то причине изучаете язык TeX и/или его внутренности. В любом случае, **Aspose.TeX for C++** позволяет конвертировать файлы, написанные в формате Plain TeX. Он также позволяет создавать собственные форматы и верстать документы, разработанные в этих форматах.

Начнем с создания пользовательского формата.

## Создание пользовательского формата

Напомним, что файл формата представляет собой двоичный дамп внутреннего состояния движка TeX.

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Как видите, код аналогичен коду конвертации файла TeX. Но есть несколько отличий.

Во-первых, здесь мы используем конфигурацию задания [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Это специальная конфигурация, которая оставляет состояние движка «девственным», т. е. внутренние параметры имеют значения по умолчанию, а набор управляющих последовательностей совпадает с набором примитивов. В нашем примере набор примитивов расширен в смысле, упомянутом [здесь](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Далее мы настраиваем рабочие каталоги ввода и вывода как обычно. Входной рабочий каталог должен содержать исходный файл основного формата и все его зависимости.

И второе ключевое отличие — это то, как мы выполняем работу. На этот раз мы используем статический метод [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), который вместе с параметрами принимает имя основного исходного файла, которое должно совпадать с именем формата.

## Набор текста TeX-файла в вашем пользовательском формате

Теперь, когда у нас есть собственный формат TeX, мы хотим набрать файл TeX, написанный в этом формате. Вот код:

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Очевидно, нам нужно как-то указать формат. Прежде всего, нам нужно создать экземпляр класса [FormatProvider](https://reference.aspose.com/tex/cpp/class/aspose.te_x.resource_providers.format_provider). Затем в конструкторе параметров мы используем конфигурацию [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), которая принимает нашего поставщика формата в качестве аргумента и загружает формат поверх «девственного» состояния движка.

Остальная часть кода должна быть вам знакома. Он использует функции, обсуждавшиеся ранее в этом [руководстве](/tex/{{lang.url-fragment}}cpp/conversion/).

## Набор текста файла TeX в формате Plain TeX

Если мы выкинем поставщика формата из только что продемонстрированного кода, движок загрузит формат по умолчанию, то есть [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) в четвертом смысле. Таким образом, если у вас есть файл TeX, написанный в формате Plain TeX, вы можете преобразовать его в любой поддерживаемый целевой формат.