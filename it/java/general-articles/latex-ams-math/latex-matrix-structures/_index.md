---
translation: true
template: /templates/_template-java.md
linktitle: Matrice e ambienti simili
title: 3. Matrix e ambienti simili | Manuale in LaTeX
weight: 30
url: /java/latex-ams-matrix/
keywords: AMS-Latex, Amsmath, AMSCD, Matrix in LaTeX, Caso in LaTeX, Delarray in LaTeX, Diagrammi di commutazione in LaTeX
description: Questo articolo fornisce una breve introduzione alle strutture simili a matrice in LaTeX che utilizzano pacchetti AMS-Latex.
lastmod: "2025-06-13"
---

{{<section overview>}}

Esistono numerosi ambienti per le strutture simili a matrice di composizione definite nel pacchetto `amsmath`. Sono tutti simili all'ambiente standard in LaTeX `array` in sintassi e layout. In generale, un'ampia varietà di strutture matematiche bidimensionali e layout tabulari possono essere descritti come array.

Tre ambienti - `casi`,` matrix` e `pmatrix` - Sostituire i comandi del LaTeX standard. I comandi standard utilizzano una notazione diversa in modo da non poter essere utilizzati insieme ai moduli ambientali discussi qui. Il pacchetto `amsmath` produrrà un messaggio di errore se viene utilizzato uno dei vecchi comandi. Al contrario, se si tenta di utilizzare i moduli ambientali `amsmath` senza caricare il pacchetto, molto probabilmente riceverai il seguente messaggio di errore:` "Carattero della scheda di allineamento fuori posto e" `.


## 3.1. L'ambiente "casi"

L'ambiente `Case` viene utilizzato per gestire le costruzioni, in cui una singola equazione ha alcune varianti. Tali costruzioni sono molto comuni in matematica. Produce un array con due colonne, entrambe allineate a sinistra.


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

Notare l'uso del comando `\text` e della" modalità matematica incorporata "nelle stringhe di testo.

## 3.2. Gli ambienti di matrice

Gli ambienti di matrice, a differenza del "array" di LaTe, non accettano un argomento che specifica i formati delle colonne. Invece, forniscono un formato predefinito: fino a 10 colonne centrate. La spaziatura differisce anche leggermente dal valore predefinito in "Array". I seguenti esempi illustrano gli ambienti `matrix`,` pmatrix`, `bmatrix`,` bmatrix`, `vmatrix` e ` vmatrix`.


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

Il contatore `maxmatrixcols` determina il numero massimo di colonne in un ambiente a matrice. È possibile modificarlo usando il comando standard di LaTex. Il valore del parametro di lunghezza `\ArrayColsep` determina la quantità di spazio tra le colonne. Proprio come negli array standard, ma non viene aggiunto spazio su entrambi i lati dell'array. Altre colonne renderà il LaTeX di lavoro più difficile e richiede più risorse. Tuttavia, è possibile l'impostazione di "maxmatrixcols" a 20 o superiore senza un notevole successo delle prestazioni, poiché con le tipiche implementazioni di oggi tali limiti sono meno importanti.


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

In questo esempio il comando `\hdotsfor` viene utilizzato per produrre una riga di punti in una matrice, che copre un determinato numero di colonne. Il parametro opzionale (qui 2) può essere utilizzato per specificare un moltiplicatore per lo spazio predefinito (3 unità matematiche) tra i punti. Lo spazio sottile e il gruppo Brace `\, {}` Alla fine di ogni riga semplicemente rendono il layout migliore; Insieme producono due spazi sottili, circa 6MU o 1/3EM.

Per produrre una piccola matrice inline per l'uso nel testo, è possibile utilizzare l'ambiente "Smallmatrix".


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

Si noti che le righe di testo non sono sparse anche se la linea prima della piccola matrice contiene lettere con discendenti.

## 3.3. Impilamento in abbonamenti e rivestimenti

A volte potrebbe essere necessario compromettere diverse righe all'interno di un pedice o apice. Per fare ciò, puoi usare il comando `\Scadack` con righe di delimitazione di` \\ `.

L'ambiente "Subarray" è una struttura leggermente più generale che ti consente di allineare le linee a sinistra o a destra, piuttosto che centrali.


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

![Impilamento in sotto-e apice](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> Si noti che entrambi gli ambienti devono essere racchiusi tra parentesi graffe quando appaiono come apice o pedice.

## 3.4. Diagrammi commutativi

Il pacchetto `Amscd` definisce alcuni comandi per la produzione di semplici diagrammi commutativi basati su array. Esistono alcune utili forme di stenografia per specificare frecce decorate e altri connettori. Tuttavia, ha limitazioni, ad esempio, questi connettori possono essere solo orizzontali o verticali.

Nell'ambiente `CD`, le notazioni`@>>> ``@<<< `,`@vvv` `e@@aaa` producono rispettivamente a destra, a sinistra, giù e in alto. L'esempio seguente mostra anche l'uso del comando `\dichiarathoperator`.


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

Vediamo come vengono specificate le decorazioni. Per le frecce orizzontali, il materiale tra il primo e il secondo simboli `` `` o `<` saranno composti come appescrive e il materiale tra il secondo e il terzo verrà composto come un pedice. Allo stesso modo, il materiale tra il primo e il secondo, o il secondo e il terzo, `a` o` V` di frecce verticali sarà composto come sinistro o destro "sceneggiatura laterale". Vedremo l'uso di questo formato nel prossimo esempio.

Le notazioni `@=` e `@|` Dai doppie linee orizzontali e verticali.

Invece di una freccia visibile, puoi usare una "freccia nulla" (`@.`) per compilare un array dove necessario.


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

Un layout simile può essere prodotto nel LaTeX standard. Ma non sembra buono.


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Diagramma commutativo nel LaTeX standard](/tex/images/java/tutorial/latex-ams-math-3-8.png)

Questo esempio mostra abbastanza chiaramente quanto meglio risultati produce il pacchetto `Amscd`: la notazione è più semplice, le frecce orizzontali sono più lunghe, la spaziatura tra gli elementi è molto migliorata. I pacchetti più specializzati ti aiuteranno a ottenere risultati ancora più belli.

## 3.5. Delimitatori che circondano un array: il pacchetto `Delarray`

In questa sezione, discuteremo di un'utile estensione generale al pacchetto `Array`. Utilizzando questa estensione, l'utente può specificare l'apertura e la chiusura dei delimitatori estensibili per circondare un ambiente di matematica "Array". Diamo un'occhiata all'esempio:


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

> Si noti che il pacchetto `delarray` è indipendente da `amsmath` ma carica automaticamente il pacchetto `array` se necessario.

I delimitatori sono posizionati su entrambi i lati di `{cc}`.

Questo esempio illustra anche la caratteristica più utile del pacchetto `Delarray`: l'uso degli argomenti opzionali` [t] `e` [b] `, che non sono consentiti con gli ambienti a matrice di` Amsmath`. Questi mostrano che l'uso della sintassi di `Delarray` non è equivalente all'ambiente circostante con`\left` e `\a destra`, poiché i delimitatori sono sollevati e l'array stesso.