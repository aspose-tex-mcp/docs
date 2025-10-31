---
translation: true
template: /templates/_template-net.md
title: Formule matematiche in LaTeX rendering | .NET
linktitle: Formule matematiche in LaTeX rendering
weight: 10
url: /net/latex-math-formula-rendering/
description: Aspose.TeX Soluzione API per le formule matematiche .NET Latex Il rendering è descritta in questo articolo. Impara gli esempi di codice su come utilizzare la funzionalità.
lastmod: "2025-06-13"
---

{{<section overview>}}


## Come rendere una formula matematica in LaTeX a png

La sezione di riferimento API relativa a questo argomento è [qui](https://reference.aspose.com/tex/net/aspose.tex.features/). In effetti, il modo più semplice per dimostrare la funzione **LaTeX Math Rendering** è iniziare con l'esempio. Ecco qui:

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToPNG.cs" >}}

Arriviamo ai dettagli. Prima di tutto, creiamo un'istanza di [rendering options](https://reference.aspose.com/tex/net/aspose.tex.features/mathrendereroptions/), simile alla composizione Tex/Latex. Lo facciamo qui contemporaneamente specificando la risoluzione dell'immagine di output.

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

Il metodo che esegue effettivamente il rendering è [mathrender.render()](https://reference.aspose.com/tex/net/aspose.tex.features/mathrenderer/render/). Restituisce le dimensioni della formula in punti.

Il flusso in cui l'immagine deve essere scritta è accettato dal metodo come secondo argomento. Creiamo il flusso dopo.

E infine, chiamiamo il metodo `mathrenderer.render()`, passando le opzioni come terzo argomento. Il codice LaTeX della formula viene approvato come primo argomento.

Le ultime righe dell'esempio stampano due artefatti del rendering della formula matematica: le dimensioni della formula e il breve rapporto di errore (nel caso in cui vi siano errori).

Ecco il risultato del rendering.

<a href="/tex/net/latex-math-formula-rendering/math-formula.png">![Formula di matematica in LaTeX Rendering a PNG](/tex/images/net/math-formula.png)</a>

Questo è il caso d'uso più generale per la funzione **Latex Math Rendering**.

**È inoltre possibile controllare la [app Web](https://products.aspose.app/tex/equation-editor/png) gratuita in base alla funzionalità implementata in [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

## Come rendere una formula matematica in LaTeX a SVG

Allo stesso modo, possiamo rendere una formula matematica in LaTeX al formato SVG.

{{< gist "aspose-com-gists" "cd0acc55d1634f17dcf42e02075ca005" "Example-RenderMathToSVG.cs" >}}

Le differenze sono:

* Usiamo la classe [svgmathrendereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrendereroptions/) anziché [pngmathrendereroptions](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrendereroptions/).
* Non specifichiamo la risoluzione.
* Usiamo la classe [svgmathrender](https://reference.aspose.com/tex/net/aspose.tex.features/svgmathrenderer/) invece di [pngmathrender](https://reference.aspose.com/tex/net/aspose.tex.features/pngmathrenderer/).
 
Ecco il risultato:

<a href="/tex/net/latex-math-formula-rendering/math-formula.svg">![Formula di matematica in LaTeX Rendering a SVG](/tex/images/net/math-formula.svg)</a>

**Puoi anche controllare la [app Web](https://products.aspose.app/tex/equation-editor/svg) gratuita in base alla funzionalità implementata all'interno di [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**
