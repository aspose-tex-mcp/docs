---
translation: true
template: /templates/_template-java.md
linktitle: I font matematici in LaTeX
title: 8. I font nelle formule matematiche
weight: 80
url: /java/latex-math-fonts/
keywords: ams-latex, amsmath, amsfonts, amssymb, font matematici LaTeX, alfabeti matematici LaTeX, pacchetto bm LaTeX, font in LaTeX, font in LaTeX matematica
description: Questo articolo discute la gestione dei font matematici tramite il LaTeX standard e l'utilizzo dei pacchetti amsmath e bm.
lastmod: "2026-03-30"
---

{{<section overview>}}

## Introduzione ai font in LaTeX

A differenza del testo a scorrimento, in genere non sono necessari cambiamenti automatici nelle forme dei font. Forme diverse hanno significati specifici in matematica. Ad esempio, le lettere verticali in grassetto possono essere utilizzate per i vettori. Se i caratteri in una formula dovessero cambiare a causa delle condizioni circostanti, il risultato sarebbe errato. Ecco perché la gestione dei font nelle formule matematiche differisce da quella nel testo.

I caratteri in una formula possono essere divisi in due classi: simboli e caratteri alfabetici (comprese le cifre). In realtà, TeX gestisce internamente otto classi che definiscono la spaziatura appropriata, ma per la discussione in corso è sufficiente la divisione in due classi.

Alcuni simboli, come `=`, possono essere inseriti direttamente dalla tastiera. Tuttavia, parte di essi deve essere inserita tramite un comando: ad esempio, `\leq` produce il segno di minore o uguale. L'altro gruppo principale di caratteri in una formula, i caratteri alfabetici, viene inserito direttamente dalla tastiera.

Esistono più di 200 simboli predefiniti nel LaTeX standard, il che consente all'utente di comporre quasi ogni formula desiderata. Questi simboli si trovano in diversi font, ma vi si accede in modo tale che l'utente non debba preoccuparsi di come siano rappresentati internamente. Se necessario, è possibile rendere accessibili in modo simile font di simboli aggiuntivi.

Simboli e caratteri alfabetici hanno una differenza molto importante: i simboli hanno la stessa rappresentazione grafica all'interno di una formula, mentre l'utente può cambiare l'aspetto dei caratteri alfabetici. I comandi che cambiano l'aspetto dei caratteri alfabetici in una formula sono chiamati *identificatori alfabetici matematici* e i font associati a questi comandi sono chiamati *alfabeti matematici*. Una formula non cambia se viene posizionata, ad esempio, all'interno di un ambiente di teorema in cui il testo è composto in corsivo per impostazione predefinita, poiché gli identificatori alfabetici sono indipendenti dai comandi dei font circostanti al di fuori della formula. Questo comportamento è fondamentale perché le forme dei caratteri veicolano significati che devono rimanere invariati ovunque la formula appaia nel documento.

## 8.1. Identificatori alfabetici matematici

Un solo alfabeto e un numero enorme di simboli non sono sufficienti per gli scienziati, che cercano di utilizzare ogni font disponibile per indicare concetti speciali. Oltre agli alfabeti stranieri come le lettere greche (solitamente accessibili come simboli — `\alpha`, `\beta`, ecc.), si possono trovare lettere sans serif per le matrici, lettere serif in grassetto per i vettori, font Fraktur per gruppi, ideali o campi. Altri usano forme calligrafiche per indicare gli insiemi. Il numero di convenzioni è infinito e varia da una disciplina all'altra. LaTeX asseconda tutto questo consentendo di dichiarare nuovi identificatori alfabetici matematici e di associarli a qualsiasi forma di font desiderata, invece di affidarsi solo a un set predefinito non estensibile. Questi identificatori sono comandi speciali da usare in una formula che compongono qualsiasi carattere alfabetico nel loro argomento con uno specifico font. Questi identificatori possono utilizzare font diversi in formule diverse, come vedremo [più avanti](/tex/{{lang.url-fragment}}java/latex-math-fonts/#3-math-formula-versions), ma all'interno di una singola formula selezionano sempre lo stesso font indipendentemente dalle condizioni circostanti.

### Identificatori alfabetici predefiniti

LaTeX ha già alcuni identificatori alfabetici integrati, mostrati nella tabella seguente. Le ultime due righe mostrano che le lettere usate nelle formule sono tratte dall'alfabeto matematico `\mathnormal`. D'altra parte, le lettere prodotte da `\mathit` hanno una spaziatura diversa, il che significa che questo alfabeto può essere usato per nomi di variabili composti da una parola intera, comuni in alcune discipline.

