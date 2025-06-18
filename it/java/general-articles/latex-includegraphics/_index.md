---
translation: true
template: /templates/_template-java.md
linktitle: Includegraphics
title: LaTeX includegraphics | Aspose.TeX per java
weight: 10
url: /java/latex-includegraphics/
keywords: IncludeGraphics Latex, LaTeX Includex, Insert Images Latex, Latex Graphicx, Latex Insert Image, IncludeGraphics Latex Package, Draw IO Latex, Latex Include Width, include Larghezza, larghezza della figura Latex
description: Scopri la macro del LaTeX Include.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Introduzione

Mentre lavori sui documenti accademici e scientifici, come documenti di ricerca, procedimenti per conferenze e presentazioni accademiche, è possibile che occasionalmente si desidera includere figure grafiche.

Da un lato, possono essere disegni, grafici, istogrammi o qualcos'altro che viene generalmente chiamato grafica vettoriale. I moderni sistemi di LaTeX (come `pdftex`) forniscono molti strumenti per creare tale grafica in un documento. Ad esempio, `Pict2e`,` pgf (tikz) `e` pgfplots` pacchetti. Nella maggior parte dei casi, le figure stesse sono generate da un motore TEX e incluse nel file di output come sequenze di istruzioni grafiche vettoriali appropriate per un formato di output specifico.

D'altra parte, potresti avere immagini raster che desideri includere anche nella tua pubblicazione. Attualmente anche i sistemi LaTex sono in grado di farlo, ma è necessario specificare il percorso del tuo file di immagine nel tuo file Latex come parametro per qualche macro Latex.

Questo articolo copre le immagini raster in file in LaTeX utilizzando la macro `\includegraphics` dal pacchetto` grafico` (e il pacchetto `graphicx`) di accompagnamento.

## Quale pacchetto scegliere, `graphics` o` graphicx`?

Entrambi i pacchetti, `grafica` e ` graphicx`, sono molto simili. La differenza principale è nella sintassi. Mentre il pacchetto `graphics` utilizza un set di macro separate per applicare le trasformazioni su un'immagine, il pacchetto `graphicx` utilizza la notazione `` key = value` per i parametri della macro `\includegraphics 'per specificare queste trasformazioni. Forniremo esempi di ciascun caso d'uso per entrambi i pacchetti contemporaneamente per rendere la differenza più chiara.

## Compreso il pacchetto scelto

Questo viene fatto con il comando `\usapackage` allo stesso modo di qualsiasi altro pacchetto Latex:


```tex
\usepackage{graphics} % to use the graphics package
\usepackage{graphicx} % to use the graphicx package
```

### Specificando un driver

Se il sistema di composizione non è configurato per l'uso, diciamo, `pdftex` per impostazione predefinita, è necessario specificare l'opzione appropriata che costringerà il pacchetto a utilizzare il" driver "richiesto


```tex
\usepackage[pdftex]{graphics} % graphics
\usepackage[pdftex]{graphicx} % graphicx
```

Un `driver` fa parte di un pacchetto che implementa l'interfaccia tra i comandi del pacchetto e le primitive di estensione TEX di basso livello dipendenti dal formato. **ASPUS.TEX** Il supporto grafico in LaTeX è configurato per utilizzare il proprio driver, quindi non è necessario specificare l'opzione driver.

## Macro Latex `\Includegraphics

Ora procediamo con l'esempio più semplice. Questo è ovviamente un caso di includere un'immagine senza alcuna trasformazione. Si prevede che il codice LaTeX che utilizza entrambi i pacchetti è lo stesso:


```tex
\includegraphics{sample-image.png}
```

Questo esempio presuppone che il tuo file di immagine si trovi nella stessa directory del file latex. Ma ci sono diversi modi per specificare una posizione diversa. Il codice LaTeX sarà di nuovo lo stesso per entrambi i pacchetti:


```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Un altro modo per specificare la posizione dei file grafici è definire un elenco di percorsi alternativi usando il comando `\graphicspath` prima di chiamare `\includegraphics`:


```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

## Trasformazioni grafiche in LaTeX

I pacchetti di LaTeX `graphics` e `graphicx` forniscono una serie di modi per manipolare il contenuto.

### Figura in scala Latex

Quindi è possibile ridimensionare la grafica inclusi (in effetti, qualsiasi cosa descritta dal codice tex/latex) come segue:


```tex
% graphics examples
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively

% graphicx examples
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
% there's no analogue for the graphicx package to scale both dimensions independently
```

### Ridimensionare la figura LaTeX

È simile al ridimensionamento, ma si specifica la dimensione richiesta anziché un fattore di ridimensionamento:


```tex
% graphics examples
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proprtions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently

% graphicx examples
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proprtions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Ruota la figura in LaTeX

```tex
% graphics example
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise

% graphicx example
\includegraphics[angle=-10]{sample-image.png} % rotates the image by 10 degrees clockwise
```

### Impostazione di una vista e un ritaglio

```tex
% This time there's no analogue for the graphics package

% graphicx example
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coinsides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

Per quanto riguarda il pacchetto `graphicx`, le trasformazioni possono essere combinate, ma l'ordine è importante.
Per saperne di più sulle funzionalità del pacchetto di pacchetto `graphics`, consultare la [pagina del pacchetto su CTAN](https://ctan.org/pkg/graphics) e
La [documentazione del pacchetto](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

### Il LaTeX include l'app Web gratuita

Se non si desidera lavorare con l'inclusione del pacchetto LaTeX in LaTeX a livello di programmazione, è possibile controllare anche l'app Web gratuita [Latex include grafica](https://products.aspose.app/tex/includegraphics/) basata sulla base di [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/). 

L'app consente di selezionare più immagini e regolare visivamente le trasformazioni per loro. Genera inoltre il codice sorgente in LaTeX utilizzando il pacchetto `graphicx` e lo rende visualizzato il risultato sulla pagina.

### Figura di rendering di figura in LaTeX nella libreria Aspose.TeX

La libreria **Aspose.TeX** fornisce un modo per creare figure raster e SVG che puoi utilizzare nelle tue pubblicazioni al di fuori del contesto Tex/Latex. Ad esempio, su una pagina web. Questo è chiamato **LaTeX figura rendering**. In breve, questa parte dell'API consente di rendere un frammento di codice sorgente in LaTeX indipendentemente dal layout della pagina. Per maggiori dettagli, consultare questo [articolo](/tex/{{lang.url-fragment}}java/latex-figure-rendering/).

L'articolo su [compresi i pacchetti di LaTeX esterni](/tex/{{lang.url-fragment}}java/external-latex-packages/) può anche darti un indizio su come creare figure dai grafici in LaTeX.