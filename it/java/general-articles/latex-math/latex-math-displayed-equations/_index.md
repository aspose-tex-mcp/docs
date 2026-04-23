---
translation: true
template: /templates/_template-java.md
linktitle: Equazioni visualizzate
title: 9. Equazioni visualizzate 
weight: 90
url: /java/latex-math-displayed-equations/
keywords: Formule di matematica in LaTeX, LaTeX, matematica in LaTeX, formula di matematica in LaTeX, LaTeX matematica mostrata equazione, array di equazioni di matematica in LaTeX, allineamento della matematica in LaTeX
description: Scopri il modo di visualizzare formule matematiche di grandi dimensioni o una grande quantità di formule utilizzando i comandi forniti dal LaTeX.
lastmod: "2026-04-21"
---

{{<section overview>}}

Ormai abbiamo discusso di come affrontare le singole formule; Ma i display coinvolgono spesso un sacco di formule diverse o pezzi diversi di una formula enorme, e può essere una sfida per espanderli in modo che si allineino correttamente tra loro. Fortunatamente, i display di grandi dimensioni generalmente cadono in alcuni semplici motivi.

### 9.1. Display a una linea

Le equazioni visualizzate spesso contengono un testo ordinario. Abbiamo già [discusso](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters) come ottenere il tipo romano in formule senza lasciare la modalità matematica, ma il modo migliore per ottenere il testo in un display è metterlo in un `\hbox`. In realtà non c'è nemmeno alcuna matematica. Per digitare il set

![Testo visualizzato senza matematica](/tex/images/java/tutorial/latex-math-9-1.png)

Puoi dire `$$ \ hbox {Testo visualizzato} $$`. Ma ecco un esempio più interessante:

![Testo in un display matematico](/tex/images/java/tutorial/latex-math-9-2.png)

In questo caso, formule e testo sono stati combinati come segue:


```tex
$$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$$
```

Come puoi vedere, `\qquad` appare intorno a" se e solo se ", ma un singolo`\quad` circonda "e"; Ciò crea un accento sul fatto che le parti *y* e *z* del display sono correlate più da vicino l'una all'altra che alla parte *x*. 

Diamo un'occhiata al seguente display:

![Testo in un display matematico](/tex/images/java/tutorial/latex-math-9-3.png)

Un modo in cui può essere specificato è


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$$
```

Ma il modo migliore sarebbe (vedi la seconda riga)


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$$
```

Sì, questa è la modalità matematica all'interno della modalità orizzontale all'interno della modalità matematica del display, ma questa soluzione sembra più naturale della prima.

Ora passiamo ai numeri dell'equazione, quelle piccole etichette che appaiono sul lato dei display. Se digiti


```tex
$$<formula>\eqno<formula>$$
```

Tex mostrerà la prima formula e metterà anche un numero di equazione (la seconda formula) al margine di destra. Per esempio,


```tex
$$x^2-y^2 = (x+y)(x-y).\eqno(15)$$
```

produrrà

![Numeri di equazione a destra](/tex/images/java/tutorial/latex-math-9-4.png)

Puoi anche ottenere numeri di equazione al margine di sinistra usando `\leqno`. Per esempio,

```tex
$$x^2-y^2 = (x+y)(x-y).\leqno(15)$$
```

produrrà

![Numeri di equazione a sinistra](/tex/images/java/tutorial/latex-math-9-5.png)

Si noti che dà sempre il numero di equazione secondo, anche quando apparirà a sinistra.

Le equazioni visualizzate sono centrate indipendentemente dalla presenza dei numeri di equazione. Ma quando una formula è grande, Tex si assicura che non interferisca con il suo numero; Il numero di equazione può anche essere posizionato su una linea da solo.

LaTex fornisce anche l'ambiente di equazione per numerare automaticamente le equazioni. Ad esempio, digitazione

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

si traduce

![L'uso dell'ambiente di equazione](/tex/images/java/tutorial/latex-math-9-6.png)