| *Comando* | *Codice di esempio* | *Risultato* |
|---|---|---|
| `\mathcal` | `$\mathcal{A}=a$` | !["Calligraphic A Equals a"](/tex/images/java/tutorial/latex-ams-math-8-1.png) |
| `\mathrm` | `$\mathrm{max}_i$`| !["Roman Max Subscript i"](/tex/images/java/tutorial/latex-ams-math-8-2.png) |
| `\mathbf` | `$\sum x = \mathbf{v}$`| !["Bold Sum x Equals v"](/tex/images/java/tutorial/latex-ams-math-8-3.png) |
| `\mathsf` | `$\mathsf{G}_1^2$`| !["Sans-serif G Subscript 1 Superscript 2"](/tex/images/java/tutorial/latex-ams-math-8-4.png) |
| `\mathtt` | `$\mathtt{W}(a)$`| !["Typewriter W of a"](/tex/images/java/tutorial/latex-ams-math-8-5.png) |
| `\mathnormal` | `$\mathnormal{abc}=abc$`| !["Normal abc Equals abc"](/tex/images/java/tutorial/latex-ams-math-8-6.png) |
| `\mathit` | `$differ\neq\mathit{differ}$`| !["Italic Differ Not Equal to Differ"](/tex/images/java/tutorial/latex-ams-math-8-7.png) |

In LaTeX2e, gli identificatori alfabetici matematici sono comandi con un argomento: una singola lettera o una singola parola da comporre con un font speciale.

```tex
Therefore, $\mathsf{G}$ can be computed as
\begin{equation}
\mathsf{G} = \mathcal{A} +
             \sum_{i=1}^{n} \mathcal{B}_{i}
\end{equation}
```

![Identificatori alfabetici matematici predefiniti](/tex/images/java/tutorial/latex-ams-math-8-8.png)

***Alfabeto matematico predefinito***

Se non si specifica esplicitamente un identificatore alfabetico, da quale alfabeto vengono selezionati i caratteri? In altre parole, qual è l'alfabeto matematico predefinito? La risposta è che non esiste un unico alfabeto matematico predefinito. Il sistema LaTeX può essere impostato in modo che i caratteri alfabetici siano prelevati da alfabeti diversi (a meno che l'utente non ne richieda uno specifico), e questo è normalmente il caso, come mostrato nell'esempio seguente.

```tex
\begin{eqnarray}
x &=& 12345 \\
\mathrm{x} &=& \mathrm{12345} \\
\mathnormal{x} &=& \mathnormal{12345}
\end{eqnarray}
```

![Nessun alfabeto matematico predefinito](/tex/images/java/tutorial/latex-ams-math-8-9.png)

Qui si può vedere che `\mathrm` non cambia le cifre e `\mathnormal` non cambia le lettere; quindi, il predefinito per le cifre nella configurazione normale è l'alfabeto matematico associato a `\mathrm`, mentre il predefinito per le lettere è quello associato a `\mathnormal`. Questo comportamento può essere controllato con il comando `\DeclareMathSymbol`.

### Quale font usa LaTeX per la matematica?

In LaTeX, il font predefinito utilizzato per la modalità matematica è in genere *Computer Modern*. Tuttavia, è possibile utilizzare anche font diversi specificandoli nel preambolo del documento tramite appositi pacchetti.

### Identificatori alfabetici personalizzati

È possibile utilizzare il comando `\DeclareMathAlphabet` per definire un nuovo identificatore alfabetico matematico. Supponiamo di voler rendere disponibile un font sans serif inclinato come alfabeto matematico. Per prima cosa, si sceglie un nuovo nome per il comando, ad esempio `\msfsl`. Quindi, si fa riferimento alla tabella di classificazione dei font qui sotto per trovare un gruppo di forme di font adatto da assegnare a questo identificatore.

![Classificazione delle famiglie di font Computer Modern](/tex/images/java/tutorial/latex-ams-math-8-10.png)

Si scoprirà che la famiglia **Computer Modern Sans**, ad esempio, consiste in una serie medium con forme verticali e inclinate. Se si decide di utilizzare la forma inclinata di questa famiglia, lo si comunica a LaTeX tramite `\DeclareMathAlphabet`.

```text
\DeclareMathAlphabet{cmd}{encoding}{family}{series}{shape}
```

