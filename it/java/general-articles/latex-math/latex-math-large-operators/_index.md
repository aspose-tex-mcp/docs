---
translation: true
template: /templates/_template-java.md
linktitle: 6. Operatori di grandi dimensioni
title: Grandi operatori | Manuale in LaTeX
weight: 60
url: /java/latex-math-large-operators/
keywords: LaTeX, formule di matematica in LaTeX, matematica in LaTeX, matematica in LaTeX grandi operatori, somma del LaTeX, integrale in LaTeX
description: Questo articolo discute come costruire formule matematiche che contengono grandi operatori come somma e integrazione con Tex e LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}

In matematica, ci sono simboli che indicano, ad esempio, le operazioni di "somma" o "integrazione". Si chiamano "grandi operatori" e li digiti proprio mentre digiti simboli e lettere ordinari. La differenza è che Tex sceglierà un simbolo più grande per il grande operatore in stile display di quanto non lo sarà in stile di testo.

![Somma e integrazione senza super/abbonamenti](/tex/images/java/tutorial/latex-math-6-1.png)

Un `\sum` visualizzato si verifica di solito con" limiti ", cioè con sottocule che devono apparire sopra e sotto di esso. I limiti dovrebbero essere digitati come se fossero abbonamenti e sovrascritti;
`$$ \ sum_ {n = 1}^m $$` o `$$ \ sum^m_ {n = 1} $$` entrambi producono

![Somma con limiti](/tex/images/java/tutorial/latex-math-6-2.png)

Le normali convenzioni della composizione matematica presumono che la formula sopra dovrebbe essere cambiata

![Somma senza limiti](/tex/images/java/tutorial/latex-math-6-3.png)

(cioè, senza limiti) se si verifica nel testo anziché in un display. E Tex segue queste convenzioni.

Apscript e abbonamenti sul segno di integrazione non sono impostati come limiti anche nello stile di visualizzazione:

![Integrazione nel testo e in un display](/tex/images/java/tutorial/latex-math-6-4.png)

L'impostazione di abbonamenti e apripisti come limiti fornisce un aspetto migliore se le subformule sono complesse, sebbene assume più spazio sulla pagina. È possibile costringere Tex a elaborare la formula in questo modo digitando `\Limits` immediatamente dopo il`\int`, o `\sum`, o un altro operatore, indipendentemente da quale stile verrà utilizzato nella sottomissione. D'altra parte, i limiti sui segni di somma visualizzati a volte non sono desiderabili. Puoi cambiare la convenzione di Tex digitando `\nolimits` immediatamente dopo il grande operatore.

![Forzando i limiti e nessun limite per la somma e l'integrazione](/tex/images/java/tutorial/latex-math-6-5.png)

Se dici `\Nolimits \ Limits` (ad esempio, alcuni macro come`\int` specificano `\nolimits`), l'ultimo comando ha la precedenza. Il comando `\Displaylimits 'può essere utilizzato per passare alle normali convenzioni di Tex; vale a dire, i limiti verranno visualizzati solo negli stili *d* e *d ' *.

Se hai bisogno di mettere più di una fila di limiti sotto un grande operatore, puoi farlo con `\in cima`. Il modo corretto per digitare la seguente formula è 

```tex
$$\sum_{\scriptstyle0\le i\le m\atop\scriptstyle0<j<n}P(i,j)$$.
```

![Limiti multi-file sotto il segno di somma](/tex/images/java/tutorial/latex-math-6-6.png)

Il comando `\scriptstyle` è necessario qui, altrimenti entrambe le righe del limite sarebbero state nella dimensione di Scriptscript, che è troppo piccola. Questo è un altro raro caso in cui le regole di stile di Tex devono essere annullate.