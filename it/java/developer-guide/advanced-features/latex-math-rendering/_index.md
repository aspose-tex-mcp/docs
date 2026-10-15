---
translation: true
template: /templates/_template-java.md
title: Formule matematiche in LaTeX rendering | Java
linktitle: Formule matematiche in LaTeX rendering
weight: 10
url: /java/latex-math-formula-rendering/
description: Le formule di matematica in LaTeX rendering all'interno dell'API Aspose.Tex per Java sono descritte in questo articolo. Impara gli esempi di codice su come utilizzare la funzionalità.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Come rendere una formula matematica in LaTeX a png

In effetti, il modo più semplice per dimostrare la funzione di rendering della formula di matematica ** Latex è iniziare con l'esempio. Ecco qui:

Impostare `outputFile` su un `java.nio.file.Path` in una cartella esistente, ad esempio `Paths.get(outputDirectory, "math-formula.png")` per PNG o `Paths.get(outputDirectory, "math-formula.svg")` per SVG. Importare le classi Aspose.TeX del renderer, delle opzioni e `Size2D` utilizzate, oltre a `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza secondo la [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToPNG.java" >}}

Arriviamo ai dettagli. Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/), simile alla composizione Tex/Latex. Lo facciamo qui contemporaneamente specificando la risoluzione dell'immagine di output.

Successivamente, specifichiamo il preambolo. Il preambolo predefinito è:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

che fornisce supporto per la formula matematica leggermente più avanzata rispetto al LaTeX di base. Ad esempio, puoi aggiungere il pacchetto `Color` se si desidera utilizzare il tuo evidenziazione nella formula, come abbiamo mostrato nell'esempio del codice.

Quindi istruiamo il rendering di ridimensionare l'output del 300%.

Le due opzioni definiscono i colori di primo piano e sfondo. Le parti della formula senza evidenziazione personalizzata utilizzano il colore impostato con `setTextColor()`.

L'esempio indirizza i log di rendering a un `ByteArrayOutputStream` con `setLogStream()`. I flussi del log e dell'immagine vengono chiusi automaticamente dopo il rendering.

`showTerminal()` controlla l'output del terminale sulla console. Gli esempi utilizzano `false`; impostare `true` per visualizzarlo.

[MathRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-) viene chiamato su un'istanza di `PngMathRenderer` o `SvgMathRenderer` e restituisce le dimensioni della formula in punti come `Size2D`.

Il metodo accetta il flusso di output dell'immagine come secondo argomento. L'esempio lo apre in un blocco try-with-resources, che lo chiude dopo il rendering.

Infine, chiamiamo `render()` sull'istanza del renderer: la formula LaTeX è il primo argomento, il flusso dell'immagine il secondo e le opzioni di rendering il terzo.

Le ultime righe dell'esempio stampano due artefatti del rendering della formula matematica: le dimensioni della formula e il breve rapporto di errore (nel caso in cui vi fossero errori).

Ecco il risultato del rendering.

<a href="/tex/images/java/math-formula.png">![Figura in LaTeX rendering a png](/tex/images/java/math-formula.png)</a>

Questo è il caso d'uso più generale per il rendering **Latex Math Formula**.

**È inoltre possibile controllare la [app Web](https://products.aspose.app/tex/equation-editor/png) gratuita in base alla funzionalità implementata all'interno dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**

## Come rendere una formula matematica in LaTeX a SVG

Allo stesso modo, possiamo rendere una formula matematica in LaTeX al formato SVG.

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderMathToSVG.java" >}}

Le differenze sono:

* Usiamo la classe [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrendereroptions/) anziché [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrendereroptions/).
* Non specifichiamo la risoluzione.
* Usiamo la classe [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgmathrenderer/) invece di [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngmathrenderer/).

Ecco il risultato:

<a href="/tex/images/java/math-formula.svg">![Formula di matematica in LaTeX Rendering a SVG](/tex/images/java/math-formula.svg)</a>

**Puoi anche controllare la [app Web](https://products.aspose.app/tex/equation-editor/svg) gratuita in base alla funzionalità implementata all'interno di [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**