È anche possibile etichettare e fare riferimento alle equazioni usando `\etichetta` e `\ref`. Per esempio,

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
questo fa riferimento all'equazione \ref{eq:someequation}.
```

si traduce

![L'uso dell'ambiente di equazione con un'etichetta e un riferimento](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. Display multilinea

A volte un display potrebbe non adattarsi al modello semplice di una formula a una riga con o senza un numero di equazione. Latex fornisce comandi speciali per la maggior parte dei casi rimanenti.

I display multi-line di solito includono diverse equazioni che dovrebbero essere allineate dai loro segni '=', come in

![Un componente di equazione multilinea con l'ambiente dell'array](/tex/images/java/tutorial/latex-math-9-8.png)

Il metodo consigliato per tale display consiste nell'utilizzare l'ambiente `Array` fornito dal LaTeX:

```tex
$$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$$
```

Questo ambiente ti aiuta a rappresentare le tue equazioni come un array rettangolare multi-colonna (due colonne). Le righe contengono singole equazioni separate dal comando `\\` (che è una nuova linea). I lati a sinistra e destra di ciascuna equazione sono separati dal simbolo `&`. Non è necessario che l'ultima riga finisca con `\\`. L'ambiente ha anche un argomento che specifica l'allineamento in ciascuna colonna. Nell'esempio, il valore appropriato è `rl`, il che significa che i lati a sinistra delle equazioni usciranno a filo a destra, mentre i lati a destra usciranno a filo a sinistra.

Il LaTeX fornisce anche l'ambiente `eqnarray` che funziona in modo simile, ma per avere entrambi i lati delle equazioni allineata correttamente ha bisogno di due punti di allineamento e, sfortunatamente, la spaziatura diventa un po 'fuori dalle convenzioni di digitazione matematica. Il seguente codice

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

produce il seguente output:

![Un componente di equazione multilinea con l'ambiente eqnarray*](/tex/images/java/tutorial/latex-math-9-9.png)

L'ambiente `eqnarray` di LaTex produce lo stesso risultato, tranne per il fatto che numera automaticamente le equazioni.

Ci possono essere un numero qualsiasi di equazioni in un ambiente `array`; Il modello generale è

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  ...
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

dove ogni `<lato destro>` inizia con il simbolo su cui si desidera che si verifichi l'allineamento.

Il risultato dell'ambiente `Array` è una scatola centrata in verticale. Questo rende facile ottenere una formula come

![Due gruppi di equazioni in un display](/tex/images/java/tutorial/latex-math-9-10.png)

Si utilizza semplicemente l'ambiente `array` due volte nella linea:

```tex
$$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$$
```

Il livello successivo di complessità si verifica quando si dispone di diverse equazioni allineate con diversi numeri di equazione. O alcune linee possono essere numerate e altre no:

![Array di equazioni numerato arbitrariamente con tag a destra](/tex/images/java/tutorial/latex-math-9-11.png)

Sfortunatamente, anche con l'ambiente `eqnarray` (con la sua spaziatura impropria) non c'è modo di specificare manualmente i numeri di equazione in un display multi-line. Solo il pacchetto 'amsmath' può 
aiuto. Quindi, il modo consigliato per ottenere il risultato di cui sopra è digitare:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

Se ometti sia `\tag` che`\notag` su una riga dell'ambiente `allinea ', il numero di equazione verrà generato automaticamente utilizzando il valore corrente memorizzato nel contatore interno corrispondente.

Se si carica il pacchetto `amsmath` con l'opzione` leqno`, i numeri di equazione appariranno al margine sinistro. Così

```tex
%% Preamble
\usepackage[leqno]{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```
produce

![Array di equazioni numerato arbitrariamente con tag a sinistra](/tex/images/java/tutorial/latex-math-9-12.png)

Per saperne di più sulle formule di matematica di composizione utilizzando le funzionalità del pacchetto `amsmath`, consultare questi [articoli](/tex/{{lang.url-fragment}}java/what-is-ams-latex/).

### 9.3. Formule lunghe

Ora discutiamo di cosa si dovrebbe fare quando una formula è così lunga che non si adatta a una singola riga. Ad esempio, supponiamo di incontrare l'equazione

![Formula lunga ridotta che rende la linea eccessiva](/tex/images/java/tutorial/latex-math-9-13.png)

