---
translation: true
template: /templates/_template-python-net.md
title: Formule matematiche in LaTeX rendering | Python tramite .NET
linktitle: Formule matematiche in LaTeX rendering
weight: 10
url: /python-net/latex-math-formula-rendering/
description: L'articolo fornisce una panoramica della soluzione API Aspose.Tex per Python e la sua funzionalità per il rendering di formule di matematica in LaTeX. Impara gli esempi di codice
lastmod: "2026-04-03"
---

{{<section overview>}}

## Rendering una formula matematica in LaTeX a PNG

Se necessario, dai un'occhiata alla sezione di riferimento [API per questo argomento](https://reference.aspose.com/tex/python-net/aspose.tex.features/). In effetti, il modo migliore per dimostrare la funzione di rendering della formula matematica ** Latex è iniziare con un esempio. Ecco qui:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Arriviamo ai dettagli. In primo luogo, iniziamo un oggetto [Opzioni di rendering](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), simile alla composizione Tex/LaTex, che include le specifiche per la risoluzione dell'immagine di output desiderata.

Successivamente, specifichiamo il preambolo. Il preambolo predefinito è:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

che offre un supporto migliorato per le formule matematiche rispetto al LaTeX standard. Ad esempio, è possibile includere il pacchetto `Color` per personalizzare l'evidenziazione nella formula, come dimostrato nell'esempio del codice fornito.

Quindi istruiamo il rendering di ridimensionare l'output del 300%.

Le due opzioni successive determinano il primo piano e i colori di sfondo. Tutte le parti della formula che non sono interessate dall'evidenziazione personalizzata verranno visualizzate nel colore `TextColor`.

La riga seguente nell'esempio funge da illustrazione che hai la possibilità di reindirizzare l'output del registro su un flusso specifico.

Infine, l'opzione "Showterminal" consente di controllare se l'output del terminale deve essere visualizzato nella console.

Il processo di rendering effettivo viene effettuato dal metodo [MathRender.Render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), che restituisce le dimensioni della formula in punti.

Il metodo accetta il flusso in cui l'immagine verrà scritta come secondo argomento. Successivamente, procediamo a creare il flusso.

E infine, il metodo `MathRender.Render()` viene invocato, con le opzioni superate come terzo argomento. Il codice LaTeX della formula è fornito come primo argomento.

Le righe finali dell'esempio visualizzano due output del processo di rendering della formula matematica: la dimensione della formula e un rapporto di errore conciso, se si verificano errori.

Ecco il risultato del rendering.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Formula di matematica in LaTeX Rendering a PNG](/tex/images/python-net/math-formula.png)</a>

Ciò rappresenta l'applicazione più comune e ampia della formula della formula matematica **Latex**.

**Puoi anche esplorare la [app Web](https://products.aspose.app/tex/equation-editor/png) gratuita, che utilizza la funzione implementata dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/).**

## Rendering una formula matematica in LaTeX a SVG

Allo stesso modo, possiamo convertire una formula matematica in LaTeX in formato SVG usando lo stesso approccio.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Le differenze sono:

* Invece di usare la classe [pngmathrendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/), utilizziamo la classe [svgmathrendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Non specifichiamo la risoluzione.
* Invece di usare la classe [pngmathrender](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/), utilizziamo la classe [svgmathrender](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Ecco il risultato:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Formula di matematica in LaTeX Rendering a SVG](/tex/images/python-net/math-formula.svg)</a>

**Puoi anche esplorare la [app Web](https://products.aspose.app/tex/equation-editor/svg) gratuita, che utilizza la funzione implementata dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/).**