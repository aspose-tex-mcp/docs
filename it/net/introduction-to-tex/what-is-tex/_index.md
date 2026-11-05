---
translation: true
template: /templates/_template-net.md
title: Cos'è TeX? Introduzione a TeX
linktitle: Cos'è TeX?
weight: 10
url: /net/what-is-tex/
keywords: Cos'è TeX
description: Questa pagina risponde brevemente alla domanda "Che cos'è TeX?" È uno dei linguaggi di programmazione o è considerato un formato di documenti?
lastmod: "2026-04-22"
---

{{<section overview>}}

## Cosa non lo è TeX

TeX non è assolutamente un formato.

## Cos'è TeX?

Allora cos'è TeX? Bene, questa è la domanda, come ha detto Amleto [^1]. Proviamo a rispondere nel modo più semplice possibile.

Immagina di avere un linguaggio di programmazione costituito da due comandi elementari (chiamati *sequenze di controllo *) o *primitives *, `\a` e `\b`. E in questa lingua possiamo scrivere programmi per documenti (libri, articoli, ecc.) Comportamento. Chiamiamo questa lingua **(L1)**. Affinché questi programmi vengano eseguiti in un certo modo, abbiamo un certo motore che interpreta i comandi di questa lingua.

Ora supponiamo che quando si scrive un programma di composizione per qualche documento, abbiamo scoperto che la successione `\a \ b \ a` si verifica abbastanza frequentemente. E supponiamo anche che nella nostra lingua esiste un altro primitivo `\def`, che ci consente di definire le subroutine o le macro. Chiamiamo questa lingua **(L2)**. In queste circostanze, possiamo definire la macro `\def \ c {\ a \ b \ a}` all'inizio del programma e sostituire ogni occorrenza della sottosequenza con `\c` sia per migliore leggibilità e riduzione.

Ora, se vogliamo compensare un altro documento, nel programma di cui si verifica anche questa sottosequenza di comandi, dovremo definire nuovamente questa macro. Ma supponiamo che il nostro motore sia in grado di caricare la macro `\c` nel suo stato interno, e quindi salvare quello stato come file binario (un*dump*), che verrà quindi caricato automaticamente (" in cima "del **(L2)** set di comandi di lingua) prima di elaborare i programmi di composizione di ogni documento in cui è necessario la macro`\C`. Chiameremo l'insieme di primitive esteso dal formato `\c` Macro A *. Pertanto, il nostro formato è una*macro estensione*di linguaggio primitivo di basso livello **(L2)**.

Il motore contiene anche una serie di registri interni o *parametri interni *, a cui è possibile accedere utilizzando sequenze di controllo. Oltre alle definizioni macro, un formato può contenere espressioni di inizializzazione per questi parametri.

È successo che <a href="https://en.wikipedia.org/wiki/Donald_Knuth" target=_blank rel="nofollow">Donald E. Knuth</a>, ha definito una lingua simile a **(L2)**, ma con un set molto più vasto di primitivi, che ha chiamato TeX. Ha anche creato un motore che ha capito (e lo fa ancora) il linguaggio TeX. Lo ha anche chiamato TeX.

Fortunatamente, queste non erano le uniche cose che faceva. Ha anche proposto la macro estensione, o formato, che ha chiamato *Plain* TeX, che ha reso i programmi di scrittura più convenienti. L'insieme iniziale dei primitivi di TeX è talvolta chiamato VirTeX ("Vir" per "vergine") e, formalmente, è anche un formato, se considerato insieme alle impostazioni predefinite di parametri interni.

**Quindi, da un lato, TeX è un linguaggio di programmazione. E d'altra parte, è un motore di interpretazione che comprende questa lingua. E, in terza mano, TeX è un concetto più generale che significa un sistema di composizione in tutto.**

L'unica cosa rimasta da notare qui è che, in effetti, i caratteri del testo stesso sono anche comandi che costringono il motore TEX a digitare i caratteri corrispondenti (tenendo conto della codifica input corrente) usando le impostazioni di carattere corrente (che, a loro volta, sono controllabili dalle sequenze di controllo). Pertanto, quando si definiscono le macro, possiamo usare anche i caratteri.

Speriamo che d'ora in poi la domanda "Che cos'è TeX?" Non esiste più nella tua mente.
[^1]: Il personaggio in "The Tragical Historie of Hamlet, Prince of Denmarke" di W. Shakespeare.