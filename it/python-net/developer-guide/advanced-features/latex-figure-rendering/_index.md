---
translation: true
template: /templates/_template-python-net.md
title: Rendering di figura in LaTeX | Python tramite .NET
linktitle: Il LaTeX include la figura
weight: 20
url: /python-net/latex-figure-rendering/
description: L'articolo fornisce una panoramica della soluzione API Aspose.TeX per Python e la sua funzionalità per il rendering di frammenti di LaTeX (figure). Impara gli esempi di codice.
keywords: figura in LaTeX, dimensione della figura LaTeX, immagine in LaTeX, immagine in LaTeX, LaTeX includono figura, latex pic, opzioni di figura in LaTeX
lastmod: "2026-04-03"
---

{{<section overview>}}

In determinate situazioni, potrebbe essere necessario estrarre contenuti specifici da un file LaTeX come pezzo reso autonomo, comunemente indicata come *figura*, senza alcuna connessione al layout della pagina. Ciò potrebbe essere utile, ad esempio, quando si creano illustrazioni per una pubblicazione online. La nostra API ti consente di raggiungere questo obiettivo. I formati target per le figure di rendering sono PNG e SVG, proprio come con la funzione di rendering della formula matematica in LaTeX. Vale la pena notare che **il rendering di figura in LaTeX** è una caratteristica più generale rispetto al [rendering di formula matematica in LaTeX](/tex/{{lang.url-fragment}}python-net/latex-math-formula-rendering/).

## Rendere una figura in LaTeX a PNG

Se necessario, prima dai un'occhiata alla sezione di riferimento [API per questo argomento](https://reference.aspose.com/tex/python-net/aspose.tex.features/). Simile al rendering della formula, inizieremo con un esempio. Ecco qui:

Impostare `ASPOSE_TEX_OUTPUT_DIR` sulla directory di output oppure usare la cartella predefinita `output`. Tutto il codice LaTeX è incluso negli esempi; non servono file di input esterni. Applicare prima una licenza. [Licenze](/tex/it/python-net/licensing/).

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.py" >}}

Per iniziare, creiamo un'istanza della classe [Opzioni di rendering di figura in LaTeX](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerendereroptions/), in cui specifichiamo contemporaneamente la risoluzione dell'immagine di output.

Successivamente, dobbiamo specificare il preambolo. A differenza del rendering della formula matematica in LaTeX, non esiste un preambolo predefinito per il rendering delle figure in LaTeX. Pertanto, se hai intenzione di rendere la grafica creata utilizzando il pacchetto `pict2e` LaTeX, ad esempio, dovrai specificarlo nel preambolo:

```tex
\usepackage{pict2e}
```

Si imposta `scale = 3000` per una scala del 300% e `margin = 5` per lasciare spazio intorno al frammento. L’esempio PNG usa `resolution = 150` DPI.

L'opzione successiva determina il colore di sfondo. A differenza del rendering della formula matematica, non abbiamo bisogno di specificare un colore in primo piano, poiché supponiamo che i colori siano interamente controllati dal codice LaTeX. Allo stesso modo, il colore di sfondo è anche controllato dal codice LaTeX, quindi questa opzione è semplicemente fornita per comodità.

L’esempio assegna un flusso di file binario a `log_stream` e salva il registro come `text-and-formula.png.log` accanto a `text-and-formula.png`. L’istruzione `with` chiude automaticamente entrambi i flussi.

`show_terminal` controlla l’output del terminale nella console. Gli esempi lo impostano su `False`; il registro viene comunque scritto nel file.

Il metodo responsabile del rendering della figura è [FigureRenderer.render()](https://reference.aspose.com/tex/python-net/aspose.tex.features/figurerenderer/render/). Restituisce le dimensioni della figura in punti.

Il secondo argomento è il flusso di output binario aperto per l’immagine. Il terzo fornisce le opzioni di rendering.

Infine, invochiamo il metodo `FigureRenderer.render()`, passando le opzioni come terzo argomento. Il codice in LaTeX della figura è fornito come primo argomento.

Le ultime righe mostrano il rapporto degli errori, oppure `No rendering errors.` se è vuoto, seguito dalla larghezza e dall’altezza in punti.

Ecco il risultato del rendering.

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.png">![Figura in LaTeX rendering a png](/tex/images/python-net/text-and-formula.png)</a>

Questo rappresenta il caso d'uso più generale per la funzione **Figura Latex**.

## Rendere una figura in LaTeX a SVG

Allo stesso modo, possiamo anche rendere una figura in LaTeX in formato SVG.

{{< gist "aspose-com-gists" "cbf380b84d7f2067481756d42da32b08" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.py" >}}

Questo esempio crea `text-and-formula.svg` e il registro `text-and-formula.svg.log` nella stessa directory di output.

Le differenze sono:

* Invece di utilizzare la classe [PNGFigureRenderEroptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerendereroptions/), utilizziamo la classe [SVGFigureRenderErOptions](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerendereroptions/).
* Non abbiamo bisogno di specificare la risoluzione.
* Invece di utilizzare la classe [PNGFigureReder](https://reference.aspose.com/tex/python-net/aspose.tex.features/pngfigurerenderer/), utilizziamo la classe [Svgfigurerender](https://reference.aspose.com/tex/python-net/aspose.tex.features/svgfigurerenderer/).
 
Ecco il risultato:

<a href="/tex/python-net/latex-figure-rendering/text-and-formula.svg">![Figura in LaTeX Rendering a SVG](/tex/images/python-net/text-and-formula.svg)</a>