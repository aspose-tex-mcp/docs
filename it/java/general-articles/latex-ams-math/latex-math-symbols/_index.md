---
translation: true
template: /templates/_template-java.md
linktitle: Simboli matematici in LaTeX
title: 9. Simboli nelle formule di matematica
weight: 90
url: /java/latex-math-symbols/
keywords: ams-latex, amsmath, amsfonts, amssymb, classi di simboli matematici LaTeX, pacchetto stmaryrd, font St Mary Road
description: Impara la classificazione dei simboli matematici in TeX e l'accesso a simboli di varie classi utilizzando i comandi di TeX standard (LaTeX) e il pacchetto amssymb.
lastmod: "2026-03-30"
---

{{<section overview>}}

Le tabelle in questo articolo elencano la vasta gamma di simboli matematici forniti dai pacchetti AMS-Latex, compresi i comandi per accedere a ciascun simbolo. Includono anche i simboli supplementari del font **St Mary Road** progettato da Allan Jeffrey e Jeremy Gibbons. Questo pacchetto si estende **Computer Modern** e AMS Symbol Font Collections e normalmente dovrebbe essere caricato in aggiunta a `amssymb`, ma sempre dopo. Fornisce simboli extra per campi come la programmazione funzionale, l'algebra di processo, la teoria del dominio, la logica lineare e molti altri.

Le tabelle indicano quali pacchetti extra devono essere caricati per utilizzare ciascun comando simbolo. I simboli con nomi di comandi in nero sono disponibili nel LaTeX standard. I simboli con nomi di comandi in blu richiedono il caricamento di `amsmath`, `amssymb` o `stmaryrd`. Se necessario, l'ulteriore classificazione viene data dai contrassegni: <sup>(*StM*)</sup> significa un simbolo di `stmaryrd` quando la tabella contiene anche simboli di altri pacchetti; <sup>(*kernel*)</sup> segna i simboli disponibili nel LaTeX standard ma solo combinando due o più glifi, mentre nel pacchetto indicato esiste un singolo glifo; e <sup>(*var*)</sup> segna i "simboli alfabetici" (di tipo `\mathalpha`) che cambiano aspetto se usati all'interno dell'ambito di un [identificatore di alfabeto matematico](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers).

## 9.1. Classi di simboli matematici in LaTeX

La classificazione primaria dei simboli matematici è legata al loro significato nell'uso tecnico. Nella tipografia matematica, questa classificazione definisce il layout della formula. In particolare, il formattatore matematico di TeX regola lo spazio orizzontale su entrambi i lati di ciascun simbolo in base alla sua classe matematica. Questa classificazione rende anche alcune distinzioni più fini, ad esempio tra accenti e simboli semplici e nel suddividere l'enorme elenco dei simboli di *relazione* in diverse tabelle.

L'impostazione per la matematica inserisce ciascun simbolo in una di queste classi: *Ordinary* (Ord), *Operator* (Op), *Binary* (Bin), *Relation* (Rel), *Opening* (Open), *Closing* (Close) o *Punctuation* (Punct). La classe del simbolo può essere esplicitamente modificata usando i comandi `\mathord`, `\mathop`, `\mathbin`, `\mathrel`, `\mathopen`, `\mathclose` e `\mathpunct`. Nel prossimo esempio, `\#` e `\top` (entrambi Ord per impostazione predefinita) vengono modificati in un Rel e un Op.

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![Cambiare esplicitamente la classe dei simboli](/tex/images/java/tutorial/latex-ams-math-9-1.png)

Oltre alle classi di cui sopra, alcune sottoformule - soprattutto le frazioni e quelle prodotte da `\left` e `\right` - formano una classe chiamata *interno*, che è esplicitamente disponibile tramite il comando `\mathinner`.

