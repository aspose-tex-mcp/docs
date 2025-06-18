---
translation: true
template: /templates/_template-java.md
linktitle: Caratteri di matematica in LaTeX
title: 8. Fonts in Math Formule | Matematica del carattere in LaTeX
weight: 80
url: /java/latex-math-fonts/
keywords: AMS-Latex, Amsmath, Amsfonts, AMSSYMB, Fonts di matematica in LaTeX, alfabeti di matematica in LaTeX, pacchetto BM in LaTeX, caratteri in LaTeX, caratteri in LaTeX matematica
description: Questo articolo discute la gestione dei caratteri matematici per mezzo del LaTeX standard, nonché l'utilizzo dei pacchetti AMSMath e BM.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Introduzione ai caratteri in LaTeX

A differenza del testo galleggiante, in genere non avresti bisogno di cambiamenti automatici nelle forme del carattere. Forme diverse hanno significati specifici in matematica. Ad esempio, le lettere verticali in grassetto possono essere utilizzate per i vettori. Se i personaggi in una formula dovessero cambiare a causa delle condizioni circostanti, il risultato sarebbe errato. Ecco perché la gestione dei caratteri nelle formule di matematica differisce da quella nel testo.

I personaggi in una formula possono essere divisi in due classi: simboli e caratteri alfabeti (comprese le cifre). In realtà, Tex si occupa internamente di otto classi che definiscono la spaziatura appropriata. Ma per la discussione in corso, la divisione in due classi è abbastanza.

Alcuni simboli, come `=`, possono essere inseriti direttamente dalla tastiera. Tuttavia, una parte di essi deve essere inserita tramite un comando, ad esempio, `\leq` fornisce un segno inferiore o uguale. L'altro gruppo principale di caratteri in una formula, i caratteri dell'alfabeto, vengono inseriti direttamente dalla tastiera.

Ci sono più di 200 simboli predefiniti nel LaTeX standard. Consente all'utente di compiere quasi tutte le formula desiderate. Questi simboli si trovano in diversi caratteri, ma è possibile accedere in modo tale che l'utente non debba essere consapevole di come sono rappresentati internamente. Se necessario, i caratteri a simbolo aggiuntivi possono essere resi accessibili in modo simile.

I simboli e i caratteri alfabeti hanno una differenza che è più importante per noi ora: i simboli hanno la stessa rappresentazione grafica all'interno di una formula, mentre l'utente può cambiare l'aspetto dei caratteri dell'alfabeto. I comandi che cambiano l'aspetto dei caratteri dell'alfabeto in una formula sono chiamati *identificatori di alfabeto di matematica* e i caratteri associati a questi comandi sono chiamati *alfabeti matematici*. Una formula non cambia se viene posizionata, per esempio, all'interno di un ambiente di teorema in cui il testo è composto in corsivo per impostazione predefinita, perché gli identificatori di alfabeto sono indipendenti dai comandi di carattere circostante al di fuori della formula. Questo comportamento è molto importante perché le forme di carattere trasportano significati che devono rimanere invariati ovunque la formula appaia in un documento.

## 8.1. Identificatori alfabeti di matematica

Un alfabeto e un numero enorme di simboli non sono sufficienti per gli scienziati. Cercano di utilizzare ogni carattere tipografico disponibile per indicare concetti speciali. Oltre agli alfabeti stranieri come le lettere greche, che di solito sono accessibili come simboli - `\alpha`,`\beta`, ecc. - Possiamo trovare lettere serif sans per matrici, lettere serif audaci per vettori, caratteri Fraktur per gruppi, ideali o campi. Altri usano forme calligrafiche per indicare i set. Il numero di convenzioni è infinito e differiscono da una disciplina all'altra. E il LaTeX accoglie questo che consente di dichiarare nuovi identificatori di alfabeto matematico e associarli a qualsiasi gruppo di forma di carattere desiderato invece di fare affidamento solo su un set predefinito che non può essere esteso. Questi identificatori sono comandi speciali da utilizzare in una formula che compromettono qualsiasi carattere alfabetico nel loro argomento in un carattere tipografico specifico. Questi identificatori possono utilizzare diversi caratteri tipografici in diverse formule, come vedremo [più tardi](/tex/{{lang.url-fragment}}java/latex-math-fonts/#3-math-formula-versions), ma all'interno di una formula selezionano sempre lo stesso carattere tipografico indipendentemente dalle condizioni circostanti.

