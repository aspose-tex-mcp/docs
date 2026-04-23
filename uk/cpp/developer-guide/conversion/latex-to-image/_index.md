---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX до зображення | C++
linktitle: LaTeX до зображення
weight: 10
url: /cpp/latex-to-image/
keywords: латекс у png, латекс png, латекс у зображення, латексне зображення, латекс у jpg, латекс у jpg, латекс у jpeg, латекс у jpeg, латекс у tiff, латекс у tiff, латекс у bmp, латекс bmp
description: Щоб перетворити TeX у формати зображень за допомогою Aspose.TeX API для C++, ознайомтеся з цією статтею, яка описує, як це зробити, і прикладами коду.
lastmod: 2023-03-23
---

{{<section overview>}}

**Aspose.TeX для C++** також дозволяє нам конвертувати файли LaTeX у ряд інших форматів растрових зображень.

## Як конвертувати LaTeX у PNG

Давайте детально розглянемо код на C++, що забезпечує найпростіший спосіб перетворення LaTeX у формат PNG.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Отже, перше, що нам потрібно зробити (ну, іноді не перше), це створити екземпляр класу [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). Єдиним статичним методом, який це робить, є [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), тож давайте не будемо спантеличуватися значенням його назви. Метод використовує [get_ObjectLaTeX() екземпляр](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) класу [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), який точно підходить для перетворення [файлу LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Ця конфігурація повідомляє механізму Object TeX завантажити формат Object LaTeX і бути готовим прийняти файл LaTeX. Формат Object LaTeX насправді є лише форматом [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за винятком того, що він використовує специфічні примітиви [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для налаштування показників сторінки.

Першим із необхідних параметрів є [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), який визначає простір або область, куди буде записаний вихід TeX. [Тут](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) наведено деталі про концепцію вихідного каталогу в **Aspose.TeX для C++**. У цьому прикладі ми використовуємо клас [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), який дозволяє записувати вихідні дані у вказаний каталог або папку.

Другий варіант — екземпляр класу [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/), який керуватиме перетворенням [об’єктної моделі](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) у цільовий формат. Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [PngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/), який дозволяє нам вказати роздільну здатність вихідних зображень.

Далі нам потрібно створити екземпляр класу [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Бажаючи перетворити файл LaTeX, що зберігається у файловій системі, ми використовуємо [this](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) версію конструктора. Нам потрібно вказати повний шлях до файлу. Інакше механізм шукатиме його в поточному каталозі (це [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) і, швидше за все, не знайде. Тим не менш, ми можемо опустити розширення, якщо наш файл має *.tex*. Механізм додасть його автоматично. Другим аргументом конструктора є екземпляр класу [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Оскільки ми перетворюємо LaTeX у PNG, це екземпляр класу [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) (який є спільним для всіх підтримуваних форматів зображень). В якості останнього аргументу ми передаємо нещодавно підготовлені параметри конвертації.

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
Output written on hello-world.png (1 page).
Transcript written on hello-world.log.
```

Інші «плоди» праці движка ми знайдемо в папці, яку ми вказали як вихідний каталог. Це буде файл стенограми та, **ось він!**, основний вихідний(і) файл(и) зображень PNG.

## Альтернативний спосіб запису основних вихідних файлів PNG

Існує інший спосіб отримати дані зображення у вигляді масиву масивів байтів, кожен масив у другому вимірі представляє дані зображення для окремої сторінки.

```C++
    // Create conversion options for Object LaTeX format on Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectLaTeX());
    // Specify the file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Initialize the options for saving in PNG format.
    options->set_SaveOptions(System::MakeObject<PngSaveOptions>());
    // Run LaTeX to PNG conversion.
    System::SharedPtr<ImageDevice> device = System::MakeObject<ImageDevice>();
    System::MakeObject<TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world.ltx"), device, options)->Run();
    
    // Save pages file by file.
    for (int32_t i = 0; i < device->get_Result()->get_Length(); i++)
    {
        {
            System::SharedPtr<System::IO::Stream> fs = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, System::String(u"page-") + (i + 1) + u".png"), System::IO::FileMode::Create);
            // Clearing resources under 'using' statement
            System::Details::DisposeGuard<1> __dispose_guard_0({ fs});
            // ------------------------------------------
            
            try
            {
                fs->Write(device->get_Result()[i], 0, device->get_Result()[i]->get_Length());
            }
            catch(...)
            {
                __dispose_guard_0.SetCurrentException(std::current_exception());
            }
        }
    }
```
Файл(и) *"page-n.png"* буде записаний у будь-який шлях, який ми вкажемо. На відміну від [PDF output](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), вони дублюватимуть вихідні файли PNG, записані у вихідний каталог.

## Про параметри введення

Якщо наш головний вхідний файл потребує залежностей, наприклад, пакетів, які не входять до базової системи LaTeX і підтримуваних пакетів, ми ПОВИННІ встановити опцію [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) так само, як ми встановлюємо [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory) і помістіть залежності в цей каталог. Залежності можуть бути довільно організовані в підкаталоги. Якщо у нас є власні файли для включення в процес верстки, скажімо, зовнішні графічні файли, ми ПОВИННІ також встановити [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory), використовуючи шлях до розташування, де ці файли зібрано. Ми також можемо розмістити головний вхідний файл десь усередині вхідного каталогу та вказати відносний шлях у методі `run()` (або взагалі не вказати шлях, якщо головний вхідний файл знаходиться в корені). [Тут](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) наведено деталі про концепцію каталогу вводу в **Aspose.TeX для C++** і надані реалізації.

Інші варіанти завдань TeX обговорюються [тут](/tex/{{lang.url-fragment}}cpp/other-options/).

**Ви також можете ознайомитися з безкоштовною веб‑програмою для перетворення LaTeX у PNG, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/cpp/) – сторінка версії C++.**

Нижче ми обговорюємо перетворення LaTeX в інші підтримувані формати растрових зображень. Ми не будемо вдаватися в подробиці лише тому, що їх насправді немає. Єдина відмінність полягає в типі властивості [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) у параметрах перетворення.

## Як конвертувати LaTeX у JPEG

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**Ви також можете ознайомитися з безкоштовною веб‑програмою для перетворення LaTeX у JPEG, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/cpp/) – сторінка версії C++.**

## Як конвертувати LaTeX у TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**Ви також можете скористатися безкоштовною веб‑програмою для перетворення LaTeX у TIFF, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/cpp/) – сторінка версії C++.**

## Як конвертувати LaTeX у BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**Ви також можете ознайомитися з безкоштовною [веб-програмою] для перетворення LaTeX у BMP (36), створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/cpp/) – сторінка версії C++.**