---
translation: true
template: /templates/_template-java.md
linktitle: Ams-Latex
title: 1. Introduzione AMS-LATEX 
weight: 10
url: /java/introduction-to-ams-latex/
keywords: AMS-Latex, Amsmath, Amsmath Options, Amsopn, Amstext, Amscd, AmstHm, Amsxtra, UpRef
description: Questo articolo è una breve introduzione nel pacchetto Amsmath e copre brevemente le sue opzioni, nonché i sottopagoni e le estensioni disponibili.
lastmod: "2025-06-13"
---

{{<section overview>}}


*AMS*-latex versione 1.0 è stata rilasciata nel 1990 e ha presentato la conversione originale in LaTeX delle capacità di matematica in*Ams*-tex di Michael Spivak di Frank Mittelbach e Rainer Schopf, che ha lavorato come consulenti per il*Ams*, con l'assistenza di Michael Downe dello staff tecnologico*AMS*. Nel 1994, l'ulteriore lavoro è stato svolto con David M. Jones.

* Il pacchetto Amsmath* accetta alcune opzioni che influiscono principalmente sul posizionamento di* limiti* su vari operatori di matematica o sul posizionamento dei tag di equazione.

## Disponibile * Opzioni del pacchetto Amsmath *

Le seguenti tre opzioni possono essere utilizzate come opzioni di documento globale (specificate nel comando `\documentclass`) o come *Amsmath* Opzioni del pacchetto quando viene caricato con il comando `\usepackage`.

|||
|---|---|
| `reqno` **(predefinito)** | Posiziona i numeri delle equazioni (tag) a destra. |
| `leqno` | Posiziona i numeri delle equazioni (tag) a sinistra (predefinito, quando si utilizzano le classi di documento *AMS*-LATEX). |
| `fleqn` | Posiziona le equazioni a un rientro fisso dal margine sinistro anziché al centro della colonna di testo. |

## Sottopagoni disponibili

Nella distribuzione *AMS *-latex, puoi anche trovare componenti che possono essere caricati in modo indipendente dal comando `\usapackage`. I seguenti pacchetti più piccoli forniscono alcune funzionalità del pacchetto *amsmath*:

|||
|---|---|
| `amsopn` | Fornisce `\DeclareMathOperator` per definire nuovi nomi di operatori come `\Ker` e `\esssup`. |
| `amstext` | Fornisce il comando `\text` per comporre un frammento di testo nella dimensione corretta. |

## Pacchetti di estensione

I pacchetti elencati di seguito forniscono funzionalità aggiuntive e devono essere caricati esplicitamente.

|||
|---|---|
| `amscd` | Definisce alcuni comandi per semplificare la generazione di diagrammi commutativi. |
| `amsthm` | Fornisce un metodo per dichiarare strutture simili a teoremi e offre un ambiente `proof`. |
| `amsxtra` | Fornisce alcune funzionalità necessarie per la compatibilità storica, come `\fracwithdelims`, `\accentedsymbol` e comandi per posizionare gli accenti come apici. |
| `upref` | Fa sì che `\ref` stampi i numeri dei riferimenti incrociati in un font verticale/romano, indipendentemente dal contesto. |