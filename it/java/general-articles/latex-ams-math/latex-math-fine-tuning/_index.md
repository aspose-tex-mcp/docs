---
translation: true
template: /templates/_template-java.md
linktitle: Regolazioni precise del layout
title: 7. Regolazioni precise del layout
weight: 70
url: /java/latex-math-fine-tuning/
keywords: ams-latex, amsmath, spaziatura matematica LaTeX, stili matematici LaTeX, delimitatori matematici in LaTeX, parentesi matematiche in LaTeX, allineamento matematico in LaTeX
description: "Questo articolo discute la regolazione fine del layout matematico - dimensionamento e spaziatura automatici, delimitatori grandi, allineamento preciso."
lastmod: "2026-03-30"
---

{{<section overview>}}

Di solito, LaTeX fa un ottimo lavoro nel presentare le formule matematiche. Ma a volte è necessaria una regolazione più fine del posizionamento. In questo articolo discuteremo alcune tecniche per mettere a punto il layout per migliorare le formule matematiche.

## 7.1. Dimensionamento e spaziatura automatici

I simboli e le lettere matematiche generalmente diventano più piccoli (e con una spaziatura più stretta) quando compaiono in frazioni, pedici o apici. Le formule matematiche possono essere disposte in otto stili matematici TeX:

||||
|---|---|---|
| *D, D'* | `\displaystyle`| Visualizzato su una riga a sé stante |
| *T, T'* | `\textstyle`| Inserito nel testo |
| *S, S'* | `\scriptstyle`| In apici o pedici |
| *SS, SS'* | `\scriptscriptstyle`| In tutti gli apici o pedici di ordine superiore |

Lo stile di testo (*T*) è usato al livello superiore di una formula inserita nel testo (tra una coppia di `$` o tra `\(` e `\)`), mentre lo stile di visualizzazione viene usato al livello superiore di una formula visualizzata (tra una coppia di `$$` o tra `\[` e `\]`). Per quanto riguarda le sottoformule, lo stile può essere determinato dalla seguente tabella:

||||||
|---|---|---|---|---|
| *D* | *S* | *S'* | *T* | *T'* |
| *D'* | *S'* | *S'* | *T'* | *T'* |
| *T* | *S* | *S'* | *S* | *S'* |
| *T'* | *S'* | *S'* | *S'* | *S'* |
| *S, SS* | *SS* | *SS'* | *SS* | *SS'* |
| *S', SS'* | *SS'* | *SS'* | *SS'* | *SS'* |

Il prossimo esempio illustra i vari stili:

```tex
\normalsize                 %% Style:
\[ b                        %% D
    ^0                      %% S
   +                        %% D
   \frac{(k + p)            %% T
          _{j'}             %% S'
         % \displaystyle
         \pm                %% T [D]
         \frac{(f + q)      %% S [T]
                ^{(pk)      %% SS [S]
                   ^y       %% SS
                   _{j'}}}  %% SS'
              {(h + y)}}    %% S' [T']
        {(l + q)            %% T'
          ^{(pk)}}          %% S'
\]
```

![Vari stili di matematica](/tex/images/java/tutorial/latex-ams-math-7-1.png)

Potete rimuovere il carattere di commento (`%`) prima di `\displaystyle` e vedere come alcuni degli stili sono cambiati in quelli tra parentesi:

![Stili di matematica esplicitamente cambiati](/tex/images/java/tutorial/latex-ams-math-7-2.png)

Mostra come specificare esplicitamente lo stile da utilizzare in ciascuna parte.

## 7.2. Sottoformule

Nel testo, una coppia di graffe indica un gruppo o un ambito, all'interno del quale è in vigore una dichiarazione. All'interno di una formula matematica, esse delimitano inoltre una sottoformula, che è sempre composta come un'entità separata aggiunta alla formula esterna. Di conseguenza, le sottoformule sono sempre composte alla loro larghezza naturale e non si allungano o si restringono orizzontalmente quando TeX costruisce un paragrafo cercando di adattare la formula in una riga. Abbiamo già dimostrato che la sottoformula da un semplice gruppo di graffe viene elaborata come se fosse un singolo simbolo. Ciò significa che un gruppo vuoto produce un simbolo invisibile che può cambiare la spaziatura.

