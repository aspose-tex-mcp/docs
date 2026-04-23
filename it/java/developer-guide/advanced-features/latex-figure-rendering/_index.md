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

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXFigureRendering.java" >}}

Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions). Lo facciamo qui insieme a specificare la risoluzione dell'immagine di output.

Successivamente, specifichiamo il preambolo. Non esiste un preambolo predefinito per il rendering delle figure in LaTeX, quindi se si desidera, ad esempio, per rendere una grafica tracciata utilizzando il pacchetto `Pict2e` Latex, è necessario specificarlo nel preambolo:

```tex
\usepackage{pict2e}
```

Quindi istruiamo il rendering di ridimensionare l'output del 300%.

L'opzione successiva definisce il colore di sfondo. A differenza del rendering della formula matematica, non specifichiamo un colore in primo piano poiché supponiamo che i colori siano interamente sotto il controllo del codice LaTeX. In effetti, così è il colore di sfondo, quindi questa è solo un'opzione di convenienza.

La riga successiva dell'esempio non ha molto senso. Dimostra solo che è possibile indirizzare l'output del registro su un flusso.

E l'ultima opzione `showterminal` consente di attivare la scrittura dell'output del terminale sulla console.

Il metodo che esegue effettivamente il rendering è [FigureRender.Render()](https://reference.aspose.com/tex/java/com.aspose.tex/figurerenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.FigureRendererOptions-). Restituisce le dimensioni della figura in punti.

Il flusso in cui l'immagine deve essere scritta è accettato dal metodo come secondo argomento. Creiamo il flusso dopo.

E infine, chiamiamo il metodo `figurerender.render()`, passando le opzioni come terzo argomento. Il codice in LaTeX della figura viene approvato come primo argomento.

Le ultime righe dell'esempio stampano due artefatti del rendering della figura: la dimensione della figura e il breve rapporto di errore (nel caso in cui vi siano errori).

Ecco il risultato del rendering.

![Figura in LaTeX rendering a png](/tex/images/java/text-and-formula.png)

Questo è il caso d'uso più generale per la funzione **Latex Figure**.

## Come rendere una figura in LaTeX a SVG

Allo stesso modo, possiamo rendere una figura in LaTeX al formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXFigureRendering.java" >}}

Le differenze sono:

* Usiamo la classe [SvgFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRendererOptions) anziché [PngFigureRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRendererOptions).
* Non specifichiamo la risoluzione.
* Usiamo la classe [SvgFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgFigureRenderer) anziché [PngFigureRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngFigureRenderer).
 
Ecco il risultato:

<a href="/tex/images/java/text-and-formula.svg">![Figura in LaTeX Rendering a SVG](/tex/images/java/text-and-formula.svg)</a>
