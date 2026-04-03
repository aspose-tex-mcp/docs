---
translation: true
template: /templates/_template-java.md
linktitle: Matrici e ambienti simili
title: 3. Matrici e ambienti simili
weight: 30
url: /java/latex-ams-matrix/
keywords: ams-latex, amsmath, amscd, matrici LaTeX, casi LaTeX, delarray LaTeX, diagrammi commutativi LaTeX
description: Questo articolo fornisce una breve introduzione alla composizione di strutture simili a matrici in LaTeX utilizzando i pacchetti AMS-LaTeX.
lastmod: "2026-03-30"
---

{{<section overview>}}

Esistono numerosi ambienti per la composizione di strutture simili a matrici definiti nel pacchetto `amsmath`. Sono tutti simili all'ambiente standard di LaTeX `array` per sintassi e layout. In generale, un'ampia varietà di strutture matematiche bidimensionali e layout tabulari può essere descritta come array.

Tre ambienti — `cases`, `matrix` e `pmatrix` — sostituiscono i comandi del LaTeX standard. I comandi standard utilizzano una notazione diversa, quindi non possono essere utilizzati insieme agli ambienti discussi qui. Il pacchetto `amsmath` produrrà un messaggio di errore se viene utilizzato uno dei vecchi comandi. Al contrario, se si tenta di utilizzare gli ambienti di `amsmath` senza caricare il pacchetto, molto probabilmente si riceverà il seguente messaggio di errore: `"Misplaced alignment tab character &"`.


## 3.1. L'ambiente "cases"

L'ambiente `cases` viene utilizzato per gestire costruzioni in cui una singola equazione presenta diverse varianti. Tali costruzioni sono molto comuni in matematica. Produce un array con due colonne, entrambe allineate a sinistra.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Ambiente dei casi](/tex/images/java/tutorial/latex-ams-math-3-1.png)

Notate l'uso del comando `\text` e della "modalità matematica incorporata" nelle stringhe di testo.

## 3.2. Gli ambienti di matrice

Gli ambienti di matrice, a differenza dell'`array` di LaTeX, non accettano un argomento che specifichi il formato delle colonne. Forniscono invece un formato predefinito: fino a 10 colonne centrate. Anche la spaziatura differisce leggermente dal valore predefinito in `array`. I seguenti esempi illustrano gli ambienti `matrix`, `pmatrix`, `bmatrix`, `Bmatrix`, `vmatrix` e `Vmatrix`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Ambienti a matrice](/tex/images/java/tutorial/latex-ams-math-3-2.png)

Il contatore `MaxMatrixCols` determina il numero massimo di colonne in un ambiente di matrice. È possibile modificarlo usando il comando standard di LaTeX. Il valore del parametro di lunghezza `\arraycolsep` determina la quantità di spazio tra le colonne. Proprio come negli array standard, non viene aggiunto spazio su entrambi i lati dell'array. Un numero maggiore di colonne renderà il lavoro di LaTeX più oneroso e richiederà più risorse. Tuttavia, è possibile impostare `MaxMatrixCols` a 20 o superiore senza un notevole calo delle prestazioni, poiché con le tipiche implementazioni odierne di TeX tali limiti sono meno rilevanti.


