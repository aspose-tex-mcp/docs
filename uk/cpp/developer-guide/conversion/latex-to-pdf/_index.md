---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX у PDF | C++
linktitle: LaTeX у PDF
weight: 11
url: /cpp/latex-to-pdf/
keywords: latex у pdf, latex pdf, конвертація latex у pdf
description: Щоб конвертувати TeX у PDF за допомогою рішення Aspose.TeX API для C++, ознайомтеся з цією статтею, щоб побачити, як це зробити, і приклади коду.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Як конвертувати LaTeX у PDF

Давайте детально розглянемо код на C++, що забезпечує найпростіший спосіб перетворення LaTeX у формат PDF.

{{<app/converter
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-pdf">}}
{{</app/converter>}}

Отже, перше, що нам потрібно зробити (ну, іноді не перше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). Єдиним статичним методом, який це робить, є [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), тож давайте не будемо спантеличуватися значенням його назви. Метод приймає [примірник](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) класу [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація повідомляє механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат Object LaTeX насправді є лише форматом [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) наведено деталі про концепцію вихідного каталогу в **Aspose.TeX для C++**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation/saveoptions/), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfSaveOptions](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/).

Потім нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) версію конструктора. Потрібно вказати повний шлях до файлу. Інакше механізм шукатиме його в поточному каталозі (це [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) і, швидше за все, не знайде. Тим не менш, ми можемо опустити розширення, якщо наш файл має *.tex*. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Оскільки ми перетворюємо LaTeX у PDF, це екземпляр класу [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/). В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

Все, що залишилося зробити зараз, це [запустити](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb) роботу.

Незалежно від того, чи був запуск успішним чи ні, першим результатом, який ми побачимо, буде вихід терміналу. У разі успіху це виглядає приблизно так:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode

(<input_directory>\hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.pdf (1 page).
Transcript written on hello-world.log.
```

Інші «плоди» праці движка ми знайдемо в папці, яку ми вказали як вихідний каталог. Це буде файл стенограми та, **ось він!**, основний вихідний PDF-файл.

## Альтернативний спосіб запису основного вихідного файлу PDF

Є ще один конструктор класу [PdfDevice](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/pdfdevice/), який дозволяє нам отримати кінцевий PDF-файл альтернативним способом.

```C++
    // Create the stream to write the XPS file to.
    {
        System::SharedPtr<System::IO::Stream> pdfStream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"any-name.pdf"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ pdfsStream});
        // ------------------------------------------
        
        try
        {
            // Create conversion options for Object LaTeX format on Object TeX engine extension.
            System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
            // Specify the file system working directory for the output.
            options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            // Initialize the options for saving in PDF format.
            options->set_SaveOptions(System::MakeObject<PdfSaveOptions>());
            // Default value.
            // Run LaTeX to XPS conversion.
            System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), System::MakeObject<PdfDevice>(pdfStream), options)->Run();
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }
```

Файл *any-name.pdf* у вказаному каталозі буде нашим основним вихідним PDF-файлом. У той же час, на відміну від [image output](/tex/{{lang.url-fragment}}cpp/latex-to-image/), ми не знайдемо PDF-файлів у вихідному каталозі, визначеному параметрами перетворення. Виняток: *any-name.pdf* знаходиться (за своїм шляхом) у тому самому каталозі файлової системи, який призначено параметру [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) за допомогою [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory).

## Про параметри введення

Якщо наш основний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо ми маємо власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити головний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або взагалі не вказати шлях, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) наведено деталі про концепцію каталогу вводу в **Aspose.TeX для C++** і надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}cpp/other-options/).

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у PDF (29), створеною на основі [Aspose.TeX для C++ API](https://products.aspose.com/tex/cpp/).**