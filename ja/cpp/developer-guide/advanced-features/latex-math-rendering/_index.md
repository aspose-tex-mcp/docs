---
translation: true
template: /templates/_template-cpp.md
title: ラテックス数学式レンダリング| C++
linktitle: ラテックス数学式レンダリング
weight: 10
url: /cpp/latex-math-formula-rendering/
description: この記事では、C ++ラテックス数式レンダリング用のAspose.TeX APIソリューションについて説明します。ここでは、機能のコード例が見つかります。
lastmod: "2025-06-09"
---

{{<section overview>}}

このトピックに関連するAPI参照セクションは[ここ](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features)です。実際、ラテックス数学式レンダリング機能を実証する最も簡単な方法は、例から始めることです。ここにあります：

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

詳細について説明しましょう。まず、Tex/LaTexタイプセットと同様に、[レンダリングオプション](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions)インスタンスを作成します。ここでは、出力画像解像度を同時に指定します。

次に、前文を指定します。デフォルトのプリアンブルは次のとおりです。


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```
基本的なラテックスよりもわずかに高度な数学式サポートを提供します。たとえば、コードの例で示したように、式で独自のハイライトを使用する場合は、「Color」パッケージを追加できます。

次に、レンダラーに出力を300％スケーリングするよう指示します。

次の2つのオプションは、前景と背景の色を定義します。カスタムハイライトによって覆われていない(「色付き」)式のこれらの部分は、「TextColor」色で表示されます。

例の次の行はあまり意味がありません。ログ出力をストリームに向けることができることを示しています。

また、最後のオプション「showterminal」を使用すると、ターミナル出力の書き込みをコンソールに切り替えることができます。

実際にレンダリングを実行する方法は[MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render)です。式のサイズをポイントで返します。

画像が書かれるストリームは、2番目の引数としてメソッドによって取得されます。次にストリームを作成します。

そして最後に、 `mathrenderer.render()`メソッド自体を3番目の引数として渡します。式のラテックスコードは、最初の引数の文字列として渡されます。

この例の最後の行には、数学式の2つのアーティファクトが印刷されています。式のサイズと簡単なエラーレポート(エラーがあった場合)。

これは、ラテックス数学式レンダリングの最も一般的なユースケースです。

**[c ++ apiのAspose.TeX](https://products.aspose.com/tex/cpp/)内に実装されている機能に基づいて構築された無料の[Webアプリ](https://products.aspose.app/tex/mathrenderer)をチェックアウトすることもできます。**