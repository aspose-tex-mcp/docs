---
translation: true
template: /templates/_template-java.md
linktitle: 4. Diversi personaggi nelle formule di matematica
title: Il significato di diversi personaggi nelle formule matematiche
weight: 40
url: /java/latex-math-symbol-classes/
keywords: Formule di matematica in LaTeX, LaTeX, matematica in LaTeX, simboli di matematica in LaTeX, variabili di matematica in LaTeX, operazioni binarie di matematica in LaTeX, relazioni matematiche in LaTeX, accenti di matematica in LaTeX
description: Questo articolo discute la divisione dei simboli di matematica di Tex in classi e il significato di queste classi in matematica.
lastmod: "2025-06-13"
---

{{<section overview>}}

Le 52 lettere (`a` a` z` e `a` a` z`) indicano simboli corsivi, che un matematico chiamerebbe "variabili". Tex li chiama solo "simboli ordinari", perché costituiscono la maggior parte delle formule di matematica. Il LaTeX tratta anche i seguenti 18 caratteri

`` 0 1 2 3 4 5 6 7 8 9! ? . | ` @" ``

Come simboli ordinari, il che significa che non inserisce alcun spazio extra quando questi simboli si verificano uno accanto all'altro o accanto alle lettere. A differenza delle lettere, questi 18 personaggi rimangono in tipo romano in formule.

I tre caratteri `+`, `-` e `*`sono chiamati" operazioni binarie ", perché operano su due parti della formula. L'asterisco (*) è raro, ma si comporta anche come un'operazione binaria. Ecco alcuni esempi di operazioni binarie da composizione quando appaiono accanto ai simboli ordinari:

![Operazioni binarie](/tex/images/java/tutorial/latex-math-4-1.png)

Tex non tratta `/` come un'operazione binaria perché porterebbe a una spaziatura errata in formule come `$ 1/2 $`. Pertanto, Tex tratta `/` come un simbolo ordinario.

Ecco alcuni altri esempi di operazioni binarie:

![Operazioni binarie più complesse](/tex/images/java/tutorial/latex-math-4-2.png)

Per inciso, le operazioni binarie sono trattate come simboli ordinari se non si verificano tra due quantità su cui possono operare. Pertanto, nessun spazio extra in inserito accanto a +, -e * in casi come i seguenti:

![Operazione binaria come simboli ordinari](/tex/images/java/tutorial/latex-math-4-3.png)

I seguenti esempi mostrano che le operazioni binarie possono essere utilizzate come simboli ordinari in apice e abbonamenti:

![Operazione binaria come simboli ordinari in apice e abbonamenti](/tex/images/java/tutorial/latex-math-4-4.png)

Latex tratta i quattro caratteri `=`, `<`, `>` e `:` come "relazioni" perché esprimono una relazione tra due quantità. Tali relazioni hanno un significato piuttosto diverso dalle operazioni binarie e i simboli sono in qualche modo diversamente:

![Relazioni](/tex/images/java/tutorial/latex-math-4-5.png)

I due personaggi ',' (virgola) e ';' (punto e virgola) sono trattati come segni di punteggiatura nelle formule, il che significa che Tex mette un po 'di spazio extra dopo di loro ma non davanti a loro.

![Segni di punteggiatura](/tex/images/java/tutorial/latex-math-4-6.png)

Non è consuetudine mettere spazio extra dopo un "". (periodo) nelle formule, quindi Tex tratta un periodo come un simbolo normale. Se vuoi che il personaggio ":" sia un segno di punteggiatura invece di una relazione, chiamalo solo `\colon`. E se vuoi che una virgola sia trattata come un simbolo normale, mettila solo in parentesi graffe. Tex tratta qualsiasi cosa tra le parentesi graffe come un simbolo normale.

![Colon come punteggiatura e virgola come simbolo ordinario](/tex/images/java/tutorial/latex-math-4-7.png)

I personaggi `(` e `[` sono chiamati "aperture", mentre `)` e `]` sono chiamati "chiusure". Agiscono in modo molto simile a simboli ordinari, ma aiutano Tex a decidere quando un'operazione binaria non viene davvero utilizzata in modo binario.

Infine, il LaTeX si riserva gli altri 10 caratteri:

`\$ % # & ~ {} _ ^`

Non puoi usarli in modalità matematica. Sebbene '{' e '}' specifichi il raggruppamento, i comandi `\{` e `\}` possono essere usati per ottenere '{' come apertura e '}' come chiusura.

I caratteri speciali `^` e `_` non dovrebbero essere usati se non nelle formule. Al contrario, i nomi dei simboli di matematica come `\alpha` e `\approssimale`, e i comandi per operazioni di matematica come `\overline`, non devono apparire nel testo normale. Inoltre, una linea vuota o `\par` non è consentita in modalità matematica.
I matematici piace anche usare accenti sulle lettere come un modo efficace per indicare relazioni tra oggetti matematici. Estende inoltre notevolmente il numero di simboli disponibili senza aumentare il numero di caratteri necessari. Gli accenti matematici sono in qualche modo diversi dagli accenti utilizzati nel testo ordinario. La spaziatura non è la stessa; Tex segue le regole speciali per gli accenti nelle formule, in modo che i due tipi di accenti non vengano confusi tra loro. LaTex fornisce i seguenti accenti matematici:

![Accenti](/tex/images/java/tutorial/latex-math-4-8.png)

I primi nove di questi sono chiamati `\^`, `\v`,`\~ `,`\'`,` `\` `` `,`\.`, `\" `,`\u` e `\=`, rispettivamente, quando appaiono nel testo; `\vec` è un accento che appare solo in formula. `\V`, ecc., In formule o se si tenta di usare`\hat` o `\check`, ecc., Nel testo ordinario.

Di solito è meglio definire le macro per lettere accentate di cui hai bisogno frequentemente. Puoi mettere

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

All'inizio di un file LaTeX. Questo ti consente di risparmiare un sacco di tasti e rende il file più facile da leggere.

Quando le lettere *i* e *j* sono accentate nelle formule di matematica, dovresti usare basi di simboli senza punte che sono chiamate `\iMath` e `\jmath`. Quindi un documento che usa Hat'ed I e J potrebbe iniziare con le seguenti definizioni:

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

È possibile inserire accenti matematici su qualsiasi sottospettazione. Ma di solito non ha molto senso farlo, perché Tex centra l'accento per l'intera sottoculala. In particolare, un accento `\bar` rimane sempre delle stesse dimensioni; Non è come `\overline`, che cresce con la formula sotto di essa. Alcune persone preferiscono la linea più lunga da `\overline` anche quando si applica a una singola lettera. Tuttavia, il LaTeX fornisce due accenti che crescono; Sono chiamati `\widehat` e `\widetilde`. Ora diamo un'occhiata agli esempi di casi discussi nel presente paragrafo.

![Ampi accenti](/tex/images/java/tutorial/latex-math-4-9.png)

L'ultimo esempio mostra la dimensione massima disponibile.