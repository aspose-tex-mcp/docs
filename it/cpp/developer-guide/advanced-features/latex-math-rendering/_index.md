---
translation: true
template: /templates/_template-cpp.md
title: Formule matematiche in LaTeX rendering | C++
linktitle: Formule matematiche in LaTeX rendering
weight: 10
url: /cpp/latex-math-formula-rendering/
description: Soluzione API Aspose.TeX per le formule di matematica C ++ Latex è descritta in questo articolo. Qui troverai esempi di codice della funzionalità.
lastmod: "2025-06-13"
---

{{<section overview>}}

La sezione di riferimento API relativa a questo argomento è [qui](https://reference.aspose.com/tex/cpp/namespace/aspose.te_x.features). In effetti, il modo più semplice per dimostrare la funzione di rendering della formula matematica in LaTeX è iniziare con l'esempio. Ecco qui:

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

Arriviamo ai dettagli. Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrendereroptions), simile alla composizione Tex/Latex. Lo facciamo qui contemporaneamente specificando la risoluzione dell'immagine di output.

Successivamente, specifichiamo il preambolo. Il preambolo predefinito è:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

che fornisce supporto per la formula matematica leggermente più avanzata rispetto al LaTeX di base. Ad esempio, puoi aggiungere il pacchetto `Color` se si desidera utilizzare il tuo evidenziazione nella formula, come abbiamo mostrato nell'esempio del codice.

Quindi istruiamo il rendering di ridimensionare l'output del 300%.

Le prossime due opzioni definiscono il primo piano e i colori di sfondo. Quelle parti della formula che non sono coperte ("colorate") dall'evidenziazione personalizzata verranno visualizzate nel colore `TextColor`.

La riga successiva dell'esempio non ha molto senso. Dimostra solo che è possibile indirizzare l'output del registro su un flusso.

E l'ultima opzione `showterminal` consente di attivare la scrittura dell'output del terminale sulla console.

Il metodo che esegue effettivamente il rendering è [mathrender.render()](https://reference.aspose.com/tex/cpp/aspose.tex.features/mathrenderer/render). Restituisce le dimensioni della formula in punti.

Il flusso in cui l'immagine deve essere scritta viene preso con il metodo come secondo argomento. Creiamo il flusso dopo.

E infine, chiamiamo il metodo `mathrenderer.render()`, passando le opzioni come terzo argomento. Il codice LaTeX della formula viene superato come stringa attraverso il primo argomento.

Le ultime righe dell'esempio stampano due artefatti del rendering della formula matematica: le dimensioni della formula e il breve rapporto di errore (nel caso in cui vi fossero errori).

Questo è il caso d'uso più generale per il rendering della formula matematica in LaTeX.

**È inoltre possibile controllare la [app Web](https://products.aspose.app/tex/mathrenderer) gratuita in base alla funzionalità implementata all'interno di [Aspose.TeX per API C ++](https://products.aspose.com/tex/cpp/).**