### Identificatori alfabeti predefiniti

LaTex ha già alcuni identificatori di alfabeto integrati. Sono mostrati nella tabella seguente. Le ultime due righe mostrano che le lettere utilizzate nelle formule sono tratte dall'alfabeto matematico `\mathnormal`. D'altra parte, le lettere prodotte da `\Mathit` hanno una spaziatura diversa, il che significa che questo alfabeto può essere usato per fornire nomi di variabili di una parola piena che sono comuni in alcune discipline.

| *Comando* | *Codice di esempio* | *Risultato* |
|---|---|---|
| `\mathcal` | `$\mathcal{A}=a$` | !["Calligraphic A Equals a"](/tex/images/java/tutorial/latex-ams-math-8-1.png) |
| `\mathrm` | `$\mathrm{max}_i$`| !["Roman Max Subscript i"](/tex/images/java/tutorial/latex-ams-math-8-2.png) |
| `\mathbf` | `$\sum x = \mathbf{v}$`| !["Bold Sum x Equals v"](/tex/images/java/tutorial/latex-ams-math-8-3.png) |
| `\mathsf` | `$\mathsf{G}_1^2$`| !["Sans-serif G Subscript 1 Superscript 2"](/tex/images/java/tutorial/latex-ams-math-8-4.png) |
| `\mathtt` | `$\mathtt{W}(a)$`| !["Typewriter W of a"](/tex/images/java/tutorial/latex-ams-math-8-5.png) |
| `\mathnormal` | `$\mathnormal{abc}=abc$`| !["Normal abc Equals abc"](/tex/images/java/tutorial/latex-ams-math-8-6.png) |
| `\mathit` | `$differ\neq\mathit{differ}$`| !["Italic Differ Not Equal to Differ"](/tex/images/java/tutorial/latex-ams-math-8-7.png) |

In Latex2E, gli identificatori di alfabeto di matematica sono comandi con un argomento, una singola lettera o una singola parola da compensare in un carattere speciale.


```tex
Therefore, $\mathsf{G}$ can be computed as
\begin{equation}
\mathsf{G} = \mathcal{A} +
             \sum_{i=1}^{n} \mathcal{B}_{i}
\end{equation}
```

![Identificatori alfabeti di matematica predefinita](/tex/images/java/tutorial/latex-ams-math-8-8.png)

*** Alphabet matematica predefinita***

Se non si specifica esplicitamente un identificatore di alfabeto, da cui sono selezionati i caratteri dell'alfabeto? In altre parole, qual è l'alfabeto matematico predefinito? La risposta è che non esiste un singolo alfabeto matematico predefinito. Il sistema in LaTeX può essere impostato in modo che i caratteri alfabetici vengano recuperati da diversi alfabeti, a meno che l'utente non ne richieda esplicitamente uno specifico, e questo è normalmente il caso, come mostra l'esempio seguente.

```tex
\begin{eqnarray}
x &=& 12345 \\
\mathrm{x} &=& \mathrm{12345} \\
\mathnormal{x} &=& \mathnormal{12345}
\end{eqnarray}
```

![Nessun alfabeto matematico predefinito](/tex/images/java/tutorial/latex-ams-math-8-9.png)

Qui puoi vedere che `\mathrm` non cambia le cifre e`\mathnormal` non cambia le lettere, quindi il valore predefinito per le cifre nella normale configurazione è l'alfabeto matematico associato a `\mathrm` e il valore predefinito per le lettere è quello associato a`\mathnormal`. Questo comportamento può essere controllato con il comando `\dichiarathsymbol".

### Quale carattere usa il LaTeX per la matematica?

In LaTeX, il carattere predefinito utilizzato per la modalità matematica è in genere *computer moderno *. Tuttavia, puoi anche usare caratteri diversi specificandoli nel preambolo del documento Latex usando i pacchetti.

### Identificatori alfabeti personalizzati