```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![Altre colonne in ambienti a matrice](/tex/images/java/tutorial/latex-ams-math-3-3.png)

In questo esempio il comando `\hdotsfor` viene utilizzato per produrre una riga di puntini in una matrice, estendendosi su un determinato numero di colonne. Il parametro opzionale (qui 2) può essere utilizzato per specificare un moltiplicatore per lo spazio predefinito (3 unità matematiche) tra i puntini. Lo spazio sottile e il gruppo di graffe `\, {}` alla fine di ogni riga migliorano semplicemente il layout; insieme producono due spazi sottili, circa 6mu o 1/3em.

Per produrre una piccola matrice inline nel testo, è possibile utilizzare l'ambiente `smallmatrix`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![L'ambiente Smallmatrix](/tex/images/java/tutorial/latex-ams-math-3-4.png)

Si noti che le righe di testo non vengono distanziate ulteriormente, anche se la riga precedente la piccola matrice contiene lettere con tratti discendenti.

## 3.3. Impilamento in pedici e apici

A volte potrebbe essere necessario comporre diverse righe all'interno di un pedice o di un apice. Per fare ciò, si può usare il comando `\substack` con `\\` come delimitatore di riga.

L'ambiente `subarray` è una struttura leggermente più generale che consente di allineare le righe a sinistra o a destra, anziché centrarle.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Impilamento in pedici e apici](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> Si noti che entrambi gli ambienti devono essere racchiusi tra parentesi graffe quando appaiono come apice o pedice.

## 3.4. Diagrammi commutativi

Il pacchetto `amscd` definisce alcuni comandi per la produzione di semplici diagrammi commutativi basati su array. Esistono alcune utili forme abbreviate (shorthand) per specificare frecce decorate e altri connettori. Tuttavia, presenta delle limitazioni: ad esempio, questi connettori possono essere solo orizzontali o verticali.

Nell'ambiente `CD`, le notazioni `@>>>`, `@<<<`, `@VVV` e `@AAA` producono rispettivamente frecce verso destra, sinistra, il basso e l'alto. L'esempio seguente mostra anche l'uso del comando `\DeclareMathOperator`.


```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Diagramma commutativo semplice](/tex/images/java/tutorial/latex-ams-math-3-6.png)

Vediamo come vengono specificate le decorazioni. Per le frecce orizzontali, il materiale tra il primo e il secondo simbolo `>` o `<` sarà composto come apice, mentre quello tra il secondo e il terzo come pedice. Allo stesso modo, il materiale tra il primo e il secondo, o tra il secondo e il terzo, `A` o `V` delle frecce verticali sarà composto come "side-script" a sinistra o a destra. Vedremo l'uso di questo formato nel prossimo esempio.

Le notazioni `@=` e `@|` producono doppie linee orizzontali e verticali.

Invece di una freccia visibile, si può usare una "freccia nulla" (`@.`) per riempire l'array dove necessario.


```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]
```

![Diagramma commutativo con script](/tex/images/java/tutorial/latex-ams-math-3-7.png)

Un layout simile può essere prodotto nel LaTeX standard, ma il risultato non è altrettanto buono.


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Diagramma commutativo nel LaTeX standard](/tex/images/java/tutorial/latex-ams-math-3-8.png)

Questo esempio mostra chiaramente quanto siano migliori i risultati prodotti dal pacchetto `amscd`: la notazione è più semplice, le frecce orizzontali sono più lunghe, la spaziatura tra gli elementi è notevolmente migliorata. Pacchetti più specializzati aiuteranno a ottenere risultati ancora più belli.

## 3.5. Delimitatori che circondano un array: il pacchetto delarray

In questa sezione discuteremo di un'utile estensione generale del pacchetto `array`. Utilizzando questa estensione, l'utente può specificare delimitatori estensibili di apertura e chiusura per circondare un ambiente `array` in modalità matematica. Vediamo l'esempio:


```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![L'uso del pacchetto Delarray](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> Si noti che il pacchetto `delarray` è indipendente da `amsmath`, ma carica automaticamente il pacchetto `array` se necessario.

I delimitatori sono posizionati su entrambi i lati di `{cc}`.

Questo esempio illustra anche la caratteristica più utile del pacchetto `delarray`: l'uso degli argomenti opzionali `[t]` e `[b]`, che non sono consentiti con gli ambienti di matrice di `amsmath`. Questi mostrano che l'uso della sintassi di `delarray` non è equivalente al circondare l'ambiente `array` con `\left` e `\right`, poiché i delimitatori vengono sollevati insieme all'array stesso.