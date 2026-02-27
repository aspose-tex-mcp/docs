---
translation: true
template: /templates/_template-cpp.md
title: LaTeX 数学公式渲染 | C++
linktitle: LaTeX 数学公式渲染
weight: 10
url: /cpp/latex-math-formula-rendering/
description: 本文介绍了 Aspose.TeX API 在 C++ 中的 LaTeX 数学公式渲染解决方案。您将在此找到功能的代码示例。
lastmod: "2026-02-27"
---

{{<section overview>}}

与本主题相关的 API 参考章节位于[此处](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features)。事实上，演示 LaTeX 数学公式渲染功能最简单的方式是从示例开始。示例代码如下：

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

让我们进入细节。首先，我们创建一个[渲染选项](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions)实例，类似于 TeX/LaTeX 排版。在这里我们同时指定输出图像的分辨率。

接下来，指定前置段（preamble）。默认的前置段如下：

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

它比基本的 LaTeX 提供了稍微更高级的数学公式支持。例如，您可以添加 `color` 包，以便在公式中使用自己的高亮显示，正如我们在代码示例中所展示的。

然后，我们指示渲染器将输出按 300% 缩放。

接下来的两个选项定义前景色和背景色。公式中未被自定义高亮（“着色”）覆盖的部分将以 `TextColor` 颜色显示。

示例中的下一行并没有太大意义，它仅演示了您可以将日志输出定向到某个流。

最后一个选项 `ShowTerminal` 允许您切换是否在控制台上显示终端输出。

实际执行渲染的方法是[MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render)。它返回公式的点数大小。

图像写入的流作为第二个参数由该方法获取。我们随后创建该流。

最后，我们调用 `MathRenderer.Render()` 方法本身，将选项作为第三个参数传入。公式的 LaTeX 代码作为字符串通过第一个参数传递。

示例的最后几行打印了数学公式渲染的两个结果——公式的大小以及简要的错误报告（如果有错误的话）。

这就是 LaTeX 数学公式渲染的最通用用例。

**您还可以查看基于在 [Aspose.TeX for C++ API](https://products.aspose.com/tex/cpp/) 中实现的功能构建的免费[网络应用](https://products.aspose.app/tex/mathrenderer)。**
