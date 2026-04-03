---
translation: true
template: /templates/_template-java.md
linktitle: Allineamento e visualizzazione delle equazioni in LaTeX
title: 2. Visualizzazione e allineamento per le equazioni in LaTeX
weight: 10
url: /java/latex-structures-for-equations/
keywords: ams-latex, amsmath, opzioni amsmath, allineamento equazione LaTeX, leqno, eqno, fleqn, tag equazione LaTeX, etichetta equazione LaTeX, equazioni allineate LaTeX
description: Questa è un'introduzione alla composizione delle equazioni LaTeX con i pacchetti AMS-LaTeX e fornisce alcuni esempi e le relative spiegazioni. Equazioni allineate in LaTeX.
lastmod: "2026-03-30"
---

{{<section overview>}}


Il pacchetto *amsmath* contiene una serie di definizioni di ambienti per la composizione di formule matematiche visualizzate. Possono essere classificati in base al numero di righe di materiale (singole o multiple) e al numero di punti di allineamento.

> In questa sezione useremo il termine *equazione* nel modo seguente: per riferirci a una parte *logica* distinta di una visualizzazione matematica, spesso numerata per riferimento e dotata di un'etichetta (ad esempio, il suo numero tra parentesi). Tali etichette sono anche chiamate *tag*.

Il seguente elenco contiene gli ambienti di visualizzazione più popolari. Laddove appropriato, presentano forme stellate in cui non esiste la numerazione delle equazioni.

||
|---|---|---|
| `equation` | `equation*` | Una riga, un'equazione |
| `multline` | `multline*` | Una singola equazione su più righe non allineate, un solo numero di equazione |
| `gather` | `gather*` | Diverse equazioni senza allineamento |
| `align` | `align*` | Diverse equazioni con punti di allineamento multipli |
| `flalign` | `flalign*` | Diverse equazioni: una forma di `align` distribuita orizzontalmente |
| `split` | | Un allineamento semplice all'interno di un'equazione su più righe |

Tutti gli esempi in questo capitolo sono composti con il materiale matematico centrato e i numeri di equazione (tag) sulla destra. Per visualizzare il posizionamento, presentiamo linee verticali blu nell'output che rappresentano i margini sinistro e destro, oltre alla riga centrale. Nel codice sorgente LaTeX, utilizziamo il commento `% -----...` per separare le righe che dovrebbero essere inserite nel preambolo del documento da quelle che dovrebbero trovarsi nel corpo.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

Se desiderate posizionare la matematica a un rientro fisso dal margine sinistro, anziché centrarla nella colonna di testo, è disponibile l'opzione `fleqn`. È possibile specificare la dimensione del rientro nel preambolo impostando il valore della lunghezza elastica `\mathindent`. Il suo valore predefinito è lo stesso del rientro di un elenco di primo livello. Se siete soddisfatti di questo valore, potete omettere l'impostazione della lunghezza `\mathindent`.


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn, reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

Non è necessario passare l'opzione `reqno` qui (essendo il valore predefinito), ma essa sovrascrive le impostazioni della classe del documento, forzando il numero di equazione sulla destra indipendentemente dalle altre impostazioni.

Nel LaTeX standard, `&` e `\\` sono usati per la separazione di riga e colonna all'interno degli allineamenti visualizzati. I dettagli del loro utilizzo cambiano negli ambienti `amsmath`.

## 2.1. Confronto con il LaTeX standard

Alcuni degli ambienti di visualizzazione multilinea consentono di allineare parti della formula. Rispetto agli ambienti standard di LaTeX `eqnarray` ed `eqnarray*`, le strutture definite nel pacchetto `amsmath` offrono un modo leggermente diverso e più semplice di contrassegnare i punti di allineamento. Nel LaTeX standard, `eqnarray*` è simile a un ambiente `array` con `{rcl}` come preambolo, il che significa che sono necessari due caratteri `&` per indicare i due punti di allineamento. Nel pacchetto `amsmath`, le strutture equivalenti hanno un solo punto di allineamento (come se `array` avesse un preambolo `{rl}`), quindi è sufficiente inserire un solo carattere `&` a sinistra del simbolo (solitamente una relazione) che deve essere allineato.

L'ambiente `eqnarray` produce spazio extra nei punti di allineamento a seconda delle impostazioni dei parametri per `array`. Le strutture di `amsmath`, allo stesso tempo, forniscono una spaziatura fissa. La differenza è chiaramente illustrata nel prossimo esempio. La stessa equazione viene composta utilizzando gli ambienti `equation`, `align` ed `eqnarray`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![Amsmath rispetto al LaTeX standard](/tex/images/java/tutorial/latex-ams-math-2-3.png)