![Classi di simboli e spaziatura](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> Nella tabella, "0" significa "nessuno spazio", "1" significa `\thinmuspace`, "2" significa `\medmuskip`, "3" significa `\thickmuskip`, "*" significa "impossibile". Le voci in grassetto indicano che la spaziatura corrispondente non viene aggiunta negli stili di scrittura matematici.

TeX gestisce la spaziatura all'interno delle formule semplicemente identificando la classe di ciascun oggetto in una formula e quindi aggiungendo spazio tra ciascuna coppia di oggetti adiacenti come definito dalla tabella precedente. Questa tabella è codificata nelle routine di composizione matematica di TeX e quindi non può essere modificata dai pacchetti macro.

Un simbolo *Binary* viene trasformato in un simbolo *Ordinary* ogni volta che non è preceduto e seguito da simboli di una natura compatibile con un'operazione binaria. Ecco perché alcune voci nella tabella sono contrassegnate come impossibili. Ad esempio, `$ +x $` dà +*x* (un plus unario) e non +*x*. Quest'ultimo può essere prodotto da `$ {}+x $`.

Considera la seguente formula (i valori predefiniti vengono modificati per mostrare gli spazi aggiunti più chiaramente):

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\thinmuskip, \medmuskip e \thickmuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

TeX identifica gli oggetti come Ord, Bin, Ord e so on, quindi inserisce gli spazi come segue:

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

Il meno di fronte a `\max` viene trasformato in un *ordinario* perché un *binario* non può seguire una *relazione*.

In una costruzione "`\left...\right`", l'intera sottoformula delimitata dalla costruzione diventa un singolo oggetto di classe *interno*. Al contrario, comandi come `\Bigl` e `\Bigr` producono simboli individuali delle classi *Opening* e *Closing*, rispettivamente. La differenza tra loro viene rivelata nella tabella di spaziatura sopra. Sebbene possano provocare delimitatori di uguale dimensione verticale, possono sorgere differenze di spaziatura a seconda di oggetti adiacenti nella formula. Ad esempio, *Ordinary* seguito da *Opening* non ottiene spazio, mentre *Ordinary* seguito da *interno* è separato da uno spazio sottile. Gli spazi all'interno della sottoformula all'interno di una costruzione "`\left...\right`" sono fatti come previsto, a partire da un simbolo *Opening* e terminando con un simbolo di *Closing*.


```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\left...\right e \Bigl...\Bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

In sintesi, è meglio verificare che un simbolo appartenga alla classe desiderata, piuttosto che cercarlo nelle tabelle che seguono.

## 9.2. Lettere, numeri e altri simboli *Ordinary*

Le lettere latine ASCII non accentate e le cifre numeriche arabe sono tutte definite "simboli alfabetici". Il font in cui sono scritte può variare. Nelle formule matematiche, il font predefinito per le lettere latine è il corsivo, mentre per le cifre arabe è quello verticale/romano. I simboli alfabetici sono tutti di classe *Ordinary*.

![Simboli di classe \mathord (greco)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

A differenza delle lettere latine, le lettere greche matematiche non sono più strettamente correlate ai glifi utilizzati per la composizione del testo greco normale. A causa di una curiosa congiuntura del XVIII secolo, nella principale tradizione europea della tipografia matematica il font predefinito per le lettere greche minuscole nelle formule matematiche è il corsivo mentre per le lettere greche maiuscole è quello verticale/romano. (In fisica e chimica, ad esempio, le tradizioni tipografiche sono leggermente diverse.)

Le lettere greche maiuscole nelle prime righe della seguente tabella sono anche simboli alfabetici il cui font varia, con il valore predefinito verticale/romano. Ci sono lettere greche maiuscole, ognuna delle quali ha la stessa apparenza di una lettera latina (ad esempio, *A* e *Alpha*, *B* e *Beta*, *K* e *Kappa*, *O* e *Omicron*). Queste lettere non sono presenti nella tabella. Per lo stesso motivo, non esiste un omicron minuscolo. In pratica, le lettere greche che sembrano lettere latine non sono usate nelle formule matematiche.

![Lettere greche](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> I simboli in blu richiedono il pacchetto `amssymb`. <sup>(*var*)</sup> indica un simbolo alfabetico variabile.

La tabella successiva elenca altri simboli a forma di lettere della classe *Ordinary*. I primi quattro sono lettere ebraiche.

![Simboli di classe \mathord (a forma di lettera)](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> I simboli in blu richiedono il pacchetto `amssymb`.

La tabella successiva elenca i simboli rimanenti nella classe *Ordinary*, inclusi alcuni comuni segni di punteggiatura. Questi si comportano come lettere e cifre, quindi non hanno mai spazio extra intorno a loro.

![Simboli di classe \mathord (vari)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> I simboli in blu richiedono il pacchetto `amssymb` o, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

> Si noti che il punto esclamativo, il punto e il punto interrogativo non vengono considerati punteggiatura nelle formule.

> Sinonimi: negazione logica - `\lnot`, `\neg`; `|` - `\vert`, `|`; `||` - `\Vert`, `\|`.

Un errore comune è usare questi simboli direttamente come operatori *Binary* o simboli di *Relation*, senza usare un comando di simbolo matematico correttamente definito per quel tipo. Pertanto, se usi comandi come `\#`, `\square` o `\&`, controlla attentamente di ottenere gli spazi tra i simboli corretti o, ancora meglio, definire il tuo comando di simbolo.

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![Dichiarazione simboli matematici](/tex/images/java/tutorial/latex-ams-math-9-9.png)

Il comando `\DeclareMathSymbol` viene utilizzato per dichiarare il proprio nome di simbolo.

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

Il primo argomento è il nome del comando scelto. Il secondo argomento è uno dei comandi corrispondenti alla classe del simbolo. Il terzo argomento identifica il font del simbolo da cui esso dovrebbe essere recuperato. Il quarto argomento fornisce la posizione del simbolo nella codifica del font, un valore decimale, ottale o esadecimale. I valori corretti per gli argomenti possono essere trovati più facilmente osservando le definizioni nel file `amssymb.sty` o `fontmath.ltx` (per i simboli fondamentali). Ad esempio, abbiamo cercato `\neq` e `\square`, abbiamo sostituito il `\mathord` in ogni caso e infine abbiamo dato un nuovo nome al simbolo risultante.

## 9.3. Accenti matematici

La tabella seguente elenca i comandi di accento disponibili nelle formule. La maggior parte di essi è definita in TeX standard. Vedi [qui](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible) per informazioni sugli accenti estensibili. Quando aggiungi un accento matematico a un simbolo, il risultato è un simbolo della classe *Ordinary*.

![Accenti matematici, che producono sottoformule di classe \mathord](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> Gli accenti in blu richiedono il pacchetto `amsmath`.

> Gli ultimi due accenti sono disponibili in diverse larghezze, e viene automaticamente utilizzato quello più grande.

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ ma } a \tilde{=} b
\text{ che non è } a \mathrel{\tilde{=}} b \]
```

![Creare un simbolo di relazione da un simbolo accentuato](/tex/images/java/tutorial/latex-ams-math-9-11.png)

Altri modi per posizionare i simboli sopra i simboli di *relazione* sono mostrati [qui](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations). Quando si aggiunge un accento a una *i* o *j* nelle formule matematiche, è meglio usare le varianti senza punto `\imath` e `\jmath`.

## 9.4. *Simboli dell'operatore binario*

Ci sono più di 100 simboli di classe *Binary* tra cui scegliere. La maggior parte di essi è elencata nella tabella seguente. Alcuni di essi sono disponibili anche come simboli di *relazione*, sebbene con nomi diversi.

![Simboli di classe \mathbin (vari)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> I simboli in blu richiedono il pacchetto `amssymb` o, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

> I triangoli verso sinistra e verso destra sono disponibili anche come simboli di *relazione*.

> Il pacchetto `stmaryrd` trasforma in modo confusionale i simboli *Binary* `\bigtriangleup` e `\bigtriangledown` in *Operatori*, lasciando solo i sinonimi `\varbigtriangleup` e `\varbigtriangledown` per le forme di operatore *Binary*.

Il pacchetto `amssymb` offre alcuni simboli a forma di riquadro da utilizzare come operatori *Binary*; molti altri sono aggiunti da `stmaryrd`. Vedi la tabella successiva.

![Simboli di classe \mathbin (box)](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> Tutti i simboli richiedono il pacchetto `amssymb` oppure, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

È possibile caricare il pacchetto `stmaryrd` con l'opzione `heavycircles`. Di conseguenza, ogni comando del simbolo del cerchio della tabella successiva che inizia con `\var` scambia la sua definizione con il comando corrispondente senza "var"; ad esempio, il simbolo `\varodot` diventa `\odot` e viceversa.

![Simboli di classe \mathbin (cerchi)](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> I simboli in blu richiedono il pacchetto `amssymb` o, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

> L'opzione `heavycircles` del pacchetto `stmaryrd` ha effetto su tutti i comandi che iniziano con `\var` e sulle loro varianti normali.

## 9.5. Simboli di relazione

La classe di simboli di relazione binari è ancora più vasta di quella degli operatori *Binary*. La tabella successiva elenca i simboli per l'uguaglianza e l'ordine. È possibile barrare qualsiasi simbolo di relazione precedendolo con il comando `\not`. Il simbolo negato rappresenta il complemento (o negazione) delle relazioni.

![Simboli di classe \mathrel (eguaglianza e ordine)](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> I simboli in blu richiedono il pacchetto `amssymb` oppure, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![Negare una relazione](/tex/images/java/tutorial/latex-ams-math-9-16.png)

Questo metodo generico per negare un simbolo di relazione non dà sempre buoni risultati, specialmente con simboli più grandi, perché la barra sarà sempre delle stesse dimensioni, posizione e pendenza. Per questo motivo, sono disponibili anche alcuni "simboli negati" appositamente progettati. Vedi l'elenco nella tabella successiva.

![Simboli di classe \mathrel (eguaglianza e ordine negati)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> I simboli in blu richiedono il pacchetto `amssymb`.

Se è disponibile una scelta, di solito è preferibile utilizzare i glifi appositamente progettati. Per capire perché, confronta i simboli nel prossimo esempio.

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![Simboli di relazione negati composti e appositamente progettati](/tex/images/java/tutorial/latex-ams-math-9-18.png)

La tabella successiva elenca i simboli di relazione per insiemi e inclusioni.

![Simboli di classe \mathrel (insiemi e inclusioni)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> I simboli in blu richiedono il pacchetto `amssymb` oppure, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

E ora le negazioni dei simboli di relazione per insiemi e inclusioni.

![Simboli di classe \mathrel (insiemi e inclusioni negati)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> I simboli in blu richiedono il pacchetto `amssymb`.

La tabella successiva elenca i simboli di relazione a forma di freccia. Alcune costruzioni di frecce estensibili che producono simboli di relazione composti sono descritte [qui](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible).

![Simboli di classe \mathrel (frecce)](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> I simboli in blu richiedono il pacchetto `amssymb` oppure, se contrassegnati con <sup>(*StM*)</sup>, il pacchetto `stmaryrd`.

E qui ci sono i simboli di relazione negati a forma di freccia.

![Simboli di classe \mathrel (frecce negate)](/tex/images/java/tutorial/latex-ams-math-9-22.png)

> I simboli in blu richiedono il pacchetto `amssymb`.

Esistono altri elementi (oltre a `\not` usato per negare simboli di relazione generali) che sono stati appositamente progettati per negare o estendere i simboli a forma di freccia. Vedi la tabella successiva.

![Simboli di classe \mathrel (negazione ed estensioni di freccia)](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> I simboli in blu richiedono il pacchetto `stmaryrd`.

> Questi simboli servono per la combinazione, principalmente con le frecce; ad esempio, `\longarrownot\longleftarrow`.

> Usa `\joinrel` per "incollare" insieme i simboli relazionali, ad esempio, `\lhook\joinrel\longrightarrow`.

> Le dimensioni di questi simboli li rendono inadatti ad altri usi.

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![Negazioni di freccia](/tex/images/java/tutorial/latex-ams-math-9-24.png)

Finalmente, di seguito sono riportati altri simboli di *relazione* vari.

![Simboli di classe \mathrel (vari)](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> I simboli di *relazione* in blu richiedono il pacchetto `amssymb`.

> `\therefore` è un simbolo di *relazione*, quindi la sua spaziatura potrebbe non essere quella prevista negli usi comuni.
