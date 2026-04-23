---
translation: true
template: /templates/_template-java.md
linktitle: Simboli decorati e strutture composte
title: 4. Simboli decorati e strutture composte
weight: 40
url: /java/latex-math-decorations/
keywords: ams-latex, amsmath, amsxtra, integrali in LaTeX, frazioni in LaTeX, decorazioni in LaTeX, frecce in LaTeX, limiti in LaTeX, relazioni modulari in LaTeX
description: Questo articolo descrive una serie di comandi che producono varie strutture matematiche di medie dimensioni utilizzando il pacchetto amsmath.
lastmod: "2026-04-21"
---

{{<section overview>}}

Il pacchetto `amsmath` fornisce alcuni comandi per produrre strutture come frazioni e simboli decorati. In questo articolo ne descriveremo alcuni.


## 4.1. Frazioni generali

Il pacchetto `amsmath` definisce il comando `\genfrac`, che produce una frazione generalizzata.

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

I primi due argomenti definiscono rispettivamente i delimitatori sinistro e destro. Usando il terzo argomento, *thick*, è possibile sovrascrivere lo spessore predefinito della linea di frazione. Ad esempio, i coefficienti binomiali (vedi sotto) usano il valore `0pt` per questo argomento per rendere invisibile la linea. Il valore predefinito (quando lasciato vuoto) dello spessore della linea è determinato dalla configurazione del font corrente per la composizione matematica. Il seguente elenco contiene le impostazioni predefinite utilizzate negli esempi di questo articolo.

| ***Style*** | ***Default Thickness*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

Il quarto argomento, *style*, sostituisce (se non lasciato vuoto) lo stile matematico per il layout e le dimensioni del font utilizzate. Il valore deve essere nell'intervallo 0-3: 0 - `\displaystyle`, 1 - `\textstyle`, 2 - `\scriptstyle`, 3 - `\scriptscriptstyle`. Se questo argomento viene lasciato vuoto, lo stile viene selezionato in base alle normali regole per le frazioni. Gli ultimi due argomenti sono il numeratore e il denominatore.

> I vecchi comandi di frazione `\over`, `\overwithdelims`, `\atop`, `\atopwithdelims`, `\above` e `\abovewithdelims`, che il LaTeX standard eredita da TeX, generano avvisi quando vengono utilizzati con il pacchetto `amsmath`.

### 4.1.1. Frazioni semplici

Disponendo del comando `\genfrac`, il pacchetto `amsmath` definisce anche tre comandi come comode scorciatoie: `\frac`, `\dfrac` e `\tfrac`.

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

L'esempio seguente dimostra l'uso di questi comandi:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\frac, \dfrac e \tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. Coefficienti binomiali

Un'altra struttura simile a una frazione sono i coefficienti binomiali. Per aiutarvi a comporli, il pacchetto `amsmath` fornisce comandi simili come `\binom`, `\dbinom` e `\tbinom`.

Ecco come abbreviano il comando `\genfrac`:

```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

Ed ecco l'esempio:

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\binom, \dbinom e \tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. Frazioni continue

Se è necessario comporre una serie di frazioni, che è essenzialmente una frazione infinita, nota anche come "frazione continua", esiste il comando `\cFrac` nel pacchetto `amsmath`. È possibile passare l'argomento opzionale `[l]` o `[r]` per allineare un numeratore a sinistra o a destra (è centrato per impostazione predefinita).

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![Una frazione continua](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. Matematica in un riquadro

Il pacchetto `amsmath` fornisce il comando `\boxed` simile a `\fbox` per inserire il contenuto della modalità matematica in un riquadro.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![Una formula in un riquadro](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. Posizionamento dei limiti

Pedici e apici su integrali, somme, prodotti o altri operatori possono essere posizionati sopra e sotto l'operatore matematico (la "posizione del limite") o nella posizione di pedice/apice alla destra dell'operatore. In genere, i limiti non vengono utilizzati nel testo (altrimenti le righe potrebbero allargarsi). In una formula visualizzata, il posizionamento dipende dall'operatore. L'esempio seguente mostra il posizionamento predefinito in LaTeX.

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![Il posizionamento predefinito di pedici/apici in LaTeX](/tex/images/java/tutorial/latex-ams-math-4-5.png)

Il pacchetto `amsmath` offre opzioni per il controllo del posizionamento. Sono elencate di seguito, dove *predefinito* indica il comportamento nel caso in cui il pacchetto `amsmath` sia utilizzato con una classe di documenti LaTeX standard ma senza nessuna di queste opzioni.

|||
|:---:|---|
| `intlimits`, `nointlimits` | Posiziona gli apici/pedici dei simboli di integrazione rispettivamente sopra e sotto oppure lateralmente (impostazione predefinita). Utilizzato solo nelle formule visualizzate. |
| `sumlimits`, `nosumlimits` | Posiziona gli apici/pedici degli *operatori di grandi dimensioni* (somma, prodotto, ecc.) rispettivamente sopra e sotto (impostazione predefinita) oppure lateralmente. Utilizzato solo nelle formule visualizzate. |
| `namelimits`, `nonamelimits` | Simile a `sumlimits` o `nosumlimits`, ma per alcuni operatori, o "nomi di operatore", come `inf`, `sup`, `lim`, `min`, `max`, che tradizionalmente sono composti con pedici sottostanti, almeno quando compaiono in una formula visualizzata. |

TeX ha tre comandi primitivi che, se compaiono immediatamente dopo il simbolo o il nome dell'operatore, controllano il posizionamento dei pedici/apici: `\limits`, `\nolimits` e `\displaylimits`. Il comando `\displaylimits` produce pedici/apici in posizione di limite quando lo stile matematico corrente è uno stile di visualizzazione. Questo è il comportamento predefinito ogni volta che appare un simbolo dell'operatore di classe *Operator* o viene utilizzato un comando `\mathop`. Se è necessario comporre un operatore con pedici/apici in posizione di limite al di fuori di un display, è necessario dichiararlo individualmente utilizzando il comando `\limits`.

Confrontate il seguente esempio con quello precedente.

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Controllo del posizionamento di pedici/apici con le primitive TeX](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. Integrali multipli

Per scrivere più segni integrali con spazi ben adattati tra loro sia nel testo che nei display, utilizzate i comandi `\iint`, `\iiint` e `\iiiint`. Il comando `\idotsint` produce due segni integrali con puntini di sospensione tra loro.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![Integrali multipli](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. Relazioni modulari

La notazione "mod" per le classi di equivalenza di numeri interi è regolata da speciali convenzioni di spaziatura. Per gestirla, il pacchetto `amsmath` offre i comandi `\mod`, `\bmod`, `\pmod` e `\pod`. Il seguente esempio mostra l'uso di questi comandi.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
Il layout nel testo: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![Relazione modulare](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> Con `amsmath`, la spaziatura di `\pmod` viene ridotta all'interno di una formula non visualizzata.

## 4.5. Accenti matematici a punti

Oltre agli accenti matematici `\dot` e `\ddot`, il pacchetto `amsmath` fornisce i comandi `\dddot` e `\ddddot`, che producono rispettivamente accenti a triplo e quadruplo punto.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![Accenti a punti](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. Creazione di apici dagli accenti: il pacchetto `amsxtra`

Il pacchetto `amsxtra` offre una funzione utile, una raccolta di semplici comandi per posizionare accenti come apici per le sottoformule:

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![Accenti come apici](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. Altre decorazioni

Il LaTeX standard ha il comando `\stackrel` che pone un apice sopra un simbolo di *relazione*. Inoltre, il pacchetto `amsmath` definisce i comandi `\overset` e `\underset`. Utilizzateli per posizionare materiale sopra o sotto qualsiasi simbolo *Ordinary* o *Relation* o *Binary operator*.

Il comando `\sideset` aggiunge decorazioni a qualsiasi simbolo *operatore* (somma, prodotto, ecc.) in aggiunta ai limiti normali. Queste sono inserite nelle posizioni di pedice e apice a sinistra e a destra dell'operatore.

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![Più decorazioni](/tex/images/java/tutorial/latex-ams-math-4-11.png)