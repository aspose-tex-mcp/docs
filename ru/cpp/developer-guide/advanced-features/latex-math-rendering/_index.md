---
translation: true
template: /templates/_template-cpp.md
title: Рендеринг математических формул LaTeX | С++
linktitle: Отрисовка математических формул LaTeX
weight: 10
url: /cpp/latex-math-formula-rendering/
description: В этой статье описано решение Aspose.TeX API для рендеринга математических формул C++ LaTeX. Здесь вы найдете примеры кода функциональности.
lastmod: "2024-09-24"
---

{{<section overview>}}

Справочный раздел API, связанный с этой темой, находится [здесь](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features). Фактически, самый простой способ продемонстрировать функцию рендеринга математических формул LaTeX — начать с примера. Вот:

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

Давайте перейдем к деталям. Прежде всего, мы создаем экземпляр [параметры рендеринга](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions), аналогичный набору текста TeX/LaTeX. Мы делаем это здесь, одновременно указывая разрешение выходного изображения.

Далее уточняем преамбулу. Преамбула по умолчанию:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

который обеспечивает немного более продвинутую поддержку математических формул, чем базовый LaTeX. Например, вы можете добавить пакет «color», если хотите использовать в формуле собственную подсветку, как мы показали в примере кода.

Затем мы указываем рендереру масштабировать результат на 300%.

Следующие два параметра определяют цвета переднего плана и фона. Те части формулы, которые не покрыты («окрашены») пользовательской подсветкой, будут отображаться цветом TextColor.

Следующая строка примера не имеет особого смысла. Это просто демонстрирует, что вы можете направить вывод журнала в какой-то поток.

И последняя опция «ShowTerminal» позволяет вам переключать запись вывода терминала на консоль.

Метод, который фактически выполняет рендеринг, — это [MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render). Возвращает размер формулы в пунктах.

Поток, в который должно быть записано изображение, принимается методом в качестве второго аргумента. Далее мы создаем поток.

И, наконец, мы вызываем сам метод MathRenderer.Render(), передавая параметры в качестве третьего аргумента. Код формулы LaTeX передается в виде строки через первый аргумент.

В последних строках примера выводятся два артефакта отрисовки математической формулы — размер формулы и краткий отчет об ошибке (на случай, если были ошибки).

Это наиболее общий вариант использования рендеринга математических формул LaTeX.

**Вы также можете ознакомиться с бесплатным [веб-приложением](https://products.aspose.app/tex/mathrenderer), созданным на основе функции, реализованной в [Aspose.TeX for C++ API](https://products.aspose.com/tex/cpp/).**