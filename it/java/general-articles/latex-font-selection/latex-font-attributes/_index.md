---
translation: true
template: /templates/_template-java.md
linktitle: 2. Caratteristiche del carattere
title: Caratteristiche del carattere | Aspose.TeX per java
weight: 20
url: /java/latex-font-attributes/
keywords: Font in LaTeX, LaTeX, codifica del carattere in LaTeX, NFSS
description: Questo articolo copre le classificazioni del carattere in LaTeX rispetto a varie caratteristiche dei caratteri. Menziona anche il concetto di codifica del carattere in LaTeX.
lastmod: "2025-06-13"
---

{{<section overview>}}

I caratteri possono essere divisi in singole classi sovrapposte in base a varie caratteristiche. Spesso si rivela utile conoscere queste caratteristiche quando dobbiamo decidere quale famiglia di carattere utilizzare in un contesto specifico. Vedi anche l'articolo di documentazione di [Aspose.font](https://products.aspose.com/font/) su [diversi tipi di caratteri](/font/net/what-is-font/font-types/).

## 2.1. Caratteri proporzionali e monospaziati

I caratteri possono essere proporzionali o monospati. In un carattere proporzionale, gli glifi hanno larghezze diverse a seconda della loro forma.  Allo stesso tempo, in un carattere monospazzato, tutti gli glifi sono della stessa larghezza. Gli spazi extra attorno agli glifi dei caratteri monospaziati rendono più difficile riconoscere i confini delle parole e quindi rendere il testo digitato in tali caratteri meno leggibili. Al contrario, i caratteri proporzionali (o *tipografici *) di solito consentono di posizionare più parole su una pagina e sono più leggibili dei caratteri monospati. Vedi la figura seguente:

![Caratteri proporzionali e monospaziati](/tex/images/java/tutorial/latex-font-selection-2-1.png)
 
Sebbene i caratteri monospaziati appaiano meno leggibili, hanno ancora il loro uso. Un esempio sono le tabelle o gli elenchi dei programmi in cui è importante un corretto allineamento del contenuto. Troverai sempre programmi per computer visualizzati in un carattere monospazzato in qualsiasi computer dal libro. Ciò distingue facilmente i programmi dal testo circostante.

Puoi anche scegliere un carattere monospazzato come carattere di base per un documento completo perché un carattere del genere sembra fatto a mano se usato con paragrafi ingiustificati, dandogli un sapore di una macchina da scrivere.

## 2.2. Caratteri serificati e sans serif

In alcuni caratteri, gli glifi hanno *serif*, mentre negli altri, non lo fanno. Questo fatto ci porta a un'altra utile classificazione. I serif sono piccoli colpi orizzontali alle estremità dei glifi. Inizialmente, furono prodotti dallo scalpello quando i capitali romani venivano incisi nella pietra. Ecco perché i caratteri serificati sono spesso chiamati caratteri *romani*.

![Caratteri serificati e sans serif](/tex/images/java/tutorial/latex-font-selection-2-2.png)
 
I caratteri serificati erano a lungo considerati più leggibili poiché danno all'occhio più indizi per l'identificazione. Ma ricerche dedicate hanno dimostrato che la velocità di lettura non è sostanzialmente influenzata dall'assenza di serif.

## 2.3. Famiglie di carattere e i loro attributi

A parte le classificazioni grezze che abbiamo discusso sopra, i caratteri sono raggruppati in famiglie di carattere. I membri di una famiglia di caratteri condividono i principi di progettazione comuni e si distinguono per variazioni di dimensioni, peso, larghezza e forma.

### Forme di carattere

Quasi ogni famiglia di carattere ha una forma chiamata * Upright * Shape. Il carattere che stai leggendo è in forma verticale. Questa forma del carattere viene solitamente utilizzata per digitare il testo normale.

Un'altra forma importante inclusa nella maggior parte delle famiglie è la forma *corsivo*, che sembra

![Testo in corsivo](/tex/images/java/tutorial/latex-font-selection-2-3.png)
 
Gli glifi in corsivo sono inclinati a destra e le lettere sono disegnate in modo diverso dalle loro controparti verticali, come mostrato nella figura seguente:

![Oprigente, in corsivo in posizione verticale e in corsivo a forma di confronto](/tex/images/java/tutorial/latex-font-selection-2-4.png)
 
La prima riga mostra lettere della famiglia Serif moderna del computer in forma verticale e la terza linea mostra le stesse lettere in forma in corsivo. Per fare la differenza nel disegnare più evidente, la seconda riga fornisce le lettere in corsivo senza la solita inclinazione. In altre parole, quelle sono lettere in corsivo in posizione verticale.

Le famiglie di carattere di San Serif spesso mancano di una corretta forma in corsivo; Invece, hanno una forma *inclinata* in cui i normali personaggi verticali inclinano a destra. Tali caratteri sono anche spesso chiamati *oblique* o *inclinati*.
Un'altra forma di carattere comune è la forma *di piccoli tappi*, in cui le lettere minuscole sono rappresentate come capitali con un'altezza ridotta. Se la forma di piccoli tappi non è disponibile per un carattere specifico, i tipografi a volte utilizzano capitali verticali da dimensioni più piccole, ma ciò non produce la stessa qualità di un carattere ben progettato. True Small Caps hanno larghezze e peso diverse rispetto alle lettere maiuscole dallo stesso carattere che sono state ridotte all'altezza dei piccoli tappi progettati. Puoi vedere nella figura sottostante che i colpi nei capitali falsi sono troppo sottili.

