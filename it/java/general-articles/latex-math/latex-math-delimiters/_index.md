---
translation: true
template: /templates/_template-java.md
linktitle: Delimitatori
title: 7. Delimitatori
weight: 70
url: /java/latex-math-delimiters/
keywords: Latex, formule di matematica in LaTeX, matematica in LaTeX, delimitatori di matematica in LaTeX, parentesi di matematica in LaTeX, parentesi di matematica in LaTeX, parentesi di matematica in LaTeX
description: Questo articolo discute come dividere logicamente le formule in sottocule con diversi tipi di delimitatori.
lastmod: "2025-06-13"
---

{{<section overview>}}

Qualunque sia la formula di matematica grande, Tex conosce un modo per rendere alcuni simboli abbastanza grandi da avere un aspetto adeguato. Ad esempio, il risultato della digitazione

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

Mostra una varietà di radicali disponibili o radicali, segni:

![Radicali di diverse dimensioni](/tex/images/java/tutorial/latex-math-7-1.png)

I tre segni più grandi qui sono gli stessi, ad eccezione di un segmento verticale che viene ripetuto tutte le volte necessarie per raggiungere le dimensioni richieste. Allo stesso tempo, i segni più piccoli sono personaggi distinti tratti dai caratteri di matematica di Tex.

Qualcosa di simile accade con le parentesi e altri cosiddetti simboli "delimitanti". Tali simboli sono importanti in matematica, perché forniscono indizi visivi sulla struttura sottostante delle espressioni complesse. In altre parole, limitano i confini delle singole sottocolle. Ecco l'elenco dei 22 delimitatori di base forniti dal LaTeX:

![I 22 delimitatori di base definiti in LaTeX](/tex/images/java/tutorial/latex-math-7-2.png)

Per ottenere una versione leggermente più grande di uno di questi simboli, basta digitare rispettivamente `\bigl` o`\bigr` per l'apertura o la chiusura dei delimitatori. Questo rende le formule con delimitatori nidificati più facili da leggere:

