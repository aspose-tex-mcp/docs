---
translation: true
template: /templates/_template-java.md
linktitle: Equazione in LaTeX allineare e visualizzare
title: 2. Visualizzazione e allineamento per le equazioni in LaTeX 
weight: 10
url: /java/latex-structures-for-equations/
keywords: AMS-Latex, Amsmath, Opzioni AMSMath, allineamento dell'equazione in LaTeX, Leqno, Eqno, Fleqn, tag di equazione in LaTeX, etichetta di equazione in LaTeX, equazioni allineate in LaTeX
description: Questa è un'introduzione nelle equazioni del LaTeX da taglio con pacchetti AMS-Latex e fornisce alcuni esempi e le loro spiegazioni. Equazioni allineate in LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}


Il pacchetto *amsmath* contiene una serie di definizioni di ambienti per la digitazione di formule matematiche visualizzate. Possono essere classificati in base al numero di linee materiali (singole o multiple) e dal numero di punti di allineamento.

> In questa sezione, useremo il termine *equazione* nel modo seguente: per riferirci a una parte *logica* distinta di una visualizzazione matematica, spesso numerata per riferimento ed etichettata (ad esempio, con il suo numero tra parentesi). Tali etichette sono anche chiamate *tag*.

Il seguente elenco contiene gli ambienti di visualizzazione più popolari. Laddove appropriato hanno recitato in cui non esiste un tagging delle equazioni.