Si noti che gli spazi nell'ambiente `eqnarray` risultano troppo ampi per gli standard convenzionali di composizione matematica.

Come nel LaTeX standard, le righe in un display `amsmath` sono contrassegnate con `\\` (o con la fine dell'ambiente). Poiché la rottura di riga in una visualizzazione matematica richiede solitamente una profonda comprensione della struttura della formula, è comunemente considerata oltre le capacità degli odierni software.

## 2.2. Una singola equazione su una riga

Una singola equazione può essere prodotta dall'ambiente `equation`. Un tag viene generato automaticamente e posizionato all'estrema sinistra o destra a seconda dell'opzione in uso. L'ambiente `equation*` produce la stessa equazione senza tag. Il LaTeX standard possiede anche `equation`, ma non `equation*`, poiché quest'ultimo è simile all'ambiente matematico visualizzato standard.

Un fatto notevole è che la presenza del tag non influisce sul posizionamento del contenuto. Il tag verrà spostato verso l'alto o verso il basso nel caso in cui non ci sia spazio sufficiente su una riga: sulla riga precedente quando i tag di equazione sono a sinistra, e sulla riga successiva quando i tag sono a destra.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![Una singola equazione su una riga](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. Una singola equazione su più righe senza allineamento

Una variazione dell'ambiente `equation` è l'ambiente `multline`. Viene utilizzato solo per equazioni che non si adattano a una singola riga. Il carattere `\\` deve essere usato per contrassegnare le interruzioni di riga, poiché esse non vengono individuate automaticamente.

La prima riga di `multline` sarà allineata con un rientro dal margine sinistro e l'ultima con lo stesso rientro dal margine destro. Il valore della lunghezza `\multlinegap` definisce la dimensione di questo rientro.

Ogni riga diversa dalla prima e dall'ultima è centrata singolarmente all'interno della larghezza del display (a meno che non venga utilizzata l'opzione `fleqn`). Tuttavia, se si aggiunge il comando `\shoveleft` o `\shoveright` all'interno di una riga, tale riga sarà forzata rispettivamente a sinistra o a destra.

Un ambiente `multline` possiede un singolo tag, essendo logicamente un'unica equazione. Pertanto, nessuna delle singole righe può essere modificata tramite `\tag` o `\notag`. Il tag, se presente, viene posizionato allineato a destra/sinistra sull'ultima/prima riga quando viene utilizzata l'opzione `reqno`/`leqno`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![Un'unica equazione su più righe](/tex/images/java/tutorial/latex-ams-math-2-5.png)

Il prossimo esempio mostra come `\multlinegap` influisca sul risultato. Nel primo caso, le "*dy*" si allineano, il che fa sembrare che manchi un tag dalla prima riga dell'equazione. Quando `\multlinegap` è impostato a `0`, lo spazio a sinistra della seconda riga non cambia a causa del tag, mentre la prima riga viene spostata sul margine sinistro, rendendo chiaro che si tratta di un'unica equazione.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![L'effetto \multlinegap](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. Una singola equazione su più righe con allineamento

Quando è necessario allineare una singola equazione multilinea, l'ambiente `split` è a vostra disposizione. È sufficiente usare un solo carattere `&` su ogni riga per contrassegnare i punti di allineamento.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![Un'equazione singola con allineamento semplice](/tex/images/java/tutorial/latex-ams-math-2-7.png)

`split` non crea di per sé un tag di equazione (quindi non è necessaria la variante stellata), poiché viene sempre utilizzato come contenuto di una singola equazione. A tale scopo, potete inserirlo in un ambiente esterno.

Per impostazione predefinita, il tag (così come qualsiasi parte dell'equazione all'esterno di `split`) è centrato verticalmente sull'altezza totale del contenuto dell'ambiente `split`. Questo comportamento corrisponde all'opzione `centertags`. Quando si specifica l'opzione `tbtags`, il tag viene posizionato sull'ultima riga di `split` quando il tag è a destra, e sulla prima riga quando il tag è a sinistra.


```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![Un'equazione singola con allineamento semplice e il tag sull'ultima riga](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. Gruppi di equazioni senza allineamento

Quando è necessario inserire due o più equazioni in un singolo display senza allineamento tra di esse, è possibile utilizzare l'ambiente `gather`. Esso centra separatamente ogni equazione all'interno della larghezza del display e fornisce un tag individuale, se necessario. Ogni riga di un `gather` è logicamente una singola equazione.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Gruppo di equazioni senza allineamento](/tex/images/java/tutorial/latex-ams-math-2-9.png)

Potrebbe essere necessario sopprimere il numero dell'equazione per una determinata riga. Il comando `\notag`, inserito nella riga logica, è la soluzione. L'ambiente `gather*` non numera affatto le equazioni.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Gruppo di equazioni con tag omessi](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. Gruppi di equazioni con allineamento semplice

Quando è necessario comporre più di un'equazione in un singolo display e allinearle verticalmente, l'ambiente `align` viene in soccorso. Nel caso più semplice, si utilizza un solo `&` su ogni riga per contrassegnare il punto di allineamento.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![Gruppi di equazioni con allineamento semplice](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. Allineamenti multipli

Un ambiente `align` può definire più punti di allineamento. Il layout contiene tante coppie di colonne quante sono necessarie ed è simile a un `array` con il preambolo `{rlrl...}`. Supponendo che consista di *n* tali coppie di colonne `rl`, il numero di `&` per riga sarà *2n-1*: uno per l'allineamento all'interno di ciascuna coppia di colonne, che dà *n*, e *n-1* caratteri `&` per separare le coppie di colonne.

L'ambiente `align` distribuisce uniformemente il materiale attraverso la larghezza del display. Se c'è spazio extra, questo viene distribuito equamente tra le coppie di colonne adiacenti e i due margini del display.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![Allineamenti multipli](/tex/images/java/tutorial/latex-ams-math-2-12.png)

Il layout di `flalign` è simile, ma non c'è spazio ai margini. Nel prossimo esempio, potete vedere che l'equazione (3) rientra in una riga singola grazie a questo fatto (mentre l'equazione (2) no).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![flalign](/tex/images/java/tutorial/latex-ams-math-2-13.png)

In entrambi i casi, lo spazio minimo tra le coppie di colonne può essere impostato modificando `\minalignsep`. Il valore di default è `10pt` e può essere cambiato con `\renewcommand`, essendo un comando macro anziché un parametro di lunghezza. Il prossimo esempio mostra l’effetto della variazione di `\minalignsep`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![Effetto \minalignsep](/tex/images/java/tutorial/latex-ams-math-2-14.png)

Il prossimo esempio illustra un uso molto comune dell’ambiente `align`. Notate l’uso di `\text` per produrre testo normale all'interno del materiale matematico.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![L'uso di \text](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. Interruzione dei display: `\intertext`

Potreste voler inserire un piccolo frammento di testo tra le righe di un allineamento in un display. Questo si ottiene con il comando `\intertext`. È fondamentale che tutte le proprietà di allineamento rimangano inalterate dal testo, mentre il testo stesso viene composto come un normale paragrafo impostato sulla larghezza del display. L'allineamento non funzionerà se interrompete l'ambiente e ne iniziate uno nuovo dopo il testo. Questo comando deve sempre seguire immediatamente un comando `\\` o `\\*`.


``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![Il comando \intertext](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> Le parole "and finally" sono fuori dall'allineamento, sul margine sinistro, ma tutte e tre le equazioni risultano allineate.

## 2.9. Numerazione delle equazioni e tag

In LaTeX, i tag per le equazioni vengono solitamente generati automaticamente e rappresentano essenzialmente una versione stampata del contatore `equation` di LaTeX. Questo processo avviene in tre passaggi: impostazione del valore del contatore `equation`, formattazione del tag e stampa nella posizione corretta.

I primi due passaggi sono strettamente collegati, poiché il valore del contatore `equation` viene incrementato solo quando il tag corrispondente viene stampato automaticamente. Vediamo un ambiente di visualizzazione che ha sia la forma stellata che quella non stellata. Solo la forma non stellata modifica il valore del contatore `equation`, poiché etichetta automaticamente ogni equazione logica, mentre la forma stellata non lo fa.

Quando è necessario sopprimere la numerazione per una determinata equazione logica all'interno della forma non stellata, si inserisce `\notag` (o `\nonumber`) *prima* del comando `\\`. È inoltre possibile sostituire i tag predefiniti con altri personalizzati utilizzando il comando `\tag` *prima* del `\\`. L'argomento di questo comando può essere un testo normale arbitrario che viene composto, tra parentesi, come tag per tale equazione.
Si noti che anche l'incremento del valore del contatore viene soppresso quando si usa `\tag`. Ciò significa che l'impostazione predefinita del tag è visivamente identica a `\tag{\theequation}`, ma non sono equivalenti. La forma stellata, `\tag*`, compone il testo del suo argomento senza parentesi (e senza altri elementi che potrebbero essere aggiunti da una particolare classe di documento).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![Comandi \tag, \tag*, \notag, \label e \ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Notate come i comandi `\label` e `\ref` vengono utilizzati per fornire una sorta di "numerazione relativa" per le equazioni.

## 2.10. Sequenze di numerazione subordinata

Il pacchetto *amsmath* supporta anche la cosiddetta "sub-numerazione delle equazioni". L'ambiente `subequations` produce tag nella forma (2a), (2b), (2c) e così via. Questo schema di numerazione si basa su due normali contatori LaTeX: `parentequation` ed `equation`. Tutte le equazioni numerate all'interno di un ambiente `subequations` utilizzano questo schema.

L'esempio seguente mostra che il tag può essere ridefinito in una certa misura, ma si noti che la ridefinizione di `\theequation` deve essere inserita all'interno dell'ambiente `subequations`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}
\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![Sequenze di numerazione subordinata](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> L'ambiente `subequations` deve apparire *all'esterno* dei display su cui agisce. Inoltre, non deve essere annidato in se stesso. Il contatore delle equazioni "principali" viene incrementato a ogni utilizzo di questo ambiente. Un comando `\label` all'interno dell'ambiente `subequations` ma al di fuori di ogni singola equazione (logica) produrrà un `\ref` al numero genitore (ad esempio, a 2 anziché a 2i).

## 2.11. Ripristino del contatore delle equazioni

È pratica comune avere equazioni numerate all'interno di sezioni o capitoli con tag della forma (1.1), (1.2), ..., (2.1), (2.2), .... Il pacchetto `amsmath` fornisce un modo semplice per impostare questa configurazione con la dichiarazione `\numberwithin`.

Ad esempio, per ottenere tag di equazione che includano il numero della sezione, con il contatore delle equazioni che viene ripristinato automaticamente per ogni sezione, inserite questa dichiarazione nel preambolo: `\numberwithin{equation}{section}`.

## APPENDICE A. Rendering delle equazioni LaTeX con l'API Aspose.TeX

Vediamo ora come l'API Aspose.TeX consenta di ottenere equazioni LaTeX come figure autonome.

Supponiamo che dobbiate ottenere un'equazione come immagine raster per poterla utilizzare in qualche pubblicazione non-TeX (ad esempio una pagina web). Utilizzando l'API Aspose.TeX, potete farlo come segue:


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

Come potete vedere, l'API è anche in grado di convertire un'equazione LaTeX in un file SVG. Questo era un esempio di utilizzo di Aspose.TeX for .NET. Di seguito è riportato il codice equivalente per la versione Java.


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.aspose.tex.PngMathRendererOptions options = new com.aspose.tex.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.aspose.tex.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

È possibile trovare dettagli sull'uso delle opzioni di rendering nell'articolo sulla resa delle formule matematiche LaTeX con [Aspose.TeX per .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) o [Aspose.TeX per Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/). Tuttavia, un'opzione è particolarmente importante per noi qui. Tramite questa opzione, è possibile specificare il preambolo del documento LaTeX necessario per ottenere il risultato desiderato. (Di seguito, presenteremo solo la versione C# del codice sorgente.)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

Potete anche utilizzare questa opzione quando dovete disporre un'equazione in un'area più stretta rispetto a quanto definito di default da `\textwidth` in LaTeX. Avete due opzioni per raggiungere questo obiettivo:


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Nell'API Aspose.TeX, il seguente preambolo viene utilizzato per impostazione predefinita, quindi a meno che non sia necessario passare opzioni al pacchetto `amsmath` o modificare il `\textwidth` predefinito o altro, non è necessario specificare il preambolo nelle opzioni del renderer:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Appendice B. Rendering delle equazioni LaTeX con l'app web Aspose Equation

Esiste anche l'[app web LaTeX Equation Editor](https://products.aspose.app/tex/equation-editor) che consente di modificare e visualizzare le equazioni LaTeX. È possibile inserire la propria equazione nel campo di testo e cliccare sul pulsante *View* per visualizzare il risultato. In alternativa, è possibile utilizzare il pannello di controllo sopra il campo per costruire l'equazione selezionando una categoria di sottoespressione, quindi la sottoespressione e infine modificando l'argomento, se presente. Potete trovare il preambolo e altre opzioni sotto il campo *Formula*.