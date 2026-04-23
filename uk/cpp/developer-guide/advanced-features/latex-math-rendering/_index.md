---
translation: true
template: /templates/_template-cpp.md
title: Відтворення математичних формул LaTeX | C++
linktitle: Відтворення математичних формул LaTeX
weight: 10
url: /cpp/latex-math-formula-rendering/
description: У цій статті описано рішення Aspose.TeX API для відтворення математичних формул C++ LaTeX. Тут ви знайдете приклади коду функціональності.
lastmod: "2026-04-20"
---

{{<section overview>}}

Довідковий розділ API, пов’язаний із цією темою, знаходиться [тут](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features). Насправді, найпростіший спосіб продемонструвати функцію рендеринга математичних формул LaTeX — почати з прикладу. Ось воно:

```C++
    // Create rendering options 
    System::SharedPtr<PngMathRendererOptions> options = System::MakeObject<PngMathRendererOptions>();
    // Specify the image resolution 150 dpi
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

Перейдемо до деталей. Перш за все, ми створюємо екземпляр [параметри візуалізації](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions), подібний до набору TeX/LaTeX. Ми робимо це тут, одночасно вказуючи роздільну здатність вихідного зображення.

Далі уточнюємо преамбулу. Типова преамбула:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

який забезпечує трохи розширенішу підтримку математичних формул, ніж базовий LaTeX. Ви можете, наприклад, додати пакет `color`, якщо хочете використовувати власне виділення у формулі, як ми показали у прикладі коду.

Потім ми наказуємо рендереру масштабувати вихід на 300%.

Наступні два параметри визначають кольори переднього плану та фону. Ті частини формули, які не охоплені («забарвлені») спеціальним виділенням, відображатимуться кольором «Колір тексту».

Наступний рядок прикладу не має особливого сенсу. Це просто демонструє, що ви можете спрямувати вихід журналу в якийсь потік.

І остання опція `ShowTerminal` дозволяє вам перемикати запис виводу терміналу на консоль.

Метод, який фактично виконує візуалізацію, це [MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render). Він повертає розмір формули в пунктах.

Потік, куди буде записано зображення, береться методом як другий аргумент. Далі створюємо потік.

І, нарешті, ми викликаємо сам метод `MathRenderer.Render()`, передаючи параметри як третій аргумент. Код LaTeX формули передається як рядок через перший аргумент.

Останні рядки прикладу друкують два артефакти відтворення математичної формули - розмір формули та короткий звіт про помилку (якщо помилки були).

Це найзагальніший варіант використання відтворення математичних формул LaTeX.

**Ви також можете переглянути безкоштовну [веб-програму](https://products.aspose.app/tex/mathrenderer), створену на основі функції, реалізованої в [Aspose.TeX для C++ API](https://products.aspose.com/tex/cpp/).**