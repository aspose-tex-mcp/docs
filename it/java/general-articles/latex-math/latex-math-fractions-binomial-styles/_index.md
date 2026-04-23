---
translation: true
template: /templates/_template-java.md
linktitle: Frazioni, coefficienti binomiali e stili di matematica
title: 5. Frazioni, coefficienti binomiali e stili di matematica
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: Formule di matematica in LaTeX, LaTeX, matematica in LaTeX, frazioni di matematica in LaTeX, coefficienti binomiali di matematica in LaTeX, stili di matematica in LaTeX
description: Scopri la composizione di tali costruzioni di matematica come frazioni, coefficienti binomiali, ecc. E gli stili di matematica in cui le formule di TEX Typets.
lastmod: "2025-06-13"
---

{{<section overview>}}

Un'altra cosa comune che potresti trovare nelle formule di matematica sono le frazioni e altre costruzioni in cui qualcosa come un numeratore è posizionato sopra qualcosa come un denominatore. Un esempio di quest'ultimo sono i coefficienti binomiali.

![Oggetti matematici simili alla frazione](/tex/images/java/tutorial/latex-math-5-1.png)

È possibile ottenere queste tre formule come equazioni visualizzate digitando `$1\over2$`, `$n+1\over3$` e `$
+1\choose3﻿---
translation: true
template: /templates/_template-java.md
linktitle: Frazioni, coefficienti binomiali e stili di matematica
title: 5. Frazioni, coefficienti binomiali e stili di matematica
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: Formule di matematica in LaTeX, LaTeX, matematica in LaTeX, frazioni di matematica in LaTeX, coefficienti binomiali di matematica in LaTeX, stili di matematica in LaTeX
description: Scopri la composizione di tali costruzioni di matematica come frazioni, coefficienti binomiali, ecc. E gli stili di matematica in cui le formule di TEX Typets.
lastmod: "2025-06-13"
---

{{<section overview>}}

Un'altra cosa comune che potresti trovare nelle formule di matematica sono le frazioni e altre costruzioni in cui qualcosa come un numeratore è posizionato sopra qualcosa come un denominatore. Un esempio di quest'ultimo sono i coefficienti binomiali.

![Oggetti matematici simili alla frazione](/tex/images/java/tutorial/latex-math-5-1.png)

.

Il comando `\over` si applica a tutto nella formula a meno che tu non lo racchiudica in una sottomissione specifica con parentesi graffe, nel qual caso `\over` si applica a tutto in quella sottomissione.

![Frazioni](/tex/images/java/tutorial/latex-math-5-2.png)

Non è possibile utilizzare `\over` due volte nella stessa sottomissione, cioè digitare `a\over b\over2`. Invece, dovresti specificare esplicitamente ciò che accompagna cosa:

![Frazioni nidificate](/tex/images/java/tutorial/latex-math-5-3.png)

Sembra che entrambe le formule non abbiano un bell'aspetto. In tali casi, di solito è meglio convertire le frazioni in una "forma tagliata". Ad esempio, le ultime due formule dovrebbero essere digitate come segue:

![Frazioni nelle loro forme tagliate](/tex/images/java/tutorial/latex-math-5-4.png)

Ecco esempi più complessi:

![Frazioni nelle loro forme tagliate](/tex/images/java/tutorial/latex-math-5-5.png)

Guardando gli esempi sopra, potresti aver notato che le lettere e altri simboli a volte si riducono quando appaiono in frazioni, proprio mentre si riducono quando sono in abbonamenti o apice. Parliamo ora del modo in cui Tex sceglie le dimensioni dei simboli. Tex ha otto stili in cui può trattare le formule:

 * Visualizza stile (per formule visualizzate su righe da sole)
 * stile di testo (per formule incorporate nel testo)
 * Stile di script (per subformule usate come apice o abbonamenti)
 * Stile Scriptscript (per aprile o abbonamenti di secondo ordine)
e quattro stili "angusti" che sono quasi gli stessi tranne che gli abbonamenti e i spietati non sono aumentati così tanto. Faremo riferimento agli otto stili come *d*, *d ' *, *t *, *t' *, *s*, *s ' *, *ss *, *ss' *, dove *d*è uno stile di visualizzazione, *d ' *è uno stile di visualizzazione angusta, *t *è stile di testo, ecc. Tex usa anche tre dimensioni per digitare le formule matematiche: dimensione del testo, dimensione della sceneggiatura e scriptscript.

Per scrivere una formula nel testo in esecuzione, lo racchiude in `$ ... $`; Questo produce la formula con stile *t *. Oppure puoi racchiuderlo in `$$ ... $$` per ottenere una formula visualizzata; Questo visualizza la formula con stile *d*. Le subformule di una formula possono essere in stili diversi. Una volta che conosci lo stile, puoi determinare le dimensioni del tipo che Tex utilizzerà:

![Stili per la mappatura delle dimensioni](/tex/images/java/tutorial/latex-math-5-6.png)

Non esiste uno stile "*sss*" poiché tali piccoli simboli sarebbero ancora meno leggibili di quelli di Scriptscript.

![Stili di abbonamenti e superstctipts a seconda di uno stile di formula](/tex/images/java/tutorial/latex-math-5-7.png)

Ad esempio, se `x^{a_b}` è impostato nello stile *D*, `a_b` sarà impostato nello stile *S* e `b` nello stile *SS*; il risultato è ![Radici di grado arbitrario](/tex/images/java/tutorial/latex-math-5-8.png)

Non abbiamo ancora visto alcuna differenza tra gli stili *d* e *t*. C'è in realtà una leggera differenza nel posizionamento degli esponenti, sebbene in ciascun caso sia utilizzata la dimensione dello script. Ma c'è una grande distinzione tra gli stili *d* e *t* in caso di frazioni:

![Stili di un denominatore e un numeratore a seconda di uno stile di frazione](/tex/images/java/tutorial/latex-math-5-9.png)

Quindi, se digiti `$1\over2$` (in un testo) ottieni lo stile *s* sopra lo stile *s'*; ma se digiti `$$1\over2$$` ottieni lo stile *t* sopra lo stile *t'* in una formula visualizzata.

Infine, `\sottoline` non cambia lo stile. Accenti matematici e i comandi `\sqrt` e `\overline` cambiano stili non screpolati nei loro controparti anguste che mantengono stili angusti.
Può succedere che non ti piace lo stile che Tex seleziona in base alle sue regole. Sei libero di specificare lo stile desiderato digitando `\displaystyle` o`\textstyle` o `\scriptstyle` o`\scriptscriptstyle`; Lo stile selezionato si applicherà fino alla fine della formula o della subformance o fino a quando non si seleziona un altro stile. Ad esempio, `$$ N+\ ScriptStyle n+\ ScriptscriptStyle n. $$` produce il seguente display:

![Controllo manuale in stile](/tex/images/java/tutorial/latex-math-5-10.png)

Mostra che anche il segno più si riduce man mano che lo stile cambia e che Tex non pone spazio + negli stili di sceneggiatura.

Diamo un'occhiata a un altro esempio: una frazione continua.

![Una frazione continua](/tex/images/java/tutorial/latex-math-5-11.png)

Puoi ottenerlo digitando

```tex
$$a_0+{1\over\displaystyle a_1+
        {\strut 1\over\displaystyle a_2+
          {\strut 1\over\displaystyle a_3+
            {\strut 1\over a_4}}}}$$
