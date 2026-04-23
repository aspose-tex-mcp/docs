---
translation: true
template: /templates/_template-net.md
title: Rendering di figura in LaTeX | .NET
linktitle: Il LaTeX include la figura
weight: 20
url: /net/latex-figure-rendering/
description: La soluzione API Aspose.TeX per il rendering di frammenti LaTeX (figure) per .NET è descritta in questo articolo. Scopri gli esempi di codice su come utilizzare la funzionalità.
keywords: figura in LaTeX, dimensione della figura LaTeX, immagine in LaTeX, immagine in LaTeX, LaTeX includono figura, latex pic, opzioni di figura in LaTeX
lastmod: "2026-04-22"
---

{{<section overview>}}


A volte potresti voler estrarre alcuni contenuti da un file LaTeX come pezzo reso separatamente, o una *“figura”*, senza alcuna connessione al layout della pagina. Può essere un'illustrazione per la tua pubblicazione su Internet, per esempio. Puoi farlo con la nostra API. Per quanto riguarda i formati target, ci sono due opzioni: PNG e SVG. Come nel caso della funzione di rendering della formula matematica LaTeX. Vale anche la pena notare che **il rendering di figure LaTeX** è una generalizzazione del [rendering di formule matematiche LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).

## Come eseguire il rendering di una figura LaTeX in PNG

La sezione di riferimento API relativa a questo argomento è [qui](https://reference.aspose.com/tex/net/aspose.tex.features/). E come per il rendering della formula, inizieremo con un esempio. Ecco qui:

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToPNG.cs" >}}

Prima di tutto, creiamo un'istanza [opzioni di figura in LaTeX](https://reference.aspose.com/tex/net/aspose.tex.features/figurerendereroptions/). Lo facciamo qui contemporaneamente specificando la risoluzione dell'immagine di output.

Successivamente, specifichiamo il preambolo. Non esiste un preambolo predefinito per il rendering delle figure in LaTeX, quindi se, ad esempio, stai per rendere una grafica tracciata utilizzando il pacchetto `Pict2e` latex, devi specificarlo nel preambolo:


```tex
\usepackage{pict2e}
```

Quindi istruiamo il rendering di ridimensionare l'output del 300%.

L'opzione successiva definisce il colore di sfondo. A differenza del rendering della formula matematica, non specifichiamo un colore in primo piano poiché supponiamo che i colori siano interamente sotto il controllo del codice LaTeX. In effetti, così è il colore di sfondo, quindi questa è solo un'opzione di convenienza.

La riga successiva dell'esempio non ha molto senso. Dimostra solo che è possibile indirizzare l'output del registro su un flusso.

E l'ultima opzione `showterminal` consente di attivare la scrittura dell'output del terminale sulla console.

Il metodo che esegue effettivamente il rendering è [figurerender.render()](https://reference.aspose.com/tex/net/aspose.tex.features/figurerenderer/render/). Restituisce le dimensioni della figura in punti.

Il flusso in cui l'immagine deve essere scritta è accettato dal metodo come secondo argomento. Creiamo il flusso dopo.

E infine, chiamiamo il metodo `figurerender.render()`, passando le opzioni come terzo argomento. Il codice in LaTeX della figura viene approvato come primo argomento.

Le ultime righe dell'esempio stampano due artefatti del rendering della figura: la dimensione della figura e il breve rapporto di errore (nel caso in cui vi siano errori).

Ecco il risultato del rendering.

<a href="/tex/net/latex-figure-rendering/text-and-formula.png">![Figura in LaTeX rendering a png](/tex/images/net/text-and-formula.png)</a>

Questo è il caso d'uso più generale per la funzione di **rendering delle figure LaTeX**.

## Come rendere una figura in LaTeX a SVG

Allo stesso modo, possiamo rendere una figura in LaTeX in formato SVG.

{{< gist "aspose-com-gists" "79be6a0d7a31aa5deb213ba4ca81cb1b" "Example-RenderFigureToSVG.cs" >}}

Le differenze sono:

* Utilizziamo la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerendereroptions/) invece di [PngFigureRendererOptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerendereroptions/).
* Non specifichiamo la risoluzione.
* Utilizziamo la classe [SvgFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/svgfigurerenderer/) invece di [PngFigureRenderer](https://reference.aspose.com/tex/net/aspose.tex.features/pngfigurerenderer/).
 
Ecco il risultato:

<a href="/tex/net/latex-figure-rendering/text-and-formula.svg">![Figura in LaTeX Rendering a SVG](/tex/images/net/text-and-formula.svg)</a>
