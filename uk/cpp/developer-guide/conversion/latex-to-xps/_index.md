---
translation: true
template: /templates/_template-cpp.md
title: LaTeX до XPS | C++
linktitle: LaTeX до XPS
weight: 12
url: /cpp/latex-to-xps/
description: Функція перетворення рішення Aspose.TeX API для C++ дозволяє конвертувати файли LaTeX у формат XPS.
lastmod: "2025-06-13"
---

{{<section overview>}}

Іншим цільовим форматом, який підтримує **Aspose.TeX**, є [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** насправді є ZIP-пакетом, який містить розбитий на сторінки вміст документа разом із метаданими, необхідними для належного відображення певними засобами перегляду (наприклад, Windows XPS Viewer) і друку. Усі дані в пакеті представлені файлами. Деякі з них є двійковими та містять такі ресурси, як зображення, шрифти та профілі ICC. Інші — це XML-файли в різних конкретних схемах. До останніх відносяться файли, що містять самі дані документа. Дані документа складаються з набору файлів - кожен файл містить дані для окремої сторінки документа. Такі файли складаються з одного елемента сторінки та дерева дочірніх елементів - *Canvas*, *Path* і *Glyphs*. *Canvas* — це груповий елемент, який може містити інші *Canvases*, *Paths* і *Glyphs*. Його місія — контролювати зовнішній вигляд усіх дочірніх елементів як групи. Елементи *Path* використовуються для визначення шляхів векторної графіки. А елементи *Glyphs* використовуються для визначення текстового вмісту. Усі три елементи мають властивості визначати різні аспекти зовнішнього вигляду.

Існує бібліотека [**Aspose.Page**](https://products.aspose.com/page/), яка надає API для роботи з документами XPS, а також для їх перетворення у формати PDF і растрових зображень.

## Як конвертувати LaTeX у XPS

Перетворення на XPS таке ж просте, як і [перетворення на растрові формати зображень](/tex/{{lang.url-fragment}}cpp/latex-to-image/), за винятком того, що на додаток до [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions/), ми маємо змінити пристрій на екземпляр [XpsDevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/) клас.

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### Альтернативний спосіб запису основного вихідного файлу XPS

Є ще один конструктор класу [XpsDevice](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/#aa24d2c38c5d134d90782b27ba090116a), який дозволяє нам отримати кінцевий файл XPS альтернативним способом.

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

Ефект такий самий, як ми отримуємо [тут](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file).

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-xps) для перетворення LaTeX на XPS, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/cpp/) – сторінка версії C++.**