||
| --- | --- | --- |
| `Equazione '. `equation` | Una riga, un'equazione |
| `MULTRINE`. `multiline*` | Un'equazione di linea multipla non allineata, un numero di equazione |
| `Gather` `Gather*` | Diverse equazioni senza allineamento |
| `align`. `allinea*` | Diverse equazioni con più allineamenti |
| `flallen`. `flallegne*` | Diverse equazioni: forma diffusa orizzontalmente di `align` |
| `split`. | Un semplice allineamento all'interno di un'equazione a più linee |

Tutti gli esempi in questo capitolo sono composti con il materiale matematico centrato e i numeri di equazione (tag) sulla destra. Per visualizzare il posizionamento, presentiamo linee verticali blu nell'uscita che rappresentano i margini sinistra e destra, nonché la linea centrale. Nel codice sorgente in LaTeX, utilizziamo il commento `% -----...` per separare le righe che dovrebbero essere inserite nel preambolo del documento da quelle che dovrebbero essere collocate nel corpo.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![Leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

Se si desidera posizionare la matematica a un rientro fisso dal margine sinistro, piuttosto che centrata nella colonna di testo, l'opzione `Fleqn` è disponibile. È possibile specificare la dimensione del rientro nel preambolo impostando il valore della lunghezza della gomma `\Mathindent`. Il suo valore predefinito è lo stesso del rientro di un elenco di primo livello. Se sei contento di questo valore, puoi saltare l'impostazione della lunghezza `\mathindent`.


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![Fleqn, Reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

Non è necessario passare l'opzione `reqno` qui (in quanto è il valore predefinito), ma sopravvaluta dalle impostazioni della classe del documento, quindi il numero di equazione è forzato a destra qualunque cosa accada.

Nel LaTeX standard, `&` e `\\` sono usati per la separazione della colonna e della linea all'interno degli allineamenti visualizzati. I dettagli del loro cambiamento di utilizzo negli ambienti "Amsmath".

## 2.1. Confronto con il LaTeX standard

Alcuni degli ambienti di visualizzazione multilinea consentono di allineare parti della formula. Rispetto agli ambienti di LaTeX standard `eqnarray` ed` eqnarray*`, le strutture definite nel pacchetto` Amsmath` forniscono un modo leggermente diverso e semplice di contrassegnare i punti di allineamento. Nel LaTeX standard, `eqnarray` è simile a un ambiente `array` con` {rcl} `come preambolo, il che significa che sono necessari due` & `chars per indicare i due punti di allineamento. Nel pacchetto `amsmath`, le strutture equivalenti hanno un solo punto di allineamento (come se` Array` avesse un preambolo `{rl}`), quindi devi mettere solo un `&` Char a sinistra del simbolo (di solito una relazione) che dovrebbe essere allineato.

L'ambiente `Eqnarray` produce spazio extra nei punti di allineamento a seconda delle impostazioni dei parametri per`Array`. Le strutture `amsmath`, allo stesso tempo, danno una spaziatura fissa. La differenza è chiaramente illustrata dal prossimo esempio. La stessa equazione è il composizione utilizzando gli ambienti `Equation`,` align` ed `eqnarray`.


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

Si noti che gli spazi nell'ambiente `eqnarray` escono troppo per gli standard convenzionali di composizione matematica.
Come nel LaTeX standard, le linee in un display `amsmath` sono contrassegnate con` \\ `(o la fine dell'ambiente). Poiché la rottura della linea in una visualizzazione matematica di solito richiede una profonda comprensione della struttura della formula, è comunemente considerata oltre le capacità del software di oggi.

## 2.2. Una singola equazione su una riga

Una singola equazione può essere prodotta dall'ambiente `equation`. Un tag viene generato e posizionato automaticamente all'estremo sinistro o destro secondo l'opzione in uso. L'ambiente `equation` produce la stessa equazione senza un tag. Il LaTeX standard ha anche `equation`, ma non `equation`, poiché quest'ultimo è simile allo standard visualizzato l'ambiente matematico.

Un fatto notevole è che la presenza del tag non influisce sul posizionamento del contenuto. Il tag verrà spostato su o giù nel caso in cui non ci sia abbastanza spazio su una riga: alla riga precedente quando i tag di equazione sono a sinistra e alla riga successiva quando i tag sono a destra.


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

## 2.3. Una singola equazione su diverse righe senza allineamento

Una variazione dell'ambiente `equation`è l'ambiente` Multline`. È usato solo per equazioni che non si adattano a una singola riga. Il carattere `\\` deve essere usato per contrassegnare le interruzioni della linea, poiché non vengono trovate automaticamente.

La prima riga del `Multline` sarà allineata su una rientranza dal margine sinistro e l'ultima sulla stessa rientranza dal margine destro. Il valore della lunghezza `\multlinegap` definisce la dimensione di questo rientro.

Ogni riga dell'altra e dell'ultima è centrata singolarmente all'interno della larghezza del display (a meno che non venga utilizzata l'opzione `Fleqn`). Tuttavia, se aggiungi il comando `\shoveleft` o`\shoveright` all'interno di una riga, quella riga sarà forzata a sinistra oa destra.

Un ambiente `Multline` ha un singolo tag, in quanto logicamente è un'unica equazione. Pertanto, nessuna delle singole linee può essere modificata mediante l'uso di `\tag` o`\notag`. Il tag, se presente, è posizionato a filo destro/sinistro sull'ultima/prima riga quando viene utilizzata l'opzione `reqno`/` leqno`.


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

Il prossimo esempio mostra come `\multlinegap` influisca sul risultato. Nel primo caso, la line up "*dy*" s, che sembra che un tag manchi dalla prima riga dell'equazione. Quando `\multlinegap` è impostato su` 0`, lo spazio a sinistra della seconda riga non cambia a causa del tag, mentre la prima riga viene spostata sul margine sinistro, rendendo chiaro che si tratta di un'unica equazione.


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

![L'effetto \ multlinegap](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. Una singola equazione su diverse linee con allineamento

Quando è necessario allineare una singola equazione multilinea, l'ambiente `split` è al tuo servizio. Basta usare un singolo char `&` su ogni riga per contrassegnare i punti di allineamento.

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

![Un singolo equazione con semplice allineamento](/tex/images/java/tutorial/latex-ams-math-2-7.png)

A `split` non crea di per sé un tag di equazione (quindi non è necessaria la variante stellata), perché è sempre usata come contenuto di una singola equazione. A tale scopo, puoi metterlo in un ambiente esterno.

Per impostazione predefinita, il tag (così come qualsiasi parte dell'equazione al di fuori della `split`) è centrato verticalmente sull'altezza totale del materiale ambientale `split `. Questo comportamento corrisponde all'opzione `Centertags`. Quando si specifica l'opzione `tbtags`, il tag viene posizionato sull'ultima riga di `split` quando il tag è a destra e sulla prima riga quando il tag è a sinistra.


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

![Un singolo equazione con semplice allineamento e il tag sull'ultima riga](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. Gruppi di equazioni senza allineamento

Quando è necessario inserire due o più equazioni in un singolo display senza allineamento tra le equazioni, è possibile utilizzare l'ambiente `Gather`. Inoltre, centra separatamente ogni equazione all'interno della larghezza del display ed equipa con un singolo tag, se necessario. Ogni riga di un `Gather` è logicamente una singola equazione.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Gruppo di equazioni senza allineamento](/tex/images/java/tutorial/latex-ams-math-2-9.png)

Potrebbe essere necessario sopprimere il numero di equazione per una determinata riga. Il comando `\notag`, inserito nella linea logica, è la risposta. L'ambiente `gather` non tagga affatto equazioni.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Gruppo di equazioni con tag OMMEMIME](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. Gruppi di equazioni con semplice allineamento

Quando è necessario compromettere più di un'equazione in un singolo display e allinearli in verticale, l'ambiente `allinea` viene in soccorso. Nel caso più semplice, si utilizza un singolo `&` su ogni riga per contrassegnare il punto di allineamento.


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

![Gruppi di equazioni con semplice allineamento](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. Allineamenti multipli

Un ambiente `align` può definire più punti di allineamento. Il layout contiene tante coppie di colonne necessarie ed è simile a un `array` con il preambolo` {rlrl ...} `. Supponendo che consista di *n*tali coppie di colonne `rl`, il numero di` & `'' per riga sarà *2n-1 *: uno per l'allineamento all'interno di ciascuna coppia di colonne che dà *n*; e * n - 1 * `&` 'S per separare le coppie di colonne.

L'ambiente `align" diffonde uniformemente il materiale attraverso la larghezza del display. Se c'è spazio extra, è distribuito ugualmente tra coppie di colonne adiacenti e due margini di visualizzazione.


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

