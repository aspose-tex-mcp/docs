---
translation: true
template: /templates/_template-cpp.md
title: Fórmulas de matemática de LaTeX Renderização | C++
linktitle: Fórmulas de matemática de LaTeX renderização
weight: 10
url: /cpp/latex-math-formula-rendering/
description: Solução da API do Aspose.TeX para fórmulas de matemática de LaTeX C ++ A renderização é descrita neste artigo. Aqui você encontrará exemplos de código da funcionalidade.
lastmod: "2025-06-16"
---

{{<section overview>}}

A seção de referência da API relacionada a este tópico é [aqui](https://reference.aspose.com/tex/cpp/aspose.tex.features/). De fato, a maneira mais fácil de demonstrar o recurso de renderização de fórmula matemática do LATEX é começar com o exemplo. Aqui está:

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

Vamos até os detalhes. Primeiro de tudo, criamos uma instância [de renderização](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions/), semelhante à digitação Tex/Latex. Fazemos isso aqui especificando simultaneamente a resolução da imagem de saída.

Em seguida, especificamos o preâmbulo. O preâmbulo padrão é:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

que fornece suporte a fórmula matemática um pouco mais avançado do que o LaTeX básico. Você pode, por exemplo, adicionar o pacote `color` se quiser usar seu próprio destaque na fórmula, como mostramos no exemplo do código.

Em seguida, instruímos o renderizador a escalar a saída em 300%.

As próximas duas opções definem as cores de primeiro plano e fundo. As partes da fórmula que não são cobertas ("coloridas") pelo destaque personalizado serão exibidas na cor `textColor`.

A próxima linha do exemplo não faz muito sentido. Ele apenas demonstra que você pode direcionar a saída de log para algum fluxo.

E a última opção `showterminal` permite alternar a gravação da saída do terminal no console.

O método que realmente executa a renderização é [MathRenderer.render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render/). Ele retorna o tamanho da fórmula em pontos.

O fluxo em que a imagem deve ser escrito é tomada pelo método como o segundo argumento. Criamos o fluxo a seguir.

E, finalmente, chamamos o próprio método de `MathRenderer.render()`, passando as opções como o terceiro argumento. O código do LATEX da fórmula é passado como uma string durante o primeiro argumento.

As últimas linhas do exemplo imprimem dois artefatos de renderização de fórmula matemática - o tamanho da fórmula e o breve relatório de erro (caso haja erros).

Este é o caso de uso mais geral para a renderização de fórmula matemática do LATEX.

**Você também pode conferir o [aplicativo web](https://products.aspose.app/tex) gratuito construído com base no recurso implementado em [Aspose.TeX para C ++ API](https://products.aspose.com/tex/cpp/).**