![Gli esempi dell'utilizzo di \ grandi delimitatori](/tex/images/java/tutorial/latex-math-7-3.png)

I delimitatori `\big` sono appena più grandi di quelli normali in modo che la differenza possa essere notata, eppure abbastanza piccola da essere usata nel testo di un paragrafo:

![I \ grandi delimitatori rispetto a quelli normali](/tex/images/java/tutorial/latex-math-7-4.png)

Puoi ottenere un altro passo Simboli più grandi adatti per i display, se digiti `\bigl` e `\bigr` invece di `\bigl` e `\bigr`:

![I \ grandi delimitatori](/tex/images/java/tutorial/latex-math-7-5.png)

Queste sono più alte del 50% rispetto alle versioni nel passaggio precedente. Le formule visualizzate usano spesso delimitatori ancora più alti (doppio di `\big`). Puoi ottenerli digitando `\biggl` e `\biggr`:

![I \ Bigg Delimiters](/tex/images/java/tutorial/latex-math-7-6.png)

Infine, puoi digitare versioni `\biggl` e `\biggr`, 2,5 volte più alte come i delimitatori `\bigl` e `\bigr`:

![I \ Bigg Delimiters](/tex/images/java/tutorial/latex-math-7-7.png)

Il LaTeX fornisce anche comandi `\bigm`,`\bigm`, `\biggm` e `\biggm` per produrre delimitatori che possono essere usati nel mezzo delle formule. Un tale delimitatore si comporta come una relazione, quindi Tex mette un po 'di spazio su entrambi i lati:

![Delimitatori nel mezzo di formule](/tex/images/java/tutorial/latex-math-7-8.png)

È anche possibile dire solo `\big`,`\big`, `\bigg` o`\bigg` per produrre un delimitatore che si comporta come una variabile normale. Questi comandi sarebbero principalmente usati con barre e backsheshes:

![Grandi simboli ordinari](/tex/images/java/tutorial/latex-math-7-9.png)

Tex implementa un algoritmo che capisce quanto sia alta una coppia di delimitatori, al fine di racchiudere una determinata sottomissione. Puoi usarlo, invece di decidere se un delimitatore dovrebbe essere `\big` o`\bigg` o altro. Dì solo


```tex
\left<delim1><subformula>\right<delim2>
```

e Tex comporterà una sottospettazione, mettendo i delimitatori specificati a sinistra e a destra. La dimensione dei delimitatori sarà abbastanza grande da coprire la sottomissione:

![Delimitatori impostati da \ sinistra e \ comandi a destra](/tex/images/java/tutorial/latex-math-7-10.png)

Quando usi `\left` e `\a destra` devono essere accoppiati, proprio come le parentesi graffe fanno i gruppi. Non puoi avere `\Left` in una sottospettazione e`\a destra` in un'altra. Inoltre, non puoi digitare cose come `\a sinistra (... {... \ a destra ...}` o `\left (… \ begingroup ... \ a destra) ... \endgroup`. Questo perché tex deve compromettere la sottomarino che appare tra`\left` e `\\ a destra` prima che tu possa decidere i genitori. Quindi puoi digitare qualcosa come `$ [0,1) $` o `$) ($` o addirittura `$) $`. E anche quando usi `\sinistra` e `\a destra`, non devi abbinare i simboli particolari, in modo che `\a sinistra)` o `\a destra (` non causerà un errore.

Ma perché preoccuparsi di conoscere `\bigl` e `\bigr` e altri del loro genere, quando Tex può calcolare automaticamente le dimensioni per `\left` e `\a destra`? Ci sono almeno tre casi in cui vorresti decidere da solo sulla selezione delle dimensioni del delimitatore adeguate:

(1) Basta confrontare le seguenti due formule:

![\ sinistra e \ a destra vs. \ bigl e \ bigr con barre verticali](/tex/images/java/tutorial/latex-math-7-11.png)

In effetti, usare `\left` e `\a destra` non era una scelta saggia, in quanto non riuscivano a capire la dimensione delimitante appropriata per la migliore leggibilità.

(2) D'altra parte, a volte `\sinistra` e `\a destra` scegli un delimitatore più grande di quello che si desidera. Questo accade principalmente quando racchiudono un grande operatore in un display:

![\ sinistra e \ a destra vs. \ bigl e \ bigr con una somma](/tex/images/java/tutorial/latex-math-7-12.png)

L'algoritmo del Tex fa sì che `\sinistra` e `\a destra` alleggerino il `\sum` insieme ai suoi limiti, ma in casi speciali come questo sembra meglio lasciare che i limiti si inseriscano un po '. Quindi i delimitatori `\bigg` sono migliori qui.

(3) Quando è necessario compromettere un'enorme formula visualizzata, devi romperlo in due o più linee. E vuoi assicurarti che i suoi delimitatori di apertura e chiusura abbiano le stesse dimensioni; Ma non puoi usare `\a sinistra` sulla prima riga e`\a destra` sull'ultima, poiché `\sinistra` e `\a destra` devono verificarsi in coppia. L'unica soluzione è usare `\biggl` (per esempio) sulla prima riga e`\biggr` all'ultimo.

> Although `\left` and `\right` usually can make arbitrarily large delimiters, the slashes and angle brackets do have a maximum size. If you ask for really big versions of those symbols you will get the largest ones available.

Puoi anche usare un trucco che produce un cosiddetto delimitatore null (vuoto). Avresti bisogno di un tale delimitatore quando è necessario scrivere una formula che contiene visivamente un solo delimitatore di grandi dimensioni. Per esempio,

![Un delimitatore nullo nei casi](/tex/images/java/tutorial/latex-math-7-13.png)

ha '{' ma no '}'. Può essere prodotto da una costruzione della forma


```tex
$$|x|=\left\{ ... \right.$$ 
```

dove `\a destra. 'Genera il delimitatore nullo giusto.

Il LaTeX fornisce anche alcuni delimitatori in più, che non sono elencati nel set di base di 22 perché sono un po 'speciali. I comandi `\Arrowvert`,`\Arrowvert` e `\Bracevert` producono delimitatori realizzati dalle parti ripetibili delle frecce verticali, doppie frecce verticali e grandi parentesi, rispettivamente, senza punte di freccia o le parti ricci delle parentesi. Producono risultati simili a `\vert` e `\vert`, ma sono circondati da più spazio bianco e hanno un peso diverso. Ci sono anche `\lgroup` e `\rgroup`, che sono costruiti da parentesi graffe senza le parti centrali; e `\lmoustache` e `\rmoustache`, che producono le metà superiore e inferiore di grandi parentesi. Qui ci sono display con le versioni `\big` e `\bigg` di `\vert`,`\vert`, e questi sette delimitatori speciali:

![Ulteriori delimitatori forniti dal LaTeX](/tex/images/java/tutorial/latex-math-7-14.png)

Puoi scoprire che `\lgroup` e `\rgroup` sono piuttosto come parentesi audaci, con curve più nitide agli angoli; Questo li rende attraenti per alcuni display di grandi dimensioni. Nota che non puoi usarli esattamente come parentesi, perché sono disponibili solo nelle dimensioni `\big` e altro ancora.