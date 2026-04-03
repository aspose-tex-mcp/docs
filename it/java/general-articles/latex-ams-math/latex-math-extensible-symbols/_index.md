---
translation: true
template: /templates/_template-java.md
linktitle: Simboli estensibili e regolabili
title: 5. Simboli estensibili e regolabili
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, operatori matematici in LaTeX, delimitatori matematici in LaTeX, parentesi matematiche in LaTeX, graffe matematiche in LaTeX, accenti matematici in LaTeX
description: Questo articolo discute le funzionalità di LaTeX relative al lavoro con simboli matematici estensibili e regolabili.
lastmod: "2026-03-30"
---

{{<section overview>}}

In LaTeX esistono alcune caratteristiche che consentono di produrre strutture capaci di crescere fino a qualsiasi dimensione richiesta. La composizione matematica ha un estremo bisogno di tale variabilità. In questo articolo ne discuteremo alcuni aspetti. Tutti i comandi trattati in questa sezione (se non diversamente indicato) sono forniti dal LaTeX standard.


## 5.1. Ellissi ...

Il pacchetto `amsmath` sostituisce (in quasi tutti i casi) i vari `\ldots`, `\cdots`, ecc. del LaTeX standard con il singolo comando `\dots`. Sia la posizione verticale dell'ellissi che lo spazio intorno ad essa vengono automaticamente selezionati a seconda del tipo di simbolo che segue `\dots`. Se il simbolo successivo è, ad esempio, un segno più, i punti risulteranno centrati; se si tratta di una virgola, cadranno sulla linea di base. Sono sempre tre punti, ma la spaziatura è variabile.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Ellissi con spaziatura automaticamente determinata](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Tuttavia, quando i punti appaiono alla fine di una formula, l'oggetto successivo sarà qualcosa di simile a `\end` o `\)` o `$`, e questo non fornisce a LaTeX alcun indizio sul posizionamento dei punti. In tal caso, è necessario fornire assistenza usando `\dotsc` per i punti seguiti da virgole, `\dotsb` per i punti seguiti da un *operatore binario* o un *simbolo di relazione*, `\dotsm` per i punti seguiti da simboli di moltiplicazione, `\dotsi` per i punti seguiti da integrali o `\dotso` in qualsiasi altro caso.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Ellissi alla fine di una formula](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Simboli che sono orizzontalmente estensibili

Fondamentalmente, LaTeX consente di impostare qualsiasi comando di accento matematico per produrre il glifo appropriato da una gamma di larghezze, ogni volta che questi siano forniti dai font disponibili. Tuttavia, nel LaTeX standard ci sono solo due di tali comandi: `\widehat` e `\widetilde`.

Nel prossimo esempio dimostriamo l'uso di alcuni comandi che producono costrutti simili agli accenti estensibili sopra citati. Tutti producono simboli composti della classe matematica *ordinaria*.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Accenti estensibili](/tex/images/java/tutorial/latex-ams-math-5-3.png)

Qui, "cambio di stile" significa che il simbolo impiegato è influenzato dallo stile matematico in uso, in modo che appaia corretto quando usato, ad esempio, in frazioni o pedici/apici. Quelli che non cambiano lo stile appariranno corretti solo al livello più alto delle formule visualizzate.

## 5.3. Simboli che sono verticalmente estensibili

L'estensibilità verticale è molto più ampia. La tabella seguente elenca tutti i simboli che sono verticalmente estensibili.

*Simboli verticalmente estensibili*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Parentesi"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Graffe aperte"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Doppie barre verticali"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Parentesi angolari"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Graffe chiuse"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Barre verticali singole"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup e Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Quadre aperte"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Barra verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Parentesi a baffo"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Quadre chiuse"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Barra verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Freccia in giù"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Parentesi ceiling aperte"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Barra verticale con freccia"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Freccia in su"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Parentesi floor chiuse"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Barra verticale con graffa"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Freccia su-giù"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Doppie quadre aperte"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Barra verticale doppia con freccia"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Freccia in giù singola"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Barra (Slash)"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Doppia linea verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Freccia in su singola"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Barra inversa (Backslash)"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Doppia linea verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Freccia su-giù singola"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Segno di radice quadrata"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *I simboli in corsivo richiedono il pacchetto `amsmath` o, se scritti in grassetto, il pacchetto `stmaryrd`. Un punto (.) non è di per sé un simbolo estensibile, ma può essere utilizzato per creare un delimitatore "invisibile". Il simbolo `\sqrtsign` non può essere utilizzato con `\left`, `\right` o `\middle`.*

> *Sinonimi: [ - `\lbrack`, `[`;	] - `\rbrack`, `]`;	{ - `\lbrace`, `\{`;	} - `\rbrace`, `\}`; | - `\vert`, `|`;	|| - `\Vert`, `\|`.*

Questi simboli diventano estensibili solo in determinati usi. Devono essere basati sulla seguente costruzione:

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> Se LaTeX utilizza il programma eTeX, è possibile utilizzare questi simboli estensibili anche con `\middle`.

Qui `<ext-Open>` e `<ext-Close>` possono essere uno qualsiasi dei simboli (eccetto `\sqrtsign`) elencati nella tabella sopra. Devono essere simboli che sono stati impostati per essere estensibili come descritto nella [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf). Pertanto, deve essere disponibile un simbolo che rappresenta l'assenza di un vero glifo. Si dà il caso che questo simbolo, noto anche come *null delimiter* (delimitatore nullo), sia il punto (.). Le dimensioni dei glifi effettivi per la composizione di un simbolo estensibile sono scelte per adattarsi all'altezza e alla profondità della sottoformula che si trova tra di loro.

Il simbolo radicale `\sqrtsign` cresce sia verticalmente che orizzontalmente per adattarsi alle dimensioni del suo argomento. In LaTeX, preferireste usare il comando `\sqrt` per ottenere questo simbolo.


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Estendere i radicali](/tex/images/java/tutorial/latex-ams-math-5-24.png)