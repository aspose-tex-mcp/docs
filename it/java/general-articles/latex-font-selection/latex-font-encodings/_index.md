---
translation: true
template: /templates/_template-java.md
linktitle: Ingresso e output
title: 1. Codifica di input e output 
weight: 10
url: /java/latex-font-encodings/
keywords: Font in LaTeX, LaTeX, codifica del carattere in LaTeX, NFSS
description: Questo articolo spiega brevemente i concetti di codifica input e output in LaTeX. Menziona anche il nuovo schema di selezione dei caratteri (NFSS).
lastmod: "2025-06-13"
---

{{<section overview>}}

Se premi un tasto su una tastiera, verrà generato un codice numerico che rappresenta un determinato carattere. Un input codificante mappa un carattere al codice corrispondente. Ad esempio, su una tastiera tedesca, caratteri accentati (come il personaggio di "A-Umlaut") possono essere mappati su codici diversi in diversi sistemi operativi.

Un documento archiviato in un file del computer contiene solo codici caratteristici, ma le informazioni sulla codifica input non sono esplicitamente incluse. Pertanto, se si trasferisce un file in un ambiente diverso, come, dagli Stati Uniti dichiarato al Regno Unito, potresti scoprire che i segni del dollaro nel tuo documento vengono improvvisamente interpretati come simboli di sterlina quando si visualizzano il file con un programma che rende l'ipotesi sbagliata sulla codifica input.

Il pacchetto `inputenc`, sviluppato dal team di progetto LaTex, aveva lo scopo di aiutare con problemi di codifica input. Consente agli utenti di specificare esplicitamente la codifica di input utilizzata per documenti o parti di documenti. Questo meccanismo rende sicuro il trasferimento di documenti da un'installazione in LaTeX a un'altra ottenuta risultati stampati identici.

Il pacchetto `inputenc` interpreta i codici dei caratteri nel file e li mappa a una *rappresentazione interno in LaTeX *, che copre in modo univoco tutti i caratteri rappresentabili in LaTeX. Durante l'ulteriore elaborazione, come la scrittura su alcuni file ausiliari, LaTex utilizza questa rappresentazione interna, evitando così qualsiasi interpretazione errata.

Tuttavia, prima o poi, il LaTeX deve associare queste rappresentazioni di carattere interne a *glifi* (forme di carattere in determinati caratteri), quindi è richiesta un'altra mappatura. Ci sono al massimo 256 glifi in qualsiasi carattere tex. Questi glifi non sono indirizzati per nome, ma con numeri a 8 bit che rappresentano le posizioni dei glifi nel carattere. Ciò significa che dobbiamo mappare da un grande spazio di denominazione unico in diversi piccoli e queste posizioni di glifi possono variare ampiamente, il che non è sorprendente.

Quindi, anche se abbiamo preservato il significato del segno del dollaro dal file esterno agli interni del LaTeX, potremmo comunque trovare forme errate sulla carta se abbiamo selezionato un carattere per la stampa che ha un glifo inaspettato nella posizione che presumeva fosse riservato a un segno in dollari. Uno dei compiti di **NFSS** (nuovo schema di selezione dei caratteri di LaTex ****) è quello di assicurarsi che qualsiasi rappresentazione del carattere interno in LaTeX sia resa correttamente o, se ciò è impossibile per qualche motivo, l'utente riceva un messaggio di errore adeguato.

Se un carattere contiene caratteri accentati come singoli glifi, anziché solo personaggi di base più accenti (da cui Tex crea personaggi accentati internamente), è preferibile usare questi glifi poiché di solito hanno un aspetto migliore. Un altro motivo (tecnico) per l'utilizzo di questi glifi compositi è che la primitiva `\Accent 'sopprimerà sillabazione.

Per soddisfare diversi casi, un comando come `\'e` (la rappresentazione interna del LaTeX per il personaggio" e-acuto ") a volte deve avviare azioni complicate che coinvolgono il primitivo`\accento, e a volte informa il paragrafo che ha bisogno del gesso da un determinato * slot * (posizione) nell'attuale font.

Tutto ciò si ottiene attraverso il concetto di *codifica di output*, che sono mappature delle rappresentazioni del carattere interno del LaTeX a posizioni appropriate di glifi o alle azioni di costruzione del glifo, a seconda dei glifi effettivi disponibili nel carattere utilizzato per la composizione.

I seguenti articoli discutono della versione 2 di NFSS, che è diventata parte del LaTeX standard nel 1994.