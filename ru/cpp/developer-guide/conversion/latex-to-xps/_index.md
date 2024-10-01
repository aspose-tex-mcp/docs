---
translation: true
template: /templates/_template-cpp.md
title: LaTeX в XPS | Aspose.TeX для C++
linktitle: LaTeX в XPS
weight: 12
url: /cpp/latex-to-xps/
description: Функциональность преобразования решения Aspose.TeX API для C++ позволяет конвертировать файлы LaTeX в формат XPS. Вот несколько примеров кода.
lastmod: "2024-09-24"
---

{{<section overview>}}

Другой целевой формат, поддерживаемый **Aspose.TeX**, — это [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** на самом деле представляет собой ZIP-пакет, содержащий содержимое документа с разбивкой на страницы, а также метаданные, необходимые для правильного отображения конкретными программами просмотра (например, Windows XPS Viewer) и печати. Все данные в пакете представлены файлами. Некоторые из них являются двоичными и содержат такие ресурсы, как изображения, шрифты и профили ICC. Другие представляют собой XML-файлы в различных конкретных схемах. К последним относятся файлы, содержащие сами данные документа. Данные документа состоят из набора файлов – каждый файл содержит данные для отдельной страницы документа. Такие файлы состоят из одного элемента страницы и дерева дочерних элементов — *Canvas*, *Path* и *Glyphs*. *Canvas* — это элемент группировки, который может содержать другие *Canvas*, *Paths* и *Glyphs*. Его задача — контролировать внешний вид всех дочерних элементов как группы. Элементы *Path* используются для определения путей векторной графики. А элементы *Glyphs* используются для определения текстового содержимого. Все три элемента обладают свойствами, определяющими различные аспекты внешнего вида.

Существует библиотека [**Aspose.Page**](https://products.aspose.com/page/), которая предоставляет API для работы с документами XPS, а также для их преобразования в форматы PDF и растровых изображений.

## Как конвертировать LaTeX в XPS

Преобразование в XPS так же просто, как и [преобразование в форматы растровых изображений](/tex/{{lang.url-fragment}}cpp/latex-to-image/), за исключением того, что в дополнение к [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) нам нужно изменить устройство на экземпляр [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device) сорт.

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Альтернативный способ записи основного выходного файла XPS.

Есть еще один конструктор класса [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device#aa24d2c38c5d134d90782b27ba090116a), который позволяет нам получить результирующий XPS-файл альтернативным способом.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> xpsStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.xps"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ xpsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in XPS format.
            options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<XpsDevice>(xpsStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

Эффект тот же, что мы получаем [здесь](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в XPS [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-xps), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/cpp/) — страница версии C++.**