![Confronto vero e falso per piccoli tappi](/tex/images/java/tutorial/latex-font-selection-2-5.png) 

### Peso e larghezza

I caratteri di una certa forma all'interno di una famiglia possono differire in *peso*. Questa caratteristica è correlata allo spessore dei colpi usati per disegnare le singole forme. Alcuni produttori di carattere chiamano i pesi di carattere destinati ad essere utilizzati per il normale testo *libro*, mentre altri li chiamano *medio*. Per i colpi sottili, il nome *luce* è all'ordine del giorno, mentre i colpi più spessi sono generalmente chiamati *grassetto*. Nelle famiglie di carattere più grandi, a volte troviamo un intervallo che inizia con *ultra luce*, attraversando *luce extra*, *luce*, *semi luce* e così via, e finendo con *ultra audace *all'altra estremità. Ma spesso solo pochi pesi sono disponibili in alcune famiglie. La famiglia romana moderna del computer, per esempio, ha solo pesi medi e audaci.

La larghezza del carattere * è un altro attributo importante. Si riferisce alla quantità di espansione o contrazione rispetto alla larghezza normale o media nella famiglia. Computer Modern Roman ha caratteri audaci in *larghezza media* e *larghezza estesa*. I caratteri condensati vengono spesso utilizzati nei titoli e nei titoli, in cui i caratteri a livello medio, se usati a grandi dimensioni, consumerebbero troppo spazio.

### Taglie di carattere

L'unità di misurazione per le dimensioni dei caratteri è un punto di stampante (PT). Ci sono 72,27 punti in un pollice. La dimensione del carattere non si riferisce a nessuna caratteristica particolare, ma è piuttosto un valore scelto dal designer di caratteri per guidare l'utente. Ad esempio, in un carattere da 10pt, le lettere dell'alfabeto sono generalmente alte meno di 10 pt e solo i personaggi come le parentesi hanno approssimativamente questa altezza.

L'aspetto di un carattere dipende da molti fattori, come l'altezza delle lettere minuscole (la *height * *), la larghezza dell'ictus e la profondità dei discendenti (la parte delle lettere sotto la linea di base, come nella lettera "Q"). Ecco perché due caratteri della stessa dimensione potrebbero non fondersi bene tra loro.

Nel mondo del LaTeX, i caratteri sono spesso disponibili in dimensioni che sono poteri di 1.2, il che significa che seguono una progressione geometrica. Questa disposizione semplifica la produzione di una copia master ingrossata che può essere successivamente ridotta fotograficamente, aumentando così efficacemente la risoluzione finale di output. Al giorno d'oggi, i caratteri sono generalmente vettoriali e quindi possono essere ridimensionati a piacimento. Di conseguenza, molte famiglie di carattere commerciali sono fornite in una sola dimensione del design.

L'uso di caratteri in scala invece di caratteri progettati per una dimensione specifica spesso dà risultati meno soddisfacenti. Ciò è dovuto al fatto che i caratteri non si ridimensionano in modo lineare all'occhio umano. Puoi vedere la differenza nella figura seguente:

![Un vero 10pt e un caratteri 5pt ingrandito](/tex/images/java/tutorial/latex-font-selection-2-6.png)
 
I glifi in caratteri artigianali di dimensioni più grandi sono generalmente più stretti dei caratteri ingranditi da una dimensione più piccola della stessa famiglia. Si dovrebbero usare i caratteri progettati per la dimensione desiderata quando possibile, sebbene sia accettabile per ridimensionare i caratteri all'interno di una gamma di dimensioni ridotte.

## 2.4. Codifica di font

Come menzionato nell'introduzione, Tex si riferisce ai glifi di un carattere affrontandoli tramite codici. Tale mappatura è chiamata codifica del carattere *. Nel LaTeX, due caratteri con la stessa codifica dei caratteri dovrebbero essere intercambiabili nel senso che dato lo stesso input, producono gli "stessi" glifi nella pagina stampata.
Classificando i caratteri con le codifiche dei caratteri, è possibile modificare altre caratteristiche, come la famiglia di caratteri o i caratteri, e assicurarsi comunque che il risultato del composizione rimanga comprensibile.

Inizialmente, le distribuzioni tex includevano i caratteri che hanno solo 128 glifi per carattere. Pertanto, quei caratteri non includono caratteri accentati come singoli glifi. Tutti questi glifi dovevano essere costruiti usando la primitiva `\accento` di Tex con metodi simili. Di conseguenza, qualsiasi parola contenente diaritici non può essere automaticamente sillanata dal LaTeX e il kerning (correzione della spaziatura tra determinate lettere nel carattere) non può essere applicata automaticamente. La codifica di questi caratteri è chiamata `ot1`. Sebbene rimanga la codifica predefinita per il LaTeX, non è consigliabile utilizzare `ot1` per lingue diverse dall'inglese.

La comunità utente Tex ha definito una codifica di 256 caratteri chiamata `T1` che consente a Tex di compromettere correttamente in più di 30 lingue in base all'alfabeto latino. Pertanto, l'uso della codifica `t1` è altamente raccomandato poiché, al giorno d'oggi, sono disponibili quasi tutte le famiglie di caratteri che possono essere utilizzate con LaTeX in questa codifica. In effetti, alcuni sono *solo* disponibili nella codifica `T1`. Specificando `\usepackage [t1] {fontenc}` dopo che il comando `\documentclass` rende` t1` la codifica predefinita all'interno di un documento.