Il layout del `flalleg 'è simile, ma non c'è spazio ai margini. Nel prossimo esempio, puoi vedere che l'equazione (3) si adatta a una singola riga a causa di questo fatto (mentre l'equazione (2) non lo è ancora).


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

![flaluente](/tex/images/java/tutorial/latex-ams-math-2-13.png)

In entrambi i casi lo spazio minimo tra le coppie di colonne può essere impostato modificando `\minalignsep`. Il valore predefinito è `10pt` e può essere modificato con`\RenewCommand`, in quanto è un comando macro anziché un parametro di lunghezza. Il prossimo esempio dimostra l'effetto del cambiamento di `\minalignsep`.


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

![\ MinalignSep Effect](/tex/images/java/tutorial/latex-ams-math-2-14.png)

Il prossimo esempio illustra un uso molto comune per `alline`. Nota l'uso di `\text` per produrre un testo normale all'interno del materiale matematico.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![L'uso di \ testo](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. Display interruzioni: `\intertesto`

Potresti voler inserire un piccolo pezzo di testo tra le righe di un allineamento del display. Questo viene fatto con il comando `\intertest`. È molto importante che tutte le proprietà di allineamento rimangono inalterate dal testo, mentre il testo stesso è composto come un normale paragrafo impostato sulla larghezza del display. L'allineamento non funzionerà se si termina il display e poi ne avrai uno nuovo dopo il testo. Questo comando deve sempre seguire immediatamente un comando `\\` o `\\*`.


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

![Il comando \ intertest](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> Le parole "e infine" sono fuori dall'allineamento, sul margine sinistro, ma tutte e tre le equazioni sono allineate.

## 2.9. Numerazione equazione e tag

Nel LaTeX, i tag per le equazioni vengono generalmente generati automaticamente e sono essenzialmente una rappresentazione stampata dell'equazione del contatore di LaTeX. Questo viene fatto dal LaTeX in tre passaggi: impostazione del valore del contatore `Equation`; formattare il tag; e stamparlo nella giusta posizione.

I primi due passaggi sono strettamente collegati, poiché il valore del contatore `Equation` viene aumentato solo quando il tag corrispondente viene stampato automaticamente. Diamo un'occhiata a un ambiente di visualizzazione che ha sia forme da recitazione che non installata. Solo la forma non installata modifica il valore del contatore `Equation`, poiché etichetta automaticamente ogni equazione logica mentre la forma stellata non lo fa.

Quando è necessario sopprimere l'impostazione di un tag per una determinata equazione logica all'interno della forma non installata, si è inseriti `\notag` (o`\raccombra`) * prima * il `\\`. È inoltre possibile sostituire i tag predefiniti con quelli del proprio design utilizzando il comando `\tag` prima * il` \\ `. L'argomento di questo comando può essere un testo normale arbitrario che è composto, tra parentesi, come tag per tale equazione.
Si noti che anche l'incremento del valore del contatore viene soppresso quando viene utilizzato `\tag`. Ciò significa che l'impostazione del tag predefinita è visivamente la stessa di `\tag {\ theequation}`; Non sono equivalenti. La forma stellata, `\tag*`, compromette il testo nel suo argomento senza le parentesi (e senza altre cose che altrimenti potrebbero essere aggiunte con una particolare classe di documenti).


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

![\ tag, \ tag*, \ notag, \ etichetta e \ ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Nota come i comandi `\label` e `\ref` vengono utilizzati per fornire una sorta di "numerazione relativa" per le equazioni.

## 2.10. Sequenze di numerazione subordinata

Il pacchetto *amsmath* supporta anche il cosiddetto "sub-numerazione dell'equazione". L'ambiente `Sottocucce` produce tag della forma (2A), (2b), (2C) e così via. Questo schema di numerazione si basa su due contatori di LaTeX normale: `parentequation` ed equazione '. Tutte le equazioni taggate all'interno di un ambiente `Sotterraggi 'usano questo schema.

