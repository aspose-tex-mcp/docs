---
translation: true
template: /templates/_template-net.md
title: Grafica in LaTeX | comando \includegraphics
linktitle: Includegraphics LaTeX
weight: 18
url: /net/latex-graphics/
description: L'inclusione della grafica in Tex è una questione che vale la pena menzionare. Quando ne parlo, la prima cosa che mi viene in mente è il comando `\includegraphics`.
lastmod: 2026-10-19
---

{{<section overview>}}

In realtà, ci sono due aspetti della grafica in LaTeX che vale la pena menzionare:

* Grafica vettoriale descritta direttamente per mezzo di comandi LaTeX/TeX e,
* Inclusione della grafica esterna descritta per mezzo di formati esterni, come EPS, PDF o Raster PNG e PDF.

Il primo ha un supporto limitato nel LaTeX originale e nei suoi pacchetti. È implementato con l'aiuto di regole verticali e orizzontali. Questo perché il LaTeX originale si basa sul motore TeX originale, che produce output principale in formato * DVI *, che non è adatto per descrivere né linee e curve o dati di immagini raster binarie. Ma i motori che sono in grado di produrre formati di supporto grafico (come pdfTeX a PDF) possono anche gestire la grafica utilizzando pacchetti dipendenti dal formato o funzionalità del pacchetto. Quest'ultima grafica non sono supportate nel LaTeX di base per lo stesso motivo. Di seguito discuteremo di caratteristiche di inclusione grafica.

## Il pacchetto `grafico" e il comando `\includegraphics`

Quando si parla di inclusione grafica in LaTeX, la prima cosa che mi viene in mente è il comando `\includegraphics`. È definito nel pacchetto `graphics`, che dovresti menzionare nel preambolo per consentire le sue caratteristiche.

```tex
\usepackage{graphics}
```

Se il sistema di composizione non è configurato per l'uso, diciamo, pdfTeX per impostazione predefinita, è necessario specificare l'opzione appropriata che costringerà il pacchetto a utilizzare il file "driver" richiesto:


```tex
\usepackage[pdftex]{graphics}
```

Un file `driver` fa parte di un pacchetto che implementa l'interfaccia tra i comandi del pacchetto e le primitive di estensione TeX di basso livello dipendenti dal formato. Il supporto grafico in LaTeX Aspose.TeX è configurato per utilizzare il proprio driver, quindi non è necessario specificare l'opzione del driver.

Ora, il modo più semplice per includere, diciamo, un'immagine PNG è digitare:


```tex
\includegraphics{sample-image.png}
```

dove `sample-image.png` è il nome del file che si desidera includere. Potresti persino risolvere l'estensione. Il pacchetto `graphics` contiene l'elenco delle definizioni di formati supportati. Quando si cerca un file, attraversa quell'elenco e include il primo file di corrispondenza trovato.

È inoltre possibile specificare il nome file completo utilizzando un percorso assoluto o relativo:

```tex
\includegraphics{d:/sample-image.png} % absolute path
\includegraphics{./sample-image.png} % relative to the current directory
\includegraphics{../img/sample-image.png} % relative to the directory containing the current one
```

Un altro modo per specificare la posizione dei file grafici è definire un elenco di percorsi alternativi usando il comando `\graphicspath` prima di chiamare`\includegraphics`:

```tex
\graphicspath{{d:/img}{c:/img}{d:/work/img}}
```

### Ridimensionando la grafica

Il pacchetto Latex `graphics` fornisce comandi per manipolare il contenuto. Quindi è possibile ridimensionare la grafica inclusi (in effetti, qualsiasi cosa descritta dal codice tex/latex) come segue:


```tex
\scalebox{.5}{\includegraphics{sample-image.png}} % scales both width and height by 0.5
\scalebox{.5}[1.5]{\includegraphics{sample-image.png}} % scales the width and height by 0.5 and 1.5 respectively
```

### Ridimensionare la grafica

È simile al ridimensionamento, ma si specifica la dimensione richiesta anziché un fattore di ridimensionamento:


```tex
\resizebox{10mm}{!}{\includegraphics{sample-image.png}} % changes the width to 10mm preserving the proportions
\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}} % changes both width and height independently
```

### Ruotando la grafica

```tex
\rotatebox{25}{\includegraphics{sample-image.png}} % rotates the image by 25 degrees counterclockwise
```

## Il pacchetto di LaTeX `graphicx`

Il pacchetto LaTex `graphicx` fornisce l'interfaccia` `key = value` alle trasformazioni dei contenuti. Per abilitare le sue caratteristiche, dovresti menzionarlo nel preambolo:


