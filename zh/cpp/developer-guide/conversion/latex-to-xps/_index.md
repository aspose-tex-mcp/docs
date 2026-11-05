---
translation: true
template: /templates/_template-cpp.md
title: 乳胶到XPS | Aspose.TeX for C++ 开发指南
linktitle: 乳胶到XPS
weight: 12
url: /cpp/latex-to-xps/
description: C ++的Aspose.TeX API解决方案的转换功能使LATEX文件转换为TEH XPS格式。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

**Aspose.TeX**支持的另一种目标格式是[**xps**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification)。一个**xps**文件实际上是一个zip软件包，其中包含文档的分页内容，以及特定查看者(例如Windows XPS查看器)和打印所需的元数据。软件包中的所有数据均由文件表示。其中一些是二进制的，并且包含图像，字体和ICC配置文件等资源。其他是各种特定模式中的XML文件。后者包括包含文档数据本身的文件。文档数据由一组文件组成 - 每个文件都包含文档单个页面的数据。此类文件由单个页面元素和子元素树组成 -  *canvas*， *path* 和 *glyphs*。 *canvas*是一个分组元素，可以包含其他*帆布*，*路径*和*glyphs*。它的任务是控制所有子元素作为一个小组的外观。 *路径*元素用于定义向量图形路径。 *字形 *元素用于定义文本内容。这三个元素均具有定义外观各个方面的属性。

有[**aspose.page**](https://products.aspose.com/page/)库，该库提供了用于操纵XPS文档的API，并将其转换为PDF和栅格图像格式。

## 如何将乳胶转换为XPS

转换为XPS与[转换为栅格图像格式](/tex/{{lang.url-fragment}}cpp/latex-to-image/)一样简单，除了[SaveOptions](https://reference.aspose.com/tex/cpp/aspose.tex/texoptions/set_saveoptions/)之外，我们还必须将设备更改为[XPSDEVICE](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/)类的实例。

```C++
...
// Initialize the options for saving in Xps format.
options->set_SaveOptions(System::MakeObject<XpsSaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"hello-world.ltx", System::MakeObject<XpsDevice>(), options)->Run();
```

### 编写主输出XPS文件的另一种方法

[XPSDEVICE](https://reference.aspose.com/tex/cpp/aspose.tex.presentation.xps/xpsdevice/#aa24d2c38c5d134d90782b27ba090116a)类的另一个构造函数使我们可以以替代方式获取所得的XPS文件。

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

效果与我们得到[这里](/tex/{{lang.url-fragment}}cpp/latex-to-pdf/#an-alternative-way-to-write-main-output-pdf-file)相同。

**您也可以检查基于[Aspose.TeX for .NET](https://products.aspose.com/tex/net/)API构建的免费乳胶转换[Web App](https://products.aspose.app/tex/conversion/latex-to-xps)。 [这里](https://products.aspose.com/tex/cpp/)是C ++版本页。**