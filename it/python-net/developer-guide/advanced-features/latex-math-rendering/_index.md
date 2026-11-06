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

Impostare `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output oppure usare la cartella predefinita `output`. Tutto il codice LaTeX è incluso negli esempi; non servono file di input esterni. Applicare prima una licenza. [Licenze](/tex/it/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.py" >}}

Arriviamo ai dettagli. In primo luogo, iniziamo un oggetto [Opzioni di rendering](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrendereroptions/), simile alla composizione Tex/LaTex, che include le specifiche per la risoluzione dell'immagine di output desiderata.

Successivamente, specifichiamo il preambolo. Il preambolo predefinito è:

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

che offre un supporto migliorato per le formule matematiche rispetto al LaTeX standard. Ad esempio, è possibile includere il pacchetto `Color` per personalizzare l'evidenziazione nella formula, come dimostrato nell'esempio del codice fornito.

Si imposta `scale = 3000` per una scala del 300% e `margin = 5` per lasciare spazio intorno al frammento. L’esempio PNG usa `resolution = 150` DPI.

Le due opzioni successive determinano il primo piano e i colori di sfondo. Tutte le parti della formula che non sono interessate dall'evidenziazione personalizzata verranno visualizzate nel colore `text_color`.

L’esempio assegna un flusso di file binario a `log_stream` e salva il registro come `math-formula.png.log` accanto a `math-formula.png`. L’istruzione `with` chiude automaticamente entrambi i flussi.

`show_terminal` controlla l’output del terminale nella console. Gli esempi lo impostano su `False`; il registro viene comunque scritto nel file.

Il processo di rendering effettivo viene effettuato dal metodo [MathRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/mathrenderer/render/), che restituisce le dimensioni della formula in punti.

Il secondo argomento è il flusso di output binario aperto per l’immagine. Il terzo fornisce le opzioni di rendering.

E infine, il metodo `MathRenderer.render()` viene invocato, con le opzioni superate come terzo argomento. Il codice LaTeX della formula è fornito come primo argomento.

Le ultime righe mostrano il rapporto degli errori, oppure `No rendering errors.` se è vuoto, seguito dalla larghezza e dall’altezza in punti.

Ecco il risultato del rendering.

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.png">![Formula di matematica in LaTeX Rendering a PNG](/tex/images/python-net/math-formula.png)</a>

Ciò rappresenta l'applicazione più comune e ampia della formula della formula matematica **Latex**.

**Puoi anche esplorare la [app Web](https://products.aspose.app/tex/equation-editor/png) gratuita, che utilizza la funzione implementata dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/).**

## Rendering una formula matematica in LaTeX a SVG

Allo stesso modo, possiamo convertire una formula matematica in LaTeX in formato SVG usando lo stesso approccio.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.py" >}}

Questo esempio crea `math-formula.svg` e il registro `math-formula.svg.log` nella stessa directory di output.

Le differenze sono:

* Invece di usare la classe [pngmathrendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrendereroptions/), utilizziamo la classe [svgmathrendereroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrendereroptions/).
* Non specifichiamo la risoluzione.
* Invece di usare la classe [pngmathrender](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngmathrenderer/), utilizziamo la classe [svgmathrender](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgmathrenderer/).
 
Ecco il risultato:

<a href="/tex/python-net/latex-math-formula-rendering/math-formula.svg">![Formula di matematica in LaTeX Rendering a SVG](/tex/images/python-net/math-formula.svg)</a>

**Puoi anche esplorare la [app Web](https://products.aspose.app/tex/equation-editor/svg) gratuita, che utilizza la funzione implementata dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/).**