---
translation: true
template: /templates/_template-conversion-cpp.md
title: LaTeX в изображение | C++
linktitle: LaTeX для изображения
weight: 10
url: /cpp/latex-to-image/
keywords: латех в png, латех png, латех в изображение, латехное изображение, латех в jpg, латех jpg, латех в jpeg, латех jpeg, латех в tiff, латех tiff, латех в bmp, латех bmp
description: Чтобы преобразовать TeX в форматы изображений с помощью Aspose.TeX для C++, изучите эту статью, в которой описывается, как это сделать, и примеры кода.
lastmod: "2026-04-20"
---

{{<section overview>}}

**Aspose.TeX for C++** также позволяет нам конвертировать файлы LaTeX в ряд других форматов растровых изображений.

## Как конвертировать LaTeX в PNG

Давайте подробно рассмотрим код на C++, обеспечивающий простейший способ преобразования LaTeX в формат PNG.

{{<app/converter 
  input="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.input">}}"  
  formats="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.output">}}"
  title="{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images.title">}}"
>}}
{{<import path="/includes/code-snippets/conversion-cpp.md" section="converter-latex-images">}}
{{</app/converter>}}
        

Итак, первое, что нам нужно сделать (ну, иногда не самое первое), — это создать экземпляр класса [TeXOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions). Единственный статический метод, который это делает, — [ConsoleAppOptions()](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/consoleappoptions), поэтому давайте не будем озадачиваться значением его имени. Метод принимает экземпляр [get_ObjectLaTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/get_objectlatex/) класса [TeXConfig](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config/), который точно подходит для преобразования [файла LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Эта конфигурация сообщает механизму Object TeX загрузить формат Object LaTeX и быть готовым принять файл LaTeX. Формат Object LaTeX на самом деле представляет собой формат [LaTeX](/tex/{{lang.url-fragment}}net/what-is-latex/), за исключением того, что он использует специальные примитивы [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) для настройки показателей страницы.

Первая из обязательных опций — [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory), которая определяет пространство или область, куда будет записываться вывод TeX. [Здесь](/tex/{{lang.url-fragment}}cpp/aspose-tex-output/) приведены подробности концепции выходного каталога в **Aspose.TeX для C++**. В этом примере мы используем класс [OutputFileSystemDirectory](https://reference.aspose.com/tex/cpp/aspose.tex.io/outputfilesystemdirectory), который позволяет нам записывать выходные данные в указанный каталог или папку.

Второй вариант — это экземпляр класса [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation/saveoptions/), который будет управлять преобразованием [объектной модели](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#why-the-new-tex-is-object) в целевой формат. Поскольку мы конвертируем LaTeX в PNG, именно экземпляр класса [PngSaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.image/pngsaveoptions/) позволяет нам указать разрешение выходных изображений.

Далее нам нужно создать экземпляр класса [TeXJob](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/). Желая преобразовать файл LaTeX, хранящийся в файловой системе, мы используем [эту](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/texjob/#texjobtexjobsystemstring-systemsharedptrpresentationdevice-systemsharedptrtexoptions-constructor) версию конструктора. Нам нужно указать полный путь к файлу. В противном случае движок будет искать его в текущем каталоге (то есть [CurrentDirectory](https://docs.microsoft.com/en-us/dotnet/api/system.environment.currentdirectory)) и, скорее всего, не найдет. Тем не менее, мы можем опустить расширение, если наш файл имеет расширение *.tex*. Движок добавит его автоматически. Второй аргумент конструктора — это экземпляр класса [Device](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.device). Поскольку мы конвертируем LaTeX в PNG, это экземпляр класса [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) (который является общим для всех поддерживаемых форматов изображений). В качестве последнего аргумента мы передаем недавно подготовленные варианты конвертации.

Все, что осталось сделать сейчас, это [запустить](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job#a0bc7f8b329ea1f19cbba84bf2060f6fb) задание.

Независимо от того, был ли запуск успешным или нет, первым результатом, который мы увидим, будет вывод терминала. В случае успеха это выглядит примерно так:

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

Остальные «плоды» труда движка мы найдем в папке, которую мы указали в качестве выходного каталога. Это будет файл стенограммы и, **вот он!**, основной выходной файл(ы) изображений PNG.

## Альтернативный способ записи основного выходного файла PNG.

Есть еще один способ получить данные изображения в виде массива байтовых массивов: каждый массив во втором измерении представляет данные изображения для отдельной страницы.

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

Файл(ы) *"page-n.png"* будут записаны по любому указанному нами пути. В отличие от [Вывод PDF](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file), они будут дублировать выходные файлы PNG, записанные в выходной каталог.

## О параметрах ввода

Если наш основной входной файл требует зависимостей, например, пакетов, которые не включены в базовую систему LaTeX и поддерживаемых пакетов, мы ДОЛЖНЫ установить параметр [RequiredInputDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_requiredinputdirectory) аналогично тому, как мы устанавливаем параметр [OutputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_outputworkingdirectory). и поместите зависимости в этот каталог. Зависимости могут быть произвольно организованы в подкаталогах. Если у нас есть собственные файлы, которые нужно включить в процесс верстки, скажем, внешние графические файлы, мы ДОЛЖНЫ также установить [InputWorkingDirectory](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_inputworkingdirectory), используя путь к месту, где собраны эти файлы. Мы также можем поместить основной входной файл где-нибудь внутри входного каталога и указать относительный путь в методе `run()` (или вообще не указывать путь, если основной входной файл находится в корне). [Здесь](/tex/{{lang.url-fragment}}cpp/aspose-tex-input/) приведены подробные сведения о концепции входного каталога в **Aspose.TeX для C++** и предоставленных реализациях.

Другие варианты работы в TeX обсуждаются [здесь](/tex/{{lang.url-fragment}}cpp/other-options/).

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в PNG [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-png), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/cpp/) — страница версии C++.**

Ниже мы обсудим преобразование LaTeX в другие поддерживаемые форматы растровых изображений. Мы не будем вдаваться в подробности только потому, что на самом деле никаких подробностей нет. Единственная разница заключается в типе свойства [SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions) в параметрах преобразования.

## Как конвертировать LaTeX в JPEG

```C++
...
// Initialize the options for saving in JPEG format.
options->set_SaveOptions(System::MakeObject<JpegSaveOptions>());
```

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex-to-jpg) для преобразования LaTeX в JPEG, созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/cpp/) — страница версии C++.**

## Как конвертировать LaTeX в TIFF

```C++
...
// Initialize the options for saving in TIFF format.
options->set_SaveOptions(System::MakeObject<TiffSaveOptions>());
```

**Вы также можете ознакомиться с бесплатным преобразованием LaTeX в TIFF [веб-приложение](https://products.aspose.app/tex/conversion/latex-to-tiff), созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/cpp/) — страница версии C++.**

## Как конвертировать LaTeX в BMP

```C++
...
// Initialize the options for saving in BMP format.
options->set_SaveOptions(System::MakeObject<BmpSaveOptions>());
```

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex-to-bmp) для преобразования LaTeX в BMP, созданным на основе API [Aspose.TeX for .NET](https://products.aspose.com/tex/net/). [Здесь](https://products.aspose.com/tex/cpp/) — страница версии C++.**