I contenuti di pedici/apici e gli argomenti di molti (ma non tutti) comandi, come `\frac` e `\mathrel`, sono anch'essi sottoformule. Pertanto, ricevono lo stesso trattamento speciale. L'argomento di `\bm`, ad esempio, non è necessariamente impostato come sottoformula, e questa è una delle eccezioni importanti. In una formula matematica, se è necessario solo limitare l'ambito di una dichiarazione, definite un gruppo usando `\begingroup` e `\endgroup`. Ricordate che le dichiarazioni matematiche specializzate, come i cambiamenti di stile, si applicano fino alla fine della sottoformula corrente, indipendentemente dal fatto che siano presenti altri gruppi.

## 7.3. Delimitatori grandi

LaTeX definisce quattro comandi — `\big`, `\Big`, `\bigg` e `\Bigg` — per fornire il controllo diretto delle dimensioni dei delimitatori estensibili. Accettano un singolo argomento, che deve essere un delimitatore estensibile, e producono versioni più grandi del delimitatore, da 1,2 a 3 volte la dimensione di base.

Ci sono anche tre varianti per ciascuno dei quattro comandi, dando quattro dimensioni di *simbolo di apertura* (`\bigl`, `\Bigl`, `\biggl` e `\Biggl`); quattro dimensioni di *simbolo di relazione* (`\bigm`, `\Bigm`, `\biggm` e `\Biggm`); e quattro dimensioni di *simbolo di chiusura* (`\bigr`, `\Bigr`, `\biggr` e `\Biggr`). Tutti i 16 di questi comandi devono essere usati con qualsiasi simbolo che può venire dopo `\left`, `\right` o (con eTeX) `\middle` (vedere questa [tabella](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols#53-symbols-that-are-vertically-extensible)). 

Le dimensioni di questi delimitatori sono fissate nel LaTeX standard. Tuttavia, con il pacchetto `amsmath`, le dimensioni si adattano alle dimensioni del materiale circostante, in base alla dimensione del font e allo stile matematico in uso. Questo è mostrato nell'esempio seguente.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
\Large
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
```

![Delimitatori che si adattano alla dimensione del font e allo stile matematico correnti](/tex/images/java/tutorial/latex-ams-math-7-3.png)

## 7.4. Regolazione dell'indice su un radicale

Il posizionamento dell'indice su un segno radicale non è sempre ottimale nel LaTeX standard. Tuttavia, è possibile utilizzare i comandi `\leftroot` e `\uproot` definiti nel pacchetto `amsmath` per regolare il posizionamento di questo indice. Argomenti interi positivi a questi comandi spostano rispettivamente l'indice a sinistra e in alto, mentre gli argomenti negativi lo spostano a destra e in basso. Questi argomenti sono forniti in unità matematiche, che sono piuttosto piccole, quindi questi comandi sono adatti per la messa a punto fine.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[
  \sqrt[\beta]{k} \qquad
  \sqrt[\leftroot{2}\uproot{4} \beta]{k} \qquad
  \sqrt[\leftroot{1}\uproot{3} \beta]{k}
\]
```

![Regolazione dell'indice di un segno radicale](/tex/images/java/tutorial/latex-ams-math-7-4.png)

## 7.5. Perfezionamento con strut e phantom

Ogni volta che si desidera comporre "perfettamente" la spaziatura e l'allineamento della matematica, di solito è meglio rivolgersi alle capacità uniche e avanzate dei primitivi TeX. L'accesso a queste funzionalità è fornito da una serie di comandi relativi a `\phantom` e `\smash`. Tali comandi possono essere usati sia nelle formule matematiche che nel testo normale.

Diamo un'occhiata al seguente esempio:

```tex
\usepackage{amsmath}
\newcommand\relphantom[1]{\mathrel{\phantom{#1}}}
\newcommand\ve{\varepsilon} \newcommand\tve{t_{\varepsilon}}
\newcommand\vf{\varphi} \newcommand\yvf{y_{\varphi}}
\newcommand\bfE{\mathbf{E}}
% -------------------------------------------------------------------------------
\begin{equation} \begin{split}
  f_{h, \ve}(x, y)
    &= \ve \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve u)} \vf(x) \,du  \\
    &= h \int L_{x, z} \vf(x) \rho_x(dz)                             \\
    &\relphantom{=} {} + h \biggl[
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \varphi(x) \,ds
               - \tve \int L_{x, z} \varphi(x) \rho_x(dz)      \biggr) + \\
    &\relphantom{=} \phantom{{} + h \biggl[ }
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \varphi(x) \,ds
               - \bfE_{x, y} \int_0^{\tve} L_{x, y_{\varphi}(\varepsilon s)}
                                             \varphi(x) \,ds    \biggr) \biggr]
\end{split} \end{equation}
```

![I phantom della formula](/tex/images/java/tutorial/latex-ams-math-7-5.png)

Qui, il comando `\phantom` regola il posizionamento orizzontale. Nel preambolo, viene utilizzato per definire un simbolo di relazione invisibile di larghezza uguale al suo argomento (`=` in questo esempio). All'interno degli ambienti matematici, viene utilizzato per allineare determinate righe iniziandole con una sottoformula "phantom", o invisibile. La coppia di graffe vuote `{}` equivale a `\mathord{}`, che produce un simbolo invisibile a larghezza zero necessario per ottenere la spaziatura corretta di "+ *h*" (senza `{}`, il segno più verrebbe interpretato come un più unario con una spaziatura inappropriata prima di *h*).

A differenza di `\phantom`, il comando `\smash` compone il suo contenuto (in una scatola LR) ma ignora sia l'altezza che la profondità, come se fossero entrambe pari a zero. Il comando `\hphantom`, definito nel LaTeX standard, è una combinazione dei due. Produce l'equivalente di `\smash{\phantom{contenuto phantom}}`, ovvero un box invisibile con altezza e profondità pari a zero ma con la larghezza del contenuto phantom.

Il comando `\vphantom` è simile, ma rende nulla la larghezza del phantom preservandone l'altezza totale più la profondità. Il comando `\mathstrut` è definito come `\vphantom(` e produce un box a larghezza zero con altezza e profondità uguali a quelle di una parentesi.

Con il pacchetto `amsmath`, il comando `\smash` può accettare un argomento opzionale: `\smash[t]{...}` ignora l'altezza del contenuto del box mantenendone la profondità, mentre `\smash[b]{...}` ignora la profondità mantenendone l'altezza.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$\sqrt{x} + \sqrt{y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\mathstrut y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash{y}} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash[b]{y}} + \sqrt{z}$
```

![Smashing dell'espressione radicale](/tex/images/java/tutorial/latex-ams-math-7-6.png)

Sembrerebbe che dare alla *y* un po' di altezza extra con uno strut renda i radicali simili. Ma, al contrario, li rende solo più diversi e più brutti nell'insieme. Si scopre che "distruggere" (smashing) il fondo della *y* è il modo migliore.

L'esempio seguente mostra un uso molto comune dello smash. Il comando `\smash` viene utilizzato lì per fornire un controllo fine sull'altezza dei delimitatori circostanti. Dimostra anche che lo smash può causare problemi poiché è necessario conoscere la vera altezza della riga. Questo viene risolto tramite `\vphantom`. `\Hmjd` è il simbolo composto definito come:

```tex
\newcommand\Hmjd{\widetilde{\mathcal{H}^2}_{MJD}(\chi)}
```

Per mostrare lo spazio verticale risultante abbiamo aggiunto delle linee di riferimento:

| *Aspetto* | `Codice` | *Commento* |
|:---:|:---:|---|
| !["Parentesi esterne troppo grandi"](/tex/images/java/tutorial/latex-ams-math-smashing-7-1.png) | `\left( {\Hmjd } \right)` | *Parentesi esterne troppo grandi* |
| !["Parentesi esterne troppo piccole e righe troppo vicine"](/tex/images/java/tutorial/latex-ams-math-smashing-7-2.png) | `\left( \smash{\Hmjd } \right)` | *Parentesi esterne troppo piccole e righe troppo vicine* |
| !["Perfetto"](/tex/images/java/tutorial/latex-ams-math-smashing-7-3.png) | `\left( \smash[t]{\Hmjd } \right) \vphantom{\Hmjd}` | *Perfetto!* |
| !["Sono necessari sia vphantom che partial smash"](/tex/images/java/tutorial/latex-ams-math-smashing-7-4.png) | `\left( \smash[t]{\Hmjd } \right)` | *Sono necessari sia `\vphantom` che il partial smash* |

> In alcuni punti, carenze nell'elaborazione TeX di basso livello possono causare errori nei minimi dettagli della composizione. Ciò può accadere in layout particolari in cui (a) una sottoformula (numeratore/denominatore di una frazione o pedice/apice) consiste esattamente di un box LR, o di un box matematico costruito in modo simile, e inoltre (b) tale box non ha le sue dimensioni naturali, come nel caso delle forme più complesse di `\makebox`, degli smash e di alcuni phantom.

Per vedere questo, diamo un'occhiata al seguente esempio:

```tex
\[
\sqrt{ \frac{a+b}{x_j} } \quad
\sqrt{ \frac{a+b}{\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{{}\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{\smash{x_j+b}} }
\]
```

![Problemi causati dagli smash](/tex/images/java/tutorial/latex-ams-math-7-7.png)

Per ridurre la profondità del radicale, uno `\smash` è stato aggiunto nel secondo radicale, ma questo non ha avuto alcun effetto. Nel terzo radicale ha funzionato con un gruppo di graffe vuote. Ma nel quarto radicale non è stato necessario un gruppo di graffe vuote. In sintesi, ogni volta che trovate che `\smash` non funziona, provate ad aggiungere una sottoformula matematica vuota (`{}`) prima del box isolato, per farlo trattare correttamente.

## 7.6. Spaziatura orizzontale

La messa a punto più fine e difficile richiede i comandi di spaziatura espliciti mostrati nella tabella seguente:

![Comandi di spaziatura orizzontale](/tex/images/java/tutorial/latex-ams-math-7-8.png)

Sia le forme complete che quelle brevi di questi comandi sono robuste e possono essere usate anche al di fuori delle formule matematiche nel testo normale. Sono correlati agli spazi sottili, medi e ampi disponibili sulle macchine utilizzate per comporre la matematica a metà del XX secolo.

I valori attuali dei tre parametri TeX `\thinmuskip`, `\medmuskip` e `\thickmuskip` definiscono la quantità di spazio aggiunta da questi comandi `\..space`. I loro valori predefiniti con `amsmath` sono elencati nella tabella. Questi parametri di basso livello richiedono valori in unità matematiche (*mu*). Pertanto, possono essere impostati solo tramite assegnazioni TeX di basso livello, non tramite `\setlength` o simili. Inoltre, normalmente i loro valori non dovrebbero essere modificati poiché vengono utilizzati internamente dalla composizione matematica di TeX (vedere la seguente tabella).

![Spaziatura tra simboli](/tex/images/java/tutorial/latex-ams-math-7-9.png)

> Nella tabella, 0 significa "nessuno spazio", 1 significa `\thinmuspace`, 2 significa `\medmuskip`, 3 significa `\thickmuskip`, * significa "impossibile". Le voci in grassetto indicano che la spaziatura corrispondente non viene aggiunta negli stili di script matematici.

Un'unità matematica (`1mu`) è pari a 1/18 di un *em* nella dimensione del font matematico corrente. Ne consegue che il valore assoluto di un *mu* varia con lo stile matematico, fornendo una spaziatura coerente indipendentemente dallo stile usato.