```

Senza `\strut` e `\DisplayStyle` in questa formula, il risultato sarebbe diverso:

![Una frazione continua senza abbellire i trucchi](/tex/images/java/tutorial/latex-math-5-12.png)

Latex definisce la macro `\frac` che consente di specificare le frazioni usando un'altra sintassi:`\frac {a} {b} `è equivalente a` a \ over b` e `\frac12` è equivalente a` 1 \ over2`.

C'è un'altra operazione `\in cima" in tex, che è come `\over` tranne per il fatto che non disegna la linea di frazione:

![Il comando \ OPP](/tex/images/java/tutorial/latex-math-5-13.png)

Il formato in LaTeX definisce anche `\scelto`, che è come`\in cima 'ma racchiude il risultato in parentesi:

![La macro \ scegli](/tex/images/java/tutorial/latex-math-5-14.png)

Si chiama `\scelto` perché è una notazione comune per il coefficiente binomiale che dice quanti modi ci sono di scegliere * k * cose da * n * cose.

I comandi `\over`,`\inopp` e `\scelgono` non possono essere miscelati tra loro. Ad esempio, `$$ n \ Scegli k \ over 2 $$` è illegale. È necessario usare il raggruppamento per ottenere `$$ {n \ Scegli k} \ over2 $$` o `$$ n \ scelto {k \ over2} $$`.

Tex ha il comando `\sopra` che è una versione generalizzata di`\over` e `\inopp`. In questo comando si specificano lo spessore esatto della regola della linea digitando `\sopra <meen>`. Per esempio, 

```tex
$$\displaystyle{\frac{a}{b}\above1pt\displaystyle{\frac{c}{d}}$$
```

Produrrà una frazione composta con una regola spessa 1pt tra le frazioni nel numeratore e il denominatore:

![La macro \ sopra](/tex/images/java/tutorial/latex-math-5-15.png)