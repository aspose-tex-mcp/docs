---
translation: true
template: /templates/_template-cpp.md
title: Інші вихідні формати перетворення TeX | C++
linktitle: Інші формати TeX
weight: 18
url: /cpp/other-tex-formats/
description: Функція перетворення рішення Aspose.TeX API для C++ дозволяє конвертувати файли LaTeX і ваші власні файли TeX. Ось кілька прикладів коду.
lastmod: "2026-04-20"
---

{{<section overview>}}

Дуже малоймовірно, що зараз ви захочете конвертувати файл TeX, написаний у будь-якому іншому форматі, крім LaTeX. Але це можливо, якщо ви з якоїсь причини вивчаєте мову TeX та/або внутрішні засоби. У будь-якому разі **Aspose.TeX для C++** дозволяє конвертувати файли, написані у форматі Plain TeX. Це також дозволяє створювати власні формати та набирати документи, оформлені в цих форматах.

Ми почнемо зі створення спеціального формату.

## Створення власного формату

Давайте пам’ятаємо, що файл формату є двійковим дампом внутрішнього стану механізму TeX.

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

Як бачите, код схожий на код для перетворення файлу TeX. Але є кілька відмінностей.

По-перше, тут ми використовуємо конфігурацію завдання [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Це спеціальна конфігурація, яка залишає стан двигуна «незайманим», тобто внутрішні параметри мають значення за замовчуванням, а набір керуючих послідовностей збігається з набором примітивів. У нашому прикладі набір примітивів розширено в сенсі, згаданому [тут](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Далі ми налаштовуємо вхідні та вихідні робочі каталоги, як зазвичай. Вхідний робочий каталог має містити вихідний файл основного формату та всі його залежності.

І друга ключова відмінність полягає в тому, як ми виконуємо роботу. Цього разу ми використовуємо статичний метод [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), який разом із параметрами отримує назву основного вихідного файлу, яка має збігатися з назвою формату.

## Набір файлу TeX у вашому спеціальному форматі

Тепер, коли у нас є власний формат TeX, ми хочемо набрати файл TeX, написаний у цьому форматі. Ось код:

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

Вочевидь ми повинні якось визначити формат. Перш за все, нам потрібно створити екземпляр класу [FormatProvider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/). Потім у конструкторі параметрів ми використовуємо конфігурацію [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), яка приймає наш провайдер формату як аргумент і завантажує формат поверх «незайманого» стану двигуна.

Решта коду повинна бути вам знайома. Він використовує функції, розглянуті раніше в цьому [посібнику](/tex/{{lang.url-fragment}}cpp/conversion/).

## Набір файлу TeX у форматі Plain TeX

Якщо ми викинемо постачальника формату з щойно продемонстрованого коду, механізм завантажить формат за замовчуванням, яким є [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) у його четвертому значенні. Таким чином, якщо у вас є файл TeX, написаний у форматі Plain TeX, таким чином ви можете перетворити його в будь-який підтримуваний цільовий формат.