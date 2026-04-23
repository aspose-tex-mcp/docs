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

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-PngLaTeXMathRendering.java" >}}

Arriviamo ai dettagli. Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions), simile alla composizione Tex/Latex. Lo facciamo qui contemporaneamente specificando la risoluzione dell'immagine di output.

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

Il metodo che esegue effettivamente il rendering è [MathRender.Render()](https://reference.aspose.com/tex/java/com.aspose.tex/mathrenderer/#render-java.lang.String-java.io.OutputStream-com.aspose.tex.MathRendererOptions-). Restituisce le dimensioni della formula in punti.

Il flusso in cui l'immagine deve essere scritta è accettato dal metodo come secondo argomento. Creiamo il flusso dopo.

E infine, chiamiamo il metodo `mathrenderer.render()`, passando le opzioni come terzo argomento. Il codice LaTeX della formula viene approvato come primo argomento.

Le ultime righe dell'esempio stampano due artefatti del rendering della formula matematica: le dimensioni della formula e il breve rapporto di errore (nel caso in cui vi fossero errori).

Ecco il risultato del rendering.

<a href="/tex/images/java/math-formula.png">![Figura in LaTeX rendering a png](/tex/images/java/math-formula.png)</a>

Questo è il caso d'uso più generale per il rendering **Latex Math Formula**.

**È inoltre possibile controllare la [app Web](https://products.aspose.app/tex/equation-editor/png) gratuita in base alla funzionalità implementata all'interno dell'API [Aspose.TeX per .NET](https://products.aspose.com/tex/net/). [Qui](https://products.aspose.com/tex/java/) è la pagina della versione Java.**

## Come rendere una formula matematica in LaTeX a SVG

Allo stesso modo, possiamo rendere una formula matematica in LaTeX al formato SVG.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-SvgLaTeXMathRendering.java" >}}

Le differenze sono:

* Usiamo la classe [SvgMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRendererOptions) anziché [PngMathRendererOptions](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRendererOptions).
* Non specifichiamo la risoluzione.
* Usiamo la classe [SvgMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/SvgMathRenderer) invece di [PngMathRenderer](https://reference.aspose.com/tex/java/com.aspose.tex/PngMathRenderer).

Ecco il risultato:

<a href="/tex/images/java/math-formula.svg">![Formula di matematica in LaTeX Rendering a SVG](/tex/images/java/math-formula.svg)</a>

**Puoi anche controllare la [app Web](https://products.aspose.app/tex/equation-editor/svg) gratuita in base alla funzionalità implementata all'interno di [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**