Esistono quattro parametri (oltre all'identificatore stesso) nella dichiarazione: il nome della codifica, la famiglia, la serie e la forma del font da utilizzare. L'identificatore alfabetico definito nel seguente esempio passerà sempre a **Computer Modern Sans** medium slanted.

```tex
\DeclareMathAlphabet{\msfsl}{OT1}{cmss}{m}{sl}
% -------------------------------------------------------------------------------
We demonstrate this with the formula
\begin{equation}
\sum \msfsl{A}_{i} = a \tan \beta
\end{equation}
```

![Dichiarazione di un identificatore alfabetico matematico personalizzato](/tex/images/java/tutorial/latex-ams-math-8-11.png)

È anche possibile ridefinire un identificatore alfabetico matematico esistente in un pacchetto o nel preambolo del documento. Per esempio:

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{pag}{m}{n}
```

sostituirà le impostazioni predefinite per l'identificatore `\mathsf`, passando a **Adobe Avant Garde** nelle formule.

> Si noti che se l'alfabeto matematico in questione fa parte di un font di simboli già caricato da LaTeX per altri motivi (ad esempio, `\mathcal`), è meglio usare `\DeclareSymbolFontAlphabet`, poiché sfrutta meglio le risorse talvolta limitate di TeX per la matematica.

## I migliori font matematici

Oltre al font predefinito *Computer Modern*, LaTeX offre sette font integrati per la composizione degli alfabeti matematici, consentendo agli utenti di personalizzare le proprie espressioni senza richiedere pacchetti aggiuntivi nel preambolo. Usare uno di questi 8 font è l'opzione migliore.

| **Font** | **Utilizzo** | **Comando** |
|---|---|---|
|Romano verticale | Font verticale standard|`\mathrm{}`|
|Corsivo matematico | Usato per comporre le normali lettere matematiche.|`\mathnormal{}`|
|Calligrafico | Usato per comporre lettere maiuscole con uno speciale font calligrafico.|`\mathcal{}`|
|Lettere corsive| Rende il testo in lettere corsive.|`\mathit{}`|
|Sans Serif verticale| Imposta le lettere in sans serif verticale.|`\mathsf{}`|
|Romano verticale grassetto| Usato per comporre lettere in romano verticale grassetto.|`\mathbf{}`|
|Dattilo (Typewriter)|Usato per comporre lettere verticali in stile macchina da scrivere.|`\mathtt{}`|


## 8.2. Comandi dei font di testo in matematica

Sebbene le dichiarazioni dei font di testo come `\rmfamily` non possano essere usate in matematica, i comandi che cambiano il font — ad esempio, `\textrm` — possono essere utilizzati sia nel testo che in matematica. Usando questi comandi, è possibile passare temporaneamente dal contesto matematico al testo e scrivere del testo nel mezzo della formula che logicamente faccia parte del testo circostante. Il font utilizzato dipenderà dalle condizioni esterne, ereditando codifica, famiglia, serie e forma correnti, come nell'esempio seguente.

```tex
\sffamily The result will be
\[ x = 10 \textbf{ and thus } y = 12 \]
```

![Comandi dei font di testo in matematica](/tex/images/java/tutorial/latex-ams-math-8-12.png)

Qui si vede che la famiglia **Sans** è stata mantenuta e la serie è stata cambiata in grassetto. Il comando [`\text`](/tex/{{lang.url-fragment}}java/latex-text-in-math-formula/#61-the-text-command) fornito dal pacchetto `amstext` (caricato anche da `amsmath`) può rivelarsi più utile, poiché rileva i valori di codifica, famiglia, serie e forma correnti senza modificarli.

## 8.3. Versioni delle formule matematiche

Abbiamo discusso di come cambiare parti di una formula utilizzando identificatori alfabetici matematici. LaTeX consente anche di cambiare l'aspetto di una formula nel suo insieme. Le formule matematiche sono sempre composte in una certa *versione matematica*. È possibile passare da una versione all'altra al di fuori della modalità matematica tramite il comando `\mathversion`, che cambia il layout generale delle formule successive.

LaTeX ha due versioni matematiche predefinite: *normal* e *bold*. Pacchetti speciali offrono ulteriori versioni: ad esempio, il pacchetto *MathTime* (per i font commerciali **MathTime**) imposta una versione chiamata *heavy* per comporre formule con simboli ultra-grassetti.

Ovviamente, la versione predefinita è `\mathversion{normal}`. La versione bold, a sua volta, produce caratteri alfabetici e simboli in grassetto, anche se i grandi operatori come `\sum` non vengono modificati per impostazione predefinita. L'esempio seguente mostra la stessa formula prima nella versione normale e poi in quella grassetto.

```tex
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
\mathversion{bold}
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
```

![Versioni matematiche](/tex/images/java/tutorial/latex-ams-math-8-13.png)

L'uso di `\mathversion` può essere adatto in certe situazioni, come nelle intestazioni, ma bisogna ricordare che cambiare versione significa cambiare l'aspetto e forse il significato dell'intera formula. Se si desidera rendere in grassetto solo alcuni simboli o caratteri in una formula, è preferibile usare l'identificatore `\mathbf` per i caratteri e/o il comando `\bm` del pacchetto [`bm`](/tex/{{lang.url-fragment}}java/latex-math-fonts/#5-bold-face-in-formulas-the-bm-package).

Quando si cambia la versione matematica, LaTeX consulta le sue tabelle interne per trovare i simboli della nuova versione. Può anche cambiare alcuni o tutti gli identificatori alfabetici matematici associandoli ad altre forme di font.

Ma cosa succede agli identificatori personalizzati come `\msfsl` definiti nell'[esempio](/tex/{{lang.url-fragment}}java/latex-math-fonts/#custom-alphabet-identifiers)? Se dichiarati tramite `\DeclareMathAlphabet`, rimarranno gli stessi in tutte le versioni matematiche.

Se l'identificatore deve produrre un font diverso in una versione speciale, bisogna comunicarlo a LaTeX tramite `\SetMathAlphabet`. Ad esempio:

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{cmss}{m}{n}
\SetMathAlphabet{\mathsf}{bold}{OT1}{cmss}{bx}{n}
```

La prima riga imposta **Computer Modern Sans** Medium come predefinito per `\mathsf`. La seconda istruisce LaTeX a usare **Computer Modern Sans** Bold Extended nella versione bold.

```tex
\SetMathAlphabet{cmd}{version}{encoding}{family}{series}{shape}
```

`\SetMathAlphabet` accetta sei argomenti: l'identificatore alfabetico, il nome della versione matematica, e i quattro parametri del font da associare.

Come notato prima, si può ridefinire un identificatore esistente con `\DeclareMathAlphabet`. In tal caso, tutte le precedenti dichiarazioni `\SetMathAlphabet` per quell'identificatore vengono rimosse dalla memoria di LaTeX.

## 8.4. Ottimizzazione dei font nelle formule con i pacchetti AMS-LaTeX

Il pacchetto *amsfonts* (e *amssymb*) definisce due alfabeti matematici: l'alfabeto Euler Fraktur (`\mathfrak`) e l'alfabeto Blackboard Bold (`\mathbb`). Vedere l'esempio seguente.

```tex
\usepackage{amsfonts}
% -------------------------------------------------------------------------------
$ \forall n \in \mathbb{N} : \mathfrak{M}_n \leq \mathfrak{A} $
```

![Identificatori alfabetici matematici amsfonts](/tex/images/java/tutorial/latex-ams-math-8-14.png)

## 5. Lo stile dei font matematici in grassetto. Il pacchetto bm

Solo per le lettere latine si può usare il comando `\mathbf`. Per tutto il resto esiste il pacchetto `bm`. Basta caricarlo e usare `\bm` per creare formule in grassetto.

L'esempio seguente mostra vari modi di usare `\bm` e `\mathbf`. Mostra anche una strategia per definire nomi abbreviati per simboli in grassetto frequenti, usando sia `\newcommand` che `\bmdefine` (fornito dal pacchetto `bm`). Notate che `\mathbf{xy}` non è identico a `\bm{xy}`: il primo produce un romano grassetto "**xy**", il secondo un corsivo matematico in grassetto "***xy***".

```tex
\usepackage{amsmath,amssymb,bm}
\newcommand\bfB{\mathbf{B}} \newcommand\bfx{\mathbf{x}}
\bmdefine\bpi{\pi} \bmdefine\binfty{\infty}
% -------------------------------------------------------------------------------
\section{The bold equivalence
  $\sum_{j < B} \prod_\lambda : \bm{\sum_{x_j} \prod_\lambda}$}
\begin{gather}
  B_\infty + \pi B_1 \sim \bfB_{\binfty} \bm{+} \bpi \bfB_{\bm{1}}
    \bm {\sim B_\infty + \pi B_1}\\
  B_\binfty + \bpi B_{\bm{1}} \bm{\in} \bm{\biggl\lbrace}
    (\bfB, \bfx) : \frac {\partial \bfB}{\partial\bfx}
    \bm{\lnapprox} \bm{1} \bm{\biggr\rbrace}
\end{gather}
```

![Utilizzo del pacchetto bm](/tex/images/java/tutorial/latex-ams-math-8-15.png)

In questo esempio `bm` cerca di soddisfare le richieste di versioni in grassetto di singoli simboli e lettere. Ma a un'analisi attenta i risultati non sono sempre ottimali. Per gli operatori di somma e prodotto viene usata la tecnica *poor man's bold*, sovrimprimendo il simbolo tre volte. Inoltre, le graffe non sono affatto in grassetto. Questi inconvenienti sono inevitabili perché per alcuni simboli non esiste una variante in grassetto nei font **Computer Modern**.

Quali regole segue `\bm`? In generale, sfrutta la versione matematica **bold** di LaTeX (accessibile via `\boldmath`). Per ogni simbolo, `\bm` controlla quella versione: se il font selezionato è diverso da quello normale, compone il simbolo con quel font (risultato perfetto). Se i font sono identici, assume che non ci sia una variante e applica il *poor man's bold*.

> Caricate il pacchetto `bm` dopo i pacchetti che modificano la configurazione esistente dei font matematici!

Con i delimitatori (come `\biggl\lbrace`) la situazione è complessa. TeX compone un delimitatore da un glifo scelto per l'altezza richiesta da una sequenza di dimensioni. Questi glifi possono trovarsi in font diversi e non tutti hanno varianti in grassetto. Questo rende impossibile per `\bm` determinare sempre se applicare il *poor man's bold*.

```tex
\usepackage{bm}
% -------------------------------------------------------------------------------
$\bm{\Biggl\lbrace\biggl\lbrace\Bigl\lbrace\bigl \lbrace \lbrace
  \mathcal{Q}
  \rangle \bigr\rangle\Bigr\rangle\biggr\rangle
\Biggr\rangle}$
```

![Delimitatori resi (e non resi) in grassetto dal comando \bm](/tex/images/java/tutorial/latex-ams-math-8-16.png)

Normalmente, un comando che accetta argomenti deve essere incluso interamente nell'argomento di `\bm`. Se si desidera comporre solo parte dell'output in grassetto, si possono mettere i simboli non grassetti in un `\mbox` e ripristinare la versione matematica con `\unboldmath`, circondandolo magari con `\mathbin`, `\mathrel` o `\mathop` per la spaziatura corretta.

```tex
\usepackage{amsmath,bm}
% -------------------------------------------------------------------------------
$ \bm{\sqrt[2]{x \times \alpha}} $ ma
$ \bm{\sqrt[2]{x \mathbin{\mbox{\unboldmath$\times$}} \alpha}} $
o simile
$ \bm{\sqrtsign}{\bm{x} \times \bm{\alpha}} $
```

![ \bm con comandi che accettano argomenti](/tex/images/java/tutorial/latex-ams-math-8-17.png)

Fortunatamente, operazioni così complesse sono raramente necessarie. Di solito basta usare `\bm` dentro gli argomenti dei comandi. Per gli accenti in grassetto, `\bm` permette all'argomento dell'accento di stare fuori dal proprio. Se servono spesso, è meglio definire abbreviazioni.

***Miglioramento delle prestazioni***

Sebbene `\bmdefine\bpi{\pi}` sembri un'abbreviazione per `\newcommand\bpi{\bm{\pi}}`, la verità è l'opposto: `\bm` definisce un comando temporaneo tramite `\bmdefine`. Quindi `\bmdefine` fa il lavoro pesante. Se usate spesso `\bm{\alpha}`, viene eseguito un `\bmdefine` ogni volta. Definendo `\bmdefine\balpha{\alpha}` nel preambolo, il lavoro viene fatto una sola volta.

```tex
\usepackage{bm}
\bmdefine\bhat{\hat}
% -------------------------------------------------------------------------------
$\hat a \neq \bm{\hat a} \neq \bm\hat a = \bhat a\neq \bm\widehat a$
```

![Ottimizzazione degli accenti in grassetto con il comando \bm](/tex/images/java/tutorial/latex-ams-math-8-18.png)

Questo esempio mostra che gli accenti a larghezza variabile (`\widehat`) condividono una carenza con i delimitatori: nella configurazione **Computer Modern** provengono da font senza varianti in grassetto.