È possibile utilizzare il comando `\dichiarathalphabet` per definire un nuovo identificatore di alfabeto matematico. Diciamo che vuoi rendere disponibile un carattere tipografico sans serif inclinati come alfabeto di matematica. Per prima cosa decidi un nuovo nome di comando, come `\msfsl`, da usare come identificatore di alfabeto. Quindi ti riferisci alla tabella di classificazione del carattere di seguito per trovare un gruppo di forma del carattere adatto da assegnare a questo identificatore di alfabeto.

![Classificazione delle famiglie di caratteri moderni del computer](/tex/images/java/tutorial/latex-ams-math-8-10.png)

Scoprirai che la famiglia moderna **moderna**, ad esempio, è costituita da una serie media con forme verticali e inclinate. Se decidi di usare la forma inclusa di questa famiglia, dici il LaTeX usando `\dichiarathalphabet`.

```text
\DeclareMathAlphabet{cmd}{encoding}{family}{series}{shape}
```

Esistono quattro parametri (oltre all'identificatore stesso) nella dichiarazione: il nome di codifica, la famiglia, la serie e la forma del carattere da utilizzare. L'identificatore di alfabeto definito nel seguente esempio passerà sempre a **Computer modern sans** medio inclinato.

```tex
\DeclareMathAlphabet{\msfsl}{OT1}{cmss}{m}{sl}
% -------------------------------------------------------------------------------
We demonstrate this with the formula
\begin{equation}
\sum \msfsl{A}_{i} = a \tan \beta
\end{equation}
```

![Dichiarare un identificatore di alfabeto matematico personalizzato](/tex/images/java/tutorial/latex-ams-math-8-11.png)

Puoi anche ridefinire un identificatore di alfabeto matematico esistente in un file di pacchetto o nel preambolo del documento. Per esempio,

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{pag}{m}{n}
```

Sostituirà le impostazioni predefinite per l'identificatore di alfabeto `\mathsf`. Passerà a **Adobe Avant Garde** nelle tue formule.

> Si noti che se l'alfabeto matematico in questione fa parte di un font di simboli già caricato da LaTeX per altri motivi (ad esempio, `\mathcal`), è meglio usare `\DeclareSymbolFontAlphabet` poiché sfrutta meglio le risorse alquanto limitate di TeX per la matematica.

## I migliori caratteri di matematica

Oltre al carattere predefinito *per computer moderno*, il LaTeX offre sette caratteri integrati per la composizione alfabetica matematica, in modo che gli utenti possano personalizzare le proprie espressioni matematiche senza richiedere pacchetti aggiuntivi nel preambolo. E l'opzione migliore per te è usare uno di questi 8 caratteri.

| **Carattere** | **Utilizzo** | **Comando** |
|---|---|---|
|Roman Verticale | Carattere Verticale Standard|`\mathrm{}`|
|Calligrafico | Utilizzato per la composizione di lettere matematiche regolari.|`\mathnormal{}`|
|Calligrafico | Utilizzato per la composizione di lettere maiuscole con uno speciale font calligrafico.|`\mathcal{}`|
|Lettere Corsive| Rende il testo in corsivo|`\mathit{}`|
|[Sans Serif Verticale](/font/net/what-is-font/sans-serif-fonts/)| Imposta le lettere Sans Serif verticali|`\mathsf{}`|
|Roman Verticale Grassetto| Utilizzato per la composizione di lettere Romane Verticali Grassetto|`\mathbf{}`|
|Tipo di macchina da scrivere|Utilizzato per la composizione di lettere verticali tipo macchina da scrivere.|`\mathtt{}`|


## 8.2. Comandi di carattere di testo in matematica

Sebbene le dichiarazioni del carattere di testo come `\rmfamily` non possano essere usate in matematica, i comandi che cambiano il carattere - ad esempio,`\textrm` - possono essere utilizzati sia in testo che in matematica. Usando questi comandi, è possibile passare temporaneamente dal contesto matematico al testo e scrivere un testo nel mezzo della formula che logicamente fa parte del testo circostante fuori dalla formula. Il carattere utilizzato per compensare questo testo dipenderà dalle condizioni circostanti, il che significa che erediterà l'attuale codifica, famiglia, serie e forma, come nell'esempio seguente.

```tex
\sffamily The result will be
\[ x = 10 \textbf{ and thus } y = 12 \]
```

![Comandi di carattere di testo in matematica](/tex/images/java/tutorial/latex-ams-math-8-12.png)

Qui possiamo vedere che la famiglia **Sans** è stata mantenuta e la serie è stata cambiata in grassetto. Il comando [`\text`](/tex/{{lang.url-fragment}}java/latex-text-in-math-formula/#61-the-text-command) fornito dal pacchetto `amstext` (che è anche caricato da `amsmath`) può rivelarsi più utile. Raccoglie i valori di codifica, famiglia, serie e forma attuale senza cambiarne nessuno.

## 8.3. Versioni di formula matematica

Abbiamo discusso di come cambiare parti di una formula usando identificatori di alfabeto matematico. Il LaTeX ti consente anche di cambiare l'aspetto di una formula nel suo insieme. Le formule di matematica sono sempre composti in una certa *versione matematica *. E puoi passare da una versioni matematiche al di fuori della modalità matematica usando il comando `\mathversion`, che cambia il layout generale delle seguenti formule.

Latex ha due versioni matematiche per impostazione predefinita: *normale * e *grassetto*. E i pacchetti speciali offrono più versioni. Ad esempio, il pacchetto *MathTime*(per i caratteri commerciali **MathTime**) imposta una versione matematica chiamata*Heavy*per compensare formule con simboli ultra audaci come fornito dai caratteri **MathTime**.

Ovviamente, la versione matematica predefinita è `\mathversion {normale}`. La versione audace, a sua volta, produrrà caratteri e simboli alfabeti audaci, sebbene i grandi operatori, come `\sum`, non siano modificati per impostazione predefinita. L'esempio seguente mostra prima la stessa formula nella versione matematica normale e poi nella versione matematica audace.

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

L'uso di `\Mathversion` può essere adatto in determinate situazioni, ad esempio nelle intestazioni, ma devi tenere presente che cambiare la versione significa cambiare l'aspetto e possibilmente il significato dell'intera formula. Se si desidera oscurare solo alcuni simboli o caratteri all'interno di una formula, è necessario utilizzare l'identificatore di alfabeto `\mathbf` per i personaggi e/o utilizzare il comando `\bm` fornito dal pacchetto [`bm`](/tex/{{lang.url-fragment}}java/latex-math-fonts/#5-bold-face-in-formulas-the-bm-package) piuttosto che modificare`\mathversion`.

Quando si cambia la versione matematica, il LaTeX guarda nelle sue tabelle interne per trovare dove si trovano tutti i simboli per questa nuova versione matematica. Può anche cambiare tutto o alcuni degli identificatori di alfabeti matematici e associarli ad altre forme di carattere in questa versione.

Ma cosa succede agli identificatori di alfabeto personalizzati come `\msfsl` che abbiamo definito nell'[esempio](/tex/{{lang.url-fragment}}java/latex-math-fonts/#custom-alphabet-identifiers)? Finché li hai dichiarati usando `\DeclareMathAlphabet`, rimarranno gli stessi in tutte le versioni di matematica.

Se l'identificatore di alfabeto matematico deve produrre un carattere diverso in una versione matematica speciale, è necessario raccontarne il LaTeX usando il comando `\setmathalphabet`. Ad esempio, nell'impostazione predefinita l'identificatore di alfabeto `\mathsf` è definito come segue:

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{cmss}{m}{n}
\SetMathAlphabet{\mathsf}{bold}{OT1}{cmss}{bx}{n}
```

La prima riga imposta **Computer Modern sans** Medium come predefinito per `\mathsf` in tutte le versioni matematiche. La seconda riga indica al LaTeX di utilizzare **Computer Modern sans** grassetto esteso nella versione matematica audace.

```tex
\SetMathAlphabet{cmd}{version}{encoding}{family}{series}{shape}
```

Come avrete indovinato dall'esempio precedente, `\setmathalphabet` prende sei argomenti: l'identificatore di alfabeto matematico, il nome della versione matematica per il quale stai definendo un set-up speciale e quattro parametri per identificare il carattere con cui si sta associando la configurazione.

Come abbiamo notato in precedenza, puoi ridefinire un identificatore di alfabeto di matematica esistente usando `\dichiarathalphabet`. In tal caso, tutte le precedenti dichiarazioni `\setmathalphabet` per questo identificatore vengono rimosse dalla memoria interna del LaTeX. Quindi l'identificatore uscirà lo stesso in tutte le versioni matematiche a meno che tu non aggiunga nuove dichiarazioni `\setmathalphabet` per esso.

## 8.4. Fonti di sintonia in formule con pacchetti AMS-Latex

Il pacchetto *amsfonts *(e *amssymb*) definisce due alfabeti di matematica: l'alfabeto Euler Fraktur (`\MathFrak`) e l'alfabeto BLASCHBOARD BOLD (`\MATHBB`). Vedi l'esempio seguente.

```tex
\usepackage{amsfonts}
% -------------------------------------------------------------------------------
$ \forall n \in \mathbb{N} : \mathfrak{M}_n \leq \mathfrak{A} $
```

![Amsfonts Math Alphabet Identifiers](/tex/images/java/tutorial/latex-ams-math-8-14.png)

## 5. Bold Math Carattere Stile. Il pacchetto `BM`

Solo per lettere latine, puoi usare il comando `\mathbf`. Per tutto il resto, c'è il pacchetto `BM`. Basta caricarlo e utilizzare `\bm` per creare qualsiasi formula audace e bella come consentono i caratteri disponibili.

L'esempio seguente mostra molti modi per utilizzare i comandi `\bm` e `\mathbf`. Mostra anche una strategia per definire i nomi stenografici per simboli audaci che si verificano frequentemente, usando sia `\commisand` standard in LaTeX, e `\bmdefine`, che è fornito dal pacchetto` BM`. Si noti che `\mathbf {xy}` non è identico a `\bm {xy}`. Il primo produce audace romano "**xy**" e il secondo produce "*** xy***" (audace matematica corsivo).

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

![Utilizzando il pacchetto BM](/tex/images/java/tutorial/latex-ams-math-8-15.png)

In questo esempio `bm` cerca del suo meglio per soddisfare le richieste di versioni audaci di singoli simboli e lettere. Ma se guardi da vicino, vedrai che i risultati non sono sempre ottimali. Ad esempio, la somma e gli operatori di prodotti sono realizzati con una tecnica nota come *povera l'uomo audace *, in cui il simbolo è sovrastimato tre volte con lievi offset. Inoltre, le staffe ricci non sono affatto audaci. Tali svantaggi non possono essere evitati perché per alcuni simboli non esiste semplicemente una variante audace quando si usano i caratteri **Modern** Math Math.

Quali sono le regole esatte che `\bm` segue per produrre forme audaci dei simboli nel suo argomento? In generale, utilizza il fatto che il LaTeX include una versione di matematica **Bold** (accessibile tramite `\Boldmath`) per la composizione di un'intera formula in grassetto (sono disponibili e configurati i caratteri audaci forniti). Per ogni simbolo, il comando `\bm` guarda questa versione matematica per vedere cosa sarebbe stato fatto in quella versione. Se il carattere selezionato per il simbolo è diverso da quello selezionato nella versione matematica normale, quindi descrive il simbolo in questo carattere audace, ottenendo un risultato perfetto (supponendo che la versione matematica audace sia stata impostata correttamente). Se i caratteri in entrambe le versioni sono identici, presuppone che non vi sia una variante audace disponibile e applica il povero uomo in grassetto.

> Carica il pacchetto `bm` dopo i pacchetti che modificano la configurazione esistente dei font matematici!

La situazione è ancora più complessa con delimitatori, come `\biggl \lbrace` nell'esempio. TEX in genere compone un delimitatore da un glifo scelto per abbinare un'altezza richiesta da una sequenza di dimensioni diverse. Questi glifi possono essere posizionati in caratteri diversi e una dimensione particolare può o meno avere varianti audaci. Tutto questo insieme rende impossibile per `\bm` determinare in modo affidabile se deve applicare l'audace degli uomini poveri. Pertanto, compromette il delimitatore usando qualsiasi caratteristica offerta dalla versione matematica audace. Con i caratteri di matematica **Modern** moderni, solo le dimensioni del delimitatore più piccole sono disponibili in grassetto; Tutte le altre dimensioni provengono da caratteri che non hanno varianti audaci.

```tex
\usepackage{bm}
% -------------------------------------------------------------------------------
$\bm{\Biggl\lbrace\biggl\lbrace\Bigl\lbrace\bigl \lbrace \lbrace
  \mathcal{Q}
  \rangle \bigr\rangle\Bigr\rangle\biggr\rangle
\Biggr\rangle}$
```

![Delimitatori realizzati (e non resi) in grassetto dal comando \ bm](/tex/images/java/tutorial/latex-ams-math-8-16.png)

Normalmente, se un comando che si occupa di essa stesso è all'interno dell'argomento di `\bm`, allora quel comando deve essere completamente incluso nell'argomento di `\bm`. Di conseguenza, tutte le parti del materiale da composizione saranno in grassetto. Se hai bisogno che l'output di un comando con argomenti sia solo parzialmente audace, allora dovresti fare quanto segue. Dovresti mettere i simboli che non vuoi essere audace in un `\mbox` e ripristinare esplicitamente la versione matematica all'interno del contenuto della casella usando `\Unboldmath`. Tex considera un `\mbox` come un simbolo della classe *ordinaria*. Pertanto, per ottenere la spaziatura giusta, potresti doverlo circondare da un `\mathbin`,`\mathrel` o `\mathop`.

```tex
\usepackage{amsmath,bm}
% -------------------------------------------------------------------------------
$ \bm{\sqrt[2]{x \times \alpha}} $ but
$ \bm{\sqrt[2]{x \mathbin{\mbox{\unboldmath$\times$}} \alpha}} $
or the similar
$ \bm{\sqrtsign}{\bm{x} \times \bm{\alpha}} $
```

![\ bm con comandi che prendono argomenti](/tex/images/java/tutorial/latex-ams-math-8-17.png)

Fortunatamente, raramente sono richieste operazioni così complesse. Nella maggior parte dei casi che coinvolgono comandi con argomenti, solo parti dell'argomento devono essere rese audaci. E questo può essere ottenuto usando il comando `\bm` all'interno di tali argomenti. Come per `\sqrtsign` nell'esempio precedente, per il caso comune di accenti audaci,`\bm` è appositamente programmata per consentire all'argomentazione dell'accento di essere al di fuori del proprio argomento. Tuttavia, se hai bisogno di tali accenti regolarmente, è meglio definire le tue abbreviazioni, come nell'esempio seguente.

***Miglioramento delle prestazioni***

Sebbene `\bmdefine \ bpi {\ pi}` sembri essere semplicemente scorciatoia per `\newCommand \ bpi {\ bm {\ pi}}`, in realtà la verità è quasi l'opposto: `\bm` definisce un nuovo comando temporaneo nascosto usando`\bmdefine` e quindi usa immediatamente questo comando temporaneo per produrre il simbolo audace. In altre parole, `\bmdefine` fa tutto il duro lavoro! Se usi frequentemente, ad esempio, qualcosa che viene definito tramite `\bm {\ alpha}`, allora viene eseguito ogni volta un nuovo `\bmdefine`. Se fornisci la definizione `\bmdefine \ balpha {\ alpha}` nel preambolo, allora `\bmdefine` fa il suo lavoro che richiede tempo solo una volta, non importa quante volte viene utilizzata`\Balpha`.

```tex
\usepackage{bm}
\bmdefine\bhat{\hat}
% -------------------------------------------------------------------------------
$\hat a \neq \bm{\hat a} \neq \bm\hat a = \bhat a\neq \bm\widehat a$
```

![Ottimizzato rendendo gli accenti in grassetto con il comando \ bm](/tex/images/java/tutorial/latex-ams-math-8-18.png)

Questo esempio mostra anche che gli accenti di larghezza variabile (ad esempio, `\widehat`) condividono una carenza con i delimitatori: nel **configurazione di matematica moderna** moderna provengono da un carattere per il quale non è disponibile alcuna variante audace.