L'esempio seguente mostra che il tag può essere ridefinito in una certa misura, ma si noti che la ridefinizione per `\Theequation` deve essere inserita nell'ambiente` Sottoquazioni '.


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

> L'ambiente `subequations` deve apparire *all'esterno* delle visualizzazioni su cui agisce. Inoltre, non deve essere annidato in se stesso. Il contatore delle equazioni "principali" viene incrementato a ogni utilizzo di questo ambiente. Un comando `\label` all'interno dell'ambiente `subequations` ma al di fuori di qualsiasi singola equazione (logica) produrrà un `\ref` al numero padre (ad esempio, a 2 anziché a 2i).

## 2.11. Ripristina il contatore dell'equazione

È pratica comune avere equazioni numerate all'interno di sezioni o capitoli con tag della forma (1.1), (1.2), ..., (2.1), (2.2), .... Il pacchetto `amsmath` fornisce un modo semplice per impostare questo con la dichiarazione`\numerwithin`.

Ad esempio, per ottenere tag di equazione incluso il numero di sezione, con il contatore dell'equazione che viene ripristinato automaticamente per ciascuna sezione, mettere questa dichiarazione nel preambolo: `\NumberWithin {Equation} {Sezione}`.

## APPENDICE A. Rendering Equazioni in LaTeX con API ASPOSE.TEX

Ora vedremo il modo in cui l'API Aspose.Tex ti consente di ottenere equazioni in LaTeX come figure autonome.

Diciamo che devi ottenere un'equazione come immagine raster in modo da poterla utilizzare in qualche pubblicazione non TEX (ad esempio una pagina web). Usando l'API Aspose.TeX, puoi farlo come segue:


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

Come puoi vedere, l'API è anche in grado di convertire un'equazione in LaTeX in un file SVG. E questo è stato un esempio di utilizzo di Aspose.TeX per .NET. Di seguito è riportato il codice equivalente per la versione Java.


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

È possibile trovare dettagli sull'uso delle opzioni di rendering nell'articolo su Rendering Latex Math Formules con [Aspose.TeX per .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) o [Aspose.TeX per Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/). Ma uno di questi è importante per noi qui. Utilizzando questa opzione, è possibile specificare il preambolo del documento in LaTeX che dovresti ottenere il risultato desiderato. (Di seguito, presenteremo solo la versione C# del codice sorgente.)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

È inoltre possibile utilizzare questa opzione quando è necessario disporre di un'equazione in un'area più stretta del LaTeX `\textwidth` definisce per impostazione predefinita. Hai due opzioni per raggiungere questo obiettivo:


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Nell'API ASPIPE.TEX, il seguente preambolo viene utilizzato per impostazione predefinita, quindi a meno che non sia necessario passare le opzioni al pacchetto `amsmath` o modificare l'Edefault`\TextWidth` o qualcos'altro, non è necessario specificare il preambolo nelle opzioni di Renderer:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Appendice B. Rendering Equazioni in LaTeX con l'app Web Equation ASPUTI

Esiste anche la [app Web Editor Equation Latex](https://products.aspose.app/tex/equation-editor) che consente di modificare e visualizzare le equazioni in LaTeX. È possibile inserire la tua equazione nel campo di testo e fare clic sul pulsante *View* per visualizzare il risultato. Oppure, è possibile utilizzare il pannello di controllo sopra il campo per creare l'equazione selezionando una categoria di sottoespressione, quindi la sottoespressione e quindi modificando l'argomento, se presente. Puoi trovare il preambolo e altre opzioni sotto il campo *Formula*.