```tex
\usepackage{graphicx}
\usepackage[pdftex]{graphicx} % with the driver option
```

Puoi combinare una delle seguenti opzioni, ma tieni presente che l'ordine è importante.

### Viewport grafica
```tex
\includegraphics[viewport=10 10 280 220]{sample-image.png} % sets the viewport with the lower left corner
                                                           % at the point (10, 10) (coincides with (0, 0)
                                                           % of the box) and dimensions 280x220pt
\includegraphics[viewport=10 10 250 220,clip]{sample-image.png} % the same, but the image is clipped by the viewport
```

### Grafica di ridimensionamento

```tex
\includegraphics[scale=.5]{sample-image.png} % scales both width and height by 0.5
```

### Ridimensionare la grafica

```tex
\includegraphics[width=15mm]{sample-image.png} % changes the width to 15mm preserving the proportions
\includegraphics[height=15mm,width=25mm]{sample-image.png} % changes both width and height independently
```

### Grafica rotante

```tex
\includegraphics[angle=10]{sample-image.png} % rotates the image by 10 degrees counterclockwise
```

Per saperne di più sulle funzionalità del pacchetto di pacchetti `graphics`, consulta la documentazione [qui](https://ctan.org/pkg/graphics) e
[qui](http://mirrors.ctan.org/macros/latex/required/graphics/graphics.pdf).

**Puoi anche controllare la conversione gratuita [app Web](https://products.aspose.app/tex/conversion/latex/) in base a [Aspose.TeX per API .NET](https://products.aspose.com/tex/net/).**

## Sintassi tradizionale (`graphics`) a confronto con quella moderna (`graphicx`)

Sebbene entrambi i pacchetti condividano il motore di base, essi rappresentano paradigmi profondamente diversi per la gestione dei contenuti in LaTeX.

- Il pacchetto `graphics` si basa su comandi annidati e argomenti posizionali. Ciò richiede di inserire le macro di inclusione all'interno di funzioni di trasformazione separate (ad esempio, annidando `\includegraphics` dentro `\scalebox`).

- Il pacchetto `graphicx` introduce un'interfaccia "chiave-valore" (key-value) pulita ed estensibile, utilizzabile direttamente all'interno degli argomenti opzionali di `\includegraphics`. Questo consente di definire trasformazioni multiple in un unico blocco facilmente leggibile.

| **Operazione** | **Pacchetto tradizionale `graphics`** | **Pacchetto moderno `graphicx`** |
| :- | :- | :- |
| Inclusione di base di un'immagine | `\includegraphics{sample-image.png}` | `\includegraphics{sample-image.png}` |
| Ridimensionamento uniforme | `\scalebox{0.5}{\includegraphics{sample-image.png}}` | `\includegraphics[scale=0.5]{sample-image.png}` |
| Ridimensionamento non uniforme (X/Y indipendenti) | `\scalebox{0.5}[1.5]{\includegraphics{sample-image.png}}` | (Richiede annidamento o pacchetti estesi) |
| Ridimensionamento basato su una dimensione | `\resizebox{10mm}{!}{\includegraphics{sample-image.png}}` | `\includegraphics[width=10mm]{sample-image.png}` |
| Ridimensionamento indipendente di entrambe le dimensioni | `\resizebox{20mm}{10mm}{\includegraphics{sample-image.png}}` | `\includegraphics[width=25mm, height=15mm]{sample-image.png}` |
| Rotazione | `\rotatebox{25}{\includegraphics{sample-image.png}}` | `\includegraphics[angle=25]{sample-image.png}` |
| Ritaglio (viewport clipping) | Richiede sovrascritture del riquadro di delimitazione (bounding box) a un livello inferiore |`\includegraphics[viewport=10 10 280 220, clip]{sample-image.png}`|


### Vantaggi dell'approccio basato su coppie chiave-valore in `graphicx`

1. Combina nativamente trasformazioni multiple:
Con `graphicx`, è possibile applicare ridimensionamento, rotazione e ritaglio simultaneamente in un unico comando, senza dover annidare le macro.

2. Preserva le proporzioni in modo chiaro:
Utilizzando il parametro `keepaspectratio=true` insieme a vincoli espliciti di larghezza o altezza, si evita la distorsione dell'immagine senza dover calcolare manualmente i fattori di scala.

3. Maggiore manutenibilità nella generazione automatizzata:
Quando si sviluppano programmi o script (come quelli basati su Aspose.TeX per .NET) che generano o analizzano dinamicamente file sorgente LaTeX, la costruzione di stringhe di proprietà strutturate (chiave-valore) è molto meno soggetta a errori rispetto all'analisi e all'inserimento di macro annidate.