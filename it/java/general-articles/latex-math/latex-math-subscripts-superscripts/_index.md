---
translation: true
template: /templates/_template-java.md
linktitle: Sobbriposto e pedice
title: 2. Sobbriposto e pedice in LaTeX 
weight: 20
url: /java/latex-math-subscripts-superscripts/
keywords: Latex, formule di matematica in LaTeX, matematica in LaTeX, abbonamenti matematici in LaTeX, apripisti di matematica in LaTeX, latex Prime
description: Questo articolo discute su come costruire formule di matematica che contengono abbonamenti e apice con Tex e LaTex.
lastmod: "2025-06-13"
---

{{<section overview>}}


## Introduzione al LaTeX appescript e abbonamenti

**apice** è un piccolo carattere o un simbolo posizionato leggermente sopra la linea di base del testo.  Ad esempio, nell'espressione `x²`,` 2` è un apice.

**Sobbriposto** è un piccolo carattere o un simbolo leggermente posizionato sotto la linea di base del testo. Ad esempio, nella formula chimica per l'acqua, `h₂o`, il` 2` è un pedice.

## Come scrivere il pedice/apice in LaTeX

Ora proviamo a costruire formule più complesse da quelle semplici. Innanzitutto, è possibile ottenere apici e abbonamenti usando `^` e `_`, come mostrato nell'esempio seguente:

![Abbonamenti e apripisti a caratteri singoli](/tex/images/java/tutorial/latex-math-2-1.png)

Nota che `^` e `_` si applicano solo al carattere successivo. Se si desidera un pedice o un apice più complesso, basta racchiuderlo nelle parentesi graffe:

![Abbonamenti e apripisti multi-caratteri](/tex/images/java/tutorial/latex-math-2-2.png)

Le parentesi graffe in questi esempi specificano "Sottformule" - parti più semplici di una formula più grande. Tex fa una scatola per ogni subformante e tratta quella scatola come se fosse un singolo simbolo. Le parentesi graffe hanno anche il loro solito scopo di raggruppamento.

È illegale digitare `$ x^y^z $` o `$ x_y_z $`. Tex si lamenterà di un "doppio pedice" o "doppio apice". Devi rendere più chiaro ciò che vuoi digitando `$ x^{y^z} $`, o `$ x^{yz} $`, o `$ x_ {y_z} $` o `$ x_ {yz} $`.

Un apice o un pedice che segue un carattere si applica solo a quel carattere; Ma quando si seguono una sottomissione si applica a tutta la sottomissione e verrà sollevato o abbassato di conseguenza.

![Abbonamenti e apice su un singolo simbolo e su una sottomissione](/tex/images/java/tutorial/latex-math-2-3.png)

Nella prima formula i `^3` e `^4` sono appesanti sulle parentesi giuste che le precedono immediatamente, ma nella seconda formula sono appesanti sulle sottocamere che sono racchiuse in parentesi graffe. La prima versione è preferibile, perché è più facile da digitare ed è altrettanto facile da leggere.

## Scrivere un pedice o apice su una sottospettazione vuota

A volte potrebbe essere necessario creare un pedice o apice su una sottospettazione vuota per produrre una notazione piuttosto rara come *<sub> 2 </sub> f <sub> 3 </ sub> *. Il modo migliore per farlo è digitare `$ {} _ 2f_3 $` o `$ {_ 2} f_3 $` o `$ {_ 2f_3} $`.

Puoi anche avere "subscritti" simultanei e puoi specificarli in qualsiasi ordine:

![Sottoseguiti simultanei](/tex/images/java/tutorial/latex-math-2-4.png)

Questi "subscritti" simultanei sono posizionati l'uno sull'altro. Tuttavia, per alcune lettere, un pedice verrà spostato a sinistra; E per alcune di quelle lettere abbastanza notevolmente. Confronta le seguenti due formule:

![Allineamento simultaneo di sottospetti](/tex/images/java/tutorial/latex-math-2-5.png)

Quindi, se si desidera che sia il pedice e appescript, è possibile utilizzare il trucco mostrato nella seconda versione. Ancora una volta, sfrutta una sottospettazione vuota.

## Scrivere Prime in LaTeX

La prossima cosa che si verifica spesso nelle formule di matematica è il simbolo principale. LaTex fornisce il comando `\prime`, che a sua volta produce un simbolo di Prime alla dimensione di una lettera normale. Quindi, non vorresti mai usarlo se non in un apice o un pedice. Ma puoi semplicemente digitare `'` invece di `^\ prime`, e`' '`invece di`^\ prime \ prime`, e così via.

![Numeri primi](/tex/images/java/tutorial/latex-math-2-6.png)

## Double Apuerscript Latex

In LaTex, puoi scrivere doppi apice racchiudendo l'intera espressione appescritta all'interno delle parentesi graffe {}. Ecco un esempio: `x^{a^b}`

## Doppio Sottoscrizione LaTeX

In LaTex, è possibile scrivere doppi abbonamenti in modo simile racchiudendo l'intera espressione del pedice all'interno delle parentesi graffe {}. Ecco un esempio: `x_ {i_ {j}}