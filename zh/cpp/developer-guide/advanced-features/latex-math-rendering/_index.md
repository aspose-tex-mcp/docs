---
translation: true
template: /templates/_template-cpp.md
title: 乳胶数学公式渲染| C++的Aspose.TeX
linktitle: 乳胶数学公式渲染
weight: 10
url: /cpp/latex-math-formula-rendering/
description: Aspose.TeX API解决方案用于C ++乳胶数学公式渲染。在这里，您将找到该功能的代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

与此主题相关的API参考部分是[此处](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features)。实际上，演示乳胶数学公式渲染功能的最简单方法是从示例开始。这里是：

```C++
    // Create rendering options 
    System::SharedPtr<PngMathRendererOptions> options = System::MakeObject<PngMathRendererOptions>();
    // Sspecify the image resolution 150 dpi
    options->set_Resolution(150);
    // Specify the preamble.
    options->set_Preamble(u"\\usepackage{amsmath}\r\n\\usepackage{amsfonts}\r\n\\usepackage{amssymb}\r\n\\usepackage{color}");
    // Specify the scaling factor 300%.
    options->set_Scale(3000);
    // Specify the foreground color.
    options->set_TextColor(System::Drawing::Color::get_Black());
    // Specify the background color.
    options->set_BackgroundColor(System::Drawing::Color::get_White());
    // Specify the output stream for the log file.
    options->set_LogStream(System::MakeObject<System::IO::MemoryStream>());
    // Specify whether to show the terminal output on the console or not.
    options->set_ShowTerminal(true);
    
    // Create the output stream for the formula image.
    {
        System::SharedPtr<System::IO::Stream> stream = System::IO::File::Open(System::IO::Path::Combine(RunExamples::OutputDirectory, u"math-formula.png"), System::IO::FileMode::Create);
        // Clearing resources under 'using' statement
        System::Details::DisposeGuard<1> __dispose_guard_0({ stream});
        // ------------------------------------------
        try
        {
            System::Drawing::SizeF size = System::MakeObject<Features::PngMathRenderer>()->Render(u"\\begin{equation*}\r\ne^x = x^{\\color{red}0} + x^{\\color{red}1} + \\frac{x^{\\color{red}2}}{2} + \\frac{x^{\\color{red}3}}{6} + \\cdots = \\sum_{n\\geq 0} \\frac{x^{\\color{red}n}}{n!}\r\n\\end{equation*}", stream, options, size);
            
            // Show other results.
            System::Console::get_Out()->WriteLine(options->get_ErrorReport());
            System::Console::get_Out()->WriteLine();
            System::Console::get_Out()->WriteLine(System::String(u"Size: ") + size);
        }
        catch(...)
        {
            __dispose_guard_0.SetCurrentException(std::current_exception());
        }
    }

```

让我们了解细节。首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions)实例，类似于Tex/latex排版。我们在这里同时指定输出图像分辨率。

接下来，我们指定序言。默认序言是：


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

与基本乳胶相比，它提供了更高级的数学公式支持。例如，如果您想在公式中使用自己的突出显示，则可以添加“颜色”软件包，如我们在代码示例中所示。

然后，我们指示渲染器将输出扩展300％。

接下来的两个选项定义了前景和背景颜色。自定义突出显示的未覆盖(“彩色”)的公式的那些部分将显示在`TextColor`颜色中。

该示例的下一行没有太多意义。它只是证明您可以将日志输出引导到某些流。

最后一个选项`ShowTerminal`使您可以切换将终端输出写入控制台。

实际执行渲染的方法是[Mathrenderer.render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render)。它返回点数中的公式大小。

该方法作为第二个参数将其写入图像的流。我们下一步创建流。

最后，我们将`the Mathrenderer.render()`方法本身称为第三个参数。公式的乳胶代码通过第一个参数作为字符串传递。

示例的最后一行打印了数学公式渲染的两个伪像 - 公式的大小和简短的错误报告(如果有错误)。

这是乳胶数学公式渲染的最一般用例。

**您还可以查看基于 [Aspose.TeX for C++ API](https://products.aspose.com/tex/cpp/) 中实现的功能构建的免费 [web 应用程序](https://products.aspose.app/tex/mathrenderer)。**