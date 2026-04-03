---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LaTeX
title: 1. Introduzione ad AMS-LaTeX
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, amsmath options, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: Questo articolo è una breve introduzione al pacchetto amsmath e copre brevemente le sue opzioni, nonché i sottopacchetti e le estensioni disponibili.
lastmod: "2026-03-30"
---

{{<section overview>}}


La versione 1.0 di *AMS*-LaTeX è stata rilasciata nel 1990 e ha presentato la conversione originale in LaTeX delle funzionalità matematiche di *AMS*-TeX di Michael Spivak, curata da Frank Mittelbach e Rainer Schopf (che hanno lavorato come consulenti per l'AMS) con l'assistenza di Michael Downes dello staff tecnico dell'AMS. Nel 1994 è stato svolto un ulteriore lavoro con David M. Jones.

Il pacchetto *amsmath* accetta alcune opzioni che influiscono principalmente sul posizionamento dei *limiti* su vari operatori matematici o sul posizionamento dei tag delle equazioni.

## Opzioni disponibili per il pacchetto *amsmath*

Le tre opzioni seguenti possono essere utilizzate come opzioni globali del documento (specificate nel comando `\documentclass`) o come opzioni del pacchetto *amsmath* quando viene caricato tramite il comando `\usepackage`.

|||
|---|---|
| `reqno` **(predefinito)** | Posiziona i numeri delle equazioni (tag) a destra. |
| `leqno` | Posiziona i numeri delle equazioni (tag) a sinistra (predefinito quando si utilizzano le classi di documento *AMS*-LaTeX). |
| `fleqn` | Posiziona le equazioni a un rientro fisso dal margine sinistro anziché al centro della colonna di testo. |

## Sottopacchetti disponibili

Nella distribuzione *AMS*-LaTeX, puoi trovare anche componenti che possono essere caricati indipendentemente tramite il comando `\usepackage`. I seguenti piccoli pacchetti forniscono alcune funzionalità del pacchetto *amsmath*:

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
| `upref` | Fa sì che `\ref` stampi i numeri dei riferimenti in un font verticale/romano, indipendentemente dal contesto. |