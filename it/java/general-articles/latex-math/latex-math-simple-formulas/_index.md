---
translation: true
template: /templates/_template-java.md
linktitle: Formule semplici
title: 1. Formule semplici
weight: 10
url: /java/latex-math-simple-formulas/
keywords: LaTeX, formule di matematica in LaTeX, matematica in LaTeX, lettere di matematica in LaTeX, lettere greche in LaTeX, numeri in LaTeX
description: Questo articolo discute come creare semplici espressioni di matematica atomica per formule più complesse con Tex e LaTex.
lastmod: "2025-06-13"
---

{{<section overview>}}

La formula più semplice è una singola lettera '*x*' o una singola cifra '4'. Per inserire tale formula in un testo in LaTeX, si digita rispettivamente `$ x $` o `$ 4 $`. Tutte le formule di matematica sono racchiuse con parentene matematiche speciali (`$`).

Quando digiti `$ x $` il '*x*' esce in corsivo, ma `$ 2 $` produce '2' in tipo romano. In generale, tutti i personaggi sulla tastiera hanno un'interpretazione speciale nelle formule matematiche, secondo le normali convenzioni della stampa matematica. Le lettere indicano lettere corsivi, mentre cifre e punteggi indicano cifre e punteggiatura romana. Un trattino (-) indica un segno meno. La sinistra `$` mette Tex in "Modalità matematica" e quella a destra lo toglie. Quindi, se dimentichi uno `$` o digiti un ulteriore `$`, probabilmente riceverai un messaggio di errore perché Tex si confonderà.

TeX does most of its own spacing in math formulas. At the same time, it ignores any spaces that you put between `$`'s. You can type `$(x + y)/(x - y)$` or `$(x+y) / (x-y)$`, but both will result in a formula ![Abbonamenti e apripisti a caratteri singoli](/tex/images/java/tutorial/latex-math-1-1.png) in which there is a bit extra space surrounding the '+' and '-' signs but none around the '/' sign. So, you don't have to remember the complicated rule of math spacing, and you're free to use spaces in any way you like. When it is necessary to mark the end of control sequences (commands), spaces are still used in the normal way. In most cases TeX's spacing will meet a mathematician's expectations; but if you want to override TeX's spacing rules, you can do so with control sequences, which we will discuss later.

One of the common things you may find in math formulas is the use of Greek letters. In LaTeX you can type `$\alpha, \beta, \gamma, \delta$` to get the first four Greek letters. And `$\Gamma$`, for example, produces a capital gamma letter. Don't confuse the Greek letters `\kappa` and `\nu` with the italic letters *v* and *x*; the Greek `\phi` is different from the slashed zero called `\emptyset`. A lowercase `\epsilon` is different from the symbol denoting membership in a set. Some of lowercase Greek letters have variant forms in LaTeX italic fonts: `$\phi, \theta, \epsilon, \rho$` yields ![Abbonamenti e apripisti a caratteri singoli](/tex/images/java/tutorial/latex-math-1-2.png) while `$\varphi, \vartheta, \varepsilon, \varrho$` yields ![Abbonamenti e apripisti a caratteri singoli](/tex/images/java/tutorial/latex-math-1-3.png)

Oltre alle lettere greche, ci sono molti simboli di matematica come "approssimativamente uguale" (`$ \ circa $`) e "mappe a" (`$ \ mapsto $`). Puoi trovare un elenco completo di queste sequenze di controllo e dei loro simboli corrispondenti [qui](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).