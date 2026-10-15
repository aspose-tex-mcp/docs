---
translation: true
template: /templates/_template-java.md
title: Rendering di figura in LaTeX | Java
linktitle: Rendering di figura in LaTeX
weight: 20
url: /java/latex-figure-rendering/
description: Soluzione API Aspose.TeX per il rendering di frammenti di LaTeX Java (Figura) è descritta in questo articolo. Impara gli esempi di codice su come utilizzare la funzionalità.
lastmod: "2026-04-21"
---

{{<section overview>}}

Può succedere che tu voglia estrarre alcuni contenuti (un disegno, una scrittura, una trama, ecc.) Da un file LaTeX come pezzo reso separatamente o una *figura * *, indipendentemente dal suo posto su una pagina del documento di output. È così un illustrazione per la tua pubblicazione su Internet, ad esempio. La nostra API può aiutarti con l'attività. Esistono due formati target disponibili: PNG e SVG. Proprio come nel rendering della formula matematica in LaTeX. Dobbiamo anche notare che **il rendering di figura in LaTeX** è una generalizzazione del [rendering di formula matematica in LaTeX](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/).

## Come rendere una figura in LaTeX a png

E come per il rendering della formula, inizieremo con un esempio. Ecco qui:

Impostare `outputFile` su un `java.nio.file.Path` in una cartella esistente, ad esempio `Paths.get(outputDirectory, "text-and-formula.png")` per PNG o `Paths.get(outputDirectory, "text-and-formula.svg")` per SVG. Importare le classi Aspose.TeX del renderer, delle opzioni e `Size2D` utilizzate, oltre a `java.awt.Color`, `java.io.ByteArrayOutputStream`, `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path`, `java.nio.file.Paths`. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza secondo la [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione.

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToPNG.java" >}}

Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/). Lo facciamo qui insieme a specificare la risoluzione dell'immagine di output.

Successivamente, specifichiamo il preambolo. Non esiste un preambolo predefinito per il rendering delle figure in LaTeX, quindi se si desidera, ad esempio, per rendere una grafica tracciata utilizzando il pacchetto `Pict2e` Latex, è necessario specificarlo nel preambolo:

```tex
\usepackage{pict2e}
```

Quindi istruiamo il rendering di ridimensionare l'output del 300%. Gli esempi impostano anche un margine di 5 punti con `setMargin(5)` intorno alla figura. L'esempio PNG utilizza 150 DPI.

L'opzione successiva definisce il colore di sfondo. A differenza del rendering della formula matematica, non specifichiamo un colore in primo piano poiché supponiamo che i colori siano interamente sotto il controllo del codice LaTeX. In effetti, così è il colore di sfondo, quindi questa è solo un'opzione di convenienza.

L'esempio indirizza i log di rendering a un `ByteArrayOutputStream` con `setLogStream()`. I flussi del log e dell'immagine vengono chiusi automaticamente dopo il rendering.

`showTerminal()` controlla l'output del terminale sulla console. Gli esempi utilizzano `false`; impostare `true` per visualizzarlo.

[FigureRenderer.render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-) viene chiamato su un'istanza di `PngFigureRenderer` o `SvgFigureRenderer` e restituisce le dimensioni della figura in punti come `Size2D`.

Il metodo accetta il flusso di output dell'immagine come secondo argomento. L'esempio lo apre in un blocco try-with-resources, che lo chiude dopo il rendering.

Infine, chiamiamo `render()` sull'istanza del renderer: la figura LaTeX è il primo argomento, il flusso dell'immagine il secondo e le opzioni di rendering il terzo.

Le ultime righe dell'esempio stampano due artefatti del rendering della figura: la dimensione della figura e il breve rapporto di errore (nel caso in cui vi siano errori).

Ecco il risultato del rendering.

![Figura in LaTeX rendering a png](/tex/images/java/text-and-formula.png)

Questo è il caso d'uso più generale per la funzione **Latex Figure**.

## Come rendere una figura in LaTeX a SVG

Allo stesso modo, possiamo rendere una figura in LaTeX al formato SVG.

{{< gist "aspose-com-gists" "4598064edf58fab0b87d9543a4a88234" "Example-RenderFigureToSVG.java" >}}

Le differenze sono:

* Usiamo la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerendereroptions/) anziché [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerendereroptions/).
* Non specifichiamo la risoluzione.
* Usiamo la classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/svgfigurerenderer/) anziché [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/pngfigurerenderer/).
 
Ecco il risultato:

<a href="/tex/images/java/text-and-formula.svg">![Figura in LaTeX Rendering a SVG](/tex/images/java/text-and-formula.svg)</a>