Dovrai romperlo in qualche modo; Tex ha fatto del suo meglio per spremere tutto insieme riducendo gli spazi accanto a "+" e "-segni a zero, ma la linea è ancora uscita in modo eccessivo.

Proviamo a rompere quell'equazione appena prima del '+7'. L'ambiente `Array` lascia troppo spazio a destra di '=' Se lo usi allo stesso modo delle equazioni multilinea:

```tex
$$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$$
```

Quindi, è meglio ricorrere al pacchetto `amsmath`. Ma questa volta dovresti usare l'array `allinea*` poiché i numeri di equazione non sono necessari:

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$$
```

Questo produce

![Formula lunga rotta usando l'ambiente allineato*](/tex/images/java/tutorial/latex-math-9-14.png)

L'idea è quella di trattare una lunga formula a una linea come una formula a due righe, usando `\Qquad` sulla seconda riga in modo che la seconda parte della formula appaia bene a destra del segno '=' sulla prima riga.
In realtà non è un compito facile decidere come rompere le formule visualizzate a lungo in linee; Tex non tenta mai di farlo, perché nessuna serie di regole è davvero adeguata. L'autore di un manoscritto matematico è generalmente il miglior giudice di cosa fare, poiché le posizioni di rottura dipendono da sottili fattori di esposizioni matematiche. Ad esempio, è spesso auspicabile enfatizzare parte della simmetria o di altra struttura che sta alla base della formula e tali cose richiedono una solida comprensione di ciò che sta accadendo esattamente in quella formula.

Tuttavia, è possibile dichiarare alcune regole empiriche su come gestire lunghe formule nei display, poiché ci sono alcuni principi che il miglior composizione matematica tende a seguire:

a) Sebbene le formule all'interno di un paragrafo si rompano sempre * dopo * operazioni e relazioni binarie, le formule visualizzate si rompono sempre * prima delle operazioni e delle relazioni binarie. Ecco perché non abbiamo terminato la prima riga del nostro esempio precedente con `(2^{34} -1)+`; L'abbiamo concluso con `(2^{34} -1` e abbiamo iniziato la seconda riga con`+`.

b) Quando un'equazione viene rotta prima di un'operazione binaria, la seconda riga dovrebbe iniziare almeno due quad a destra di dove la sottomissione più interna contenente quell'operazione binaria inizia sulla prima riga. Ad esempio, se desideri rompere

```tex
$$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$$
```

Nel segno più tra `<formula_1>` e` <mula_2> `, è quasi obbligatorio avere il segno più sulla seconda riga apparire in qualche modo a destra della grande parentesi sinistra che corrisponde a`\a sinistra (`.

Nell'esempio appena considerato, è necessaria una cura speciale per rompere la formula in due righe, perché i delimitatori `\sinistra` e `\a destra non possono essere usati in isolamento: non si può avere solo `\sinistra` in una riga di una formula e solo`\a destra 'nel secondo. Inoltre, vorrai che i due delimitatori siano della stessa dimensione, anche se si verificano in linee diverse. La soluzione migliore è di solito scegliere tu stesso la dimensione delimitante; Ad esempio, potresti digitare

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

Se i delimitatori `\bigg` sono i migliori. Si noti che i marcatori `&` non si verificano a segni `=` in questo esempio, segnano solo un punto di allineamento.

C'è un altro modo per rompere lunghe formule, a volte chiamata forma * a due righe *. L'idea è quella di mettere la prima parte della formula quasi a filo a sinistra e di mettere la seconda parte quasi a filo a destra, dove "quasi a filo" significa "un quad di distanza". Pertanto, la forma a due righe di un'equazione Sigma lunga considerata prima è

![Forma a due righe di un'equazione](/tex/images/java/tutorial/latex-math-9-15.png)

Per ottenere questo effetto a due righe, basta digitare:

```tex
$$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$$
```

Un ulteriore `{}` è stato digitato sulla seconda riga qui in modo che Tex sapesse che `+` è un'operazione binaria. La forma a due righe è particolarmente raccomandata per le equazioni che hanno un lungo lato sinistro; In tal caso l'interruzione si avvicina generalmente poco prima del segno =.