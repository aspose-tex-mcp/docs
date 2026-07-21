---
translation: true
template: /templates/_template-cpp.md
title: Rendern von LaTeX-Matheformeln | C++
linktitle: Rendern von LaTeX-Matheformeln
weight: 10
url: /cpp/latex-math-formula-rendering/
description: Im Artikel wird die Aspose.TeX-Lösung für das Rendern mathematischer Formeln in C++ LaTeX beschrieben. Hier finden Sie Codebeispiele der Funktionalität.
lastmod: "2026-04-20"
---

{{<section overview>}}

Der API-Referenzabschnitt zu diesem Thema ist [hier](https://reference.aspose.com/tex/cpp/aspose.tex.features/). Tatsächlich lässt sich die LaTeX-Funktion zum Rendern mathematischer Formeln am einfachsten demonstrieren, indem man mit dem Beispiel beginnt. Hier ist es:

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

Kommen wir zu den Details. Zunächst erstellen wir eine [rendering options](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions/)-Instanz, ähnlich dem TeX/LaTeX-Schriftsatz. Wir tun dies hier und geben gleichzeitig die Ausgabebildauflösung an.

Als nächstes spezifizieren wir die Präambel. Die Standardpräambel lautet:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

Dies bietet etwas erweiterte Unterstützung für mathematische Formeln als einfaches LaTeX. Sie können beispielsweise das Paket „color“ hinzufügen, wenn Sie Ihre eigene Hervorhebung in der Formel verwenden möchten, wie wir im Codebeispiel gezeigt haben.

Dann weisen wir den Renderer an, die Ausgabe um 300 % zu skalieren.

Die nächsten beiden Optionen definieren die Vordergrund- und Hintergrundfarben. Die Teile der Formel, die nicht durch die benutzerdefinierte Hervorhebung abgedeckt („eingefärbt“) werden, werden in der Farbe „TextColor“ angezeigt.

Die nächste Zeile des Beispiels ergibt wenig Sinn. Es zeigt lediglich, dass Sie die Protokollausgabe an einen Stream weiterleiten können.

Und mit der letzten Option „ShowTerminal“ können Sie das Schreiben der Terminalausgabe in die Konsole umschalten.

Die Methode, die das Rendern tatsächlich durchführt, ist [MathRenderer.Render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render/). Es gibt die Größe der Formel in Punkten zurück.

Der Stream, in den das Bild geschrieben werden soll, wird von der Methode als zweites Argument verwendet. Als nächstes erstellen wir den Stream.

Und schließlich rufen wir die Methode „MathRenderer.Render()“ selbst auf und übergeben Optionen als drittes Argument. Der LaTeX-Code der Formel wird als String über das erste Argument übergeben.

Die letzten Zeilen des Beispiels geben zwei Artefakte der mathematischen Formeldarstellung aus – die Größe der Formel und den kurzen Fehlerbericht (für den Fall, dass Fehler aufgetreten sind).

Dies ist der allgemeinste Anwendungsfall für die Darstellung mathematischer Formeln in LaTeX.

**Sie können sich auch die kostenlose [Web-App](https://products.aspose.app/tex/mathrenderer) ansehen, die auf der in [Aspose.TeX for C++ API](https://products.aspose.com/tex/cpp/) implementierten Funktion basiert.**