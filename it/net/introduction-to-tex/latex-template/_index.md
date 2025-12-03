---
translation: true
template: /templates/_template-net.md
title: 'Modelli LaTeX - guida rapida'
linktitle: Modelli LaTeX
type: docs
weight: 100
url: /net/latex-templates/
description: Scopri cosa sono i modelli LaTeX, come utilizzarli e crearli, dove scaricare quelli più popolari e un flusso di lavoro veloce con snippet pronti da copiare.
keywords: LaTeX, modello, classe, stile, retro, CTAN, bibliografia, Beamer, tesi, CV
lastmod: "2025-12-03"
---

{{<section overview>}}

# Guida ai modelli LaTeX

## Cos'è un modello LaTeX?

Un modello LaTeX raggruppa una **classe** (`.cls`), un **stile** (`.sty`), file di esempio `.tex` e risorse di supporto (loghi, file di bibliografia, ecc.) che definiscono il layout, la tipografia e la struttura per un tipo di documento specifico: articolo di giornale, tesi, CV, poster, presentazione e altro.

## Come utilizzare i modelli LaTeX

1. **Scarica** lo zip o clona il repository.  
2. Apri il file principale `.tex` (spesso chiamato `main.tex` o `article.tex`).  
3. Carica la classe o lo stile fornito dal template e segui la “struttura” del README (frontespizio, abstract, sezioni, bibliografia).

```latex
\documentclass[options]{mytemplate}   % class supplied by the template
\usepackage{mytemplate}               % sometimes a .sty instead of .cls
\begin{document}
  \title{My Title}
  \author{Me}
  \maketitle
  % <content>
\end{document}
```

Compilare con `pdflatex`, `latexmk -pdf` o con il pulsante “Ricompile” sul retro.

## Come creare il tuo modello

| **Obiettivo** | **File consigliato** | **Schema minimo** |
|---|------------------|-----------------|
| Controllo completo sulla struttura del documento | **Classe** (`.cls`) | Vedi blocco di codice qui sotto |
| Solo macro o formattazione aggiuntive | **Stile** (`.sty`) | – |
| Distribuzione | Archivio zip o repository GitHub (include classe/stile, `.bib` opzionale, loghi, README) | – |

### Scheletro di classe minima (`mytemplate.cls`)

```latex
% mytemplate.cls – a very simple article‑style class
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{mytemplate}[2025/12/03 v1.0 My custom class]
\LoadClass[12pt]{article}   % inherit from article

% ---- custom settings ----
\RequirePackage{geometry}
\geometry{margin=2cm}
\RequirePackage{fontspec}
\setmainfont{Latin Modern Roman}

% ---- user‑level commands ----
\newcommand\mytitle[1]{\centerline{\LARGE\bfseries #1}}
\endinput
```

Usalo con `\documentclass{mytemplate}` nel tuo documento.

## Dove scaricare i modelli LaTeX

- **Galleria sul retro** – la più grande raccolta pubblica (≈4000 modelli gratuiti).  
  <https://www.overleaf.com/gallery>
- **CTAN (ComprehensiveTeXArchive Network)** – repository ufficiale per classi specifiche della rivista.  
  <https://ctan.org/>
- **GitHub / GitLab**: molti autori pubblicano modelli di tesi o conferenze open source.  
- Pagine web di università/istituti: la maggior parte delle scuole ospita un modello di tesi/dissertazione “ufficiale”.

## Modelli più utilizzati/molto apprezzati

| **#** | **Modello** | **Uso tipico** |
|-------|----------|-------------|
| 1 | **IEEEtran** (`ieeetran.cls`) | Articoli di conferenze e riviste IEEE |
| 2 | **SpringerLNCS** (`llncs.cls`) | Appunti di informatica |
| 3 | **Articolo Elsevier** (`elsarticle.cls`) | Riviste Elsevier |
| 4 | **CV semplice moderno** | Curriculum vitae di una pagina |
| 5 | **Tesi classica** (`classicthesis.sty`) | Libro/tesi con tipografia elegante |
| 6 | **Beamer** (`beamer.cls`) | Presentazioni di diapositive |
| 7 | **a0poster / tikzposter** | Poster scientifici di grandi dimensioni |
| 8 | **Tesi universitarie** (ad esempio, `cambridgephd.cls`) | Tesi di dottorato/laurea magistrale istituzionali |
| 9 | **Astronomia e astrofisica** (`aa.cls`) | Articoli di riviste A&A |
| 10 | **Articolo di rivista accademica di base** | Introduzione semplice per articoli (retro) |

## Flusso di lavoro rapido per gli utenti alle prime armi

1. **Scegli un modello** → fai clic su "Apri sul retro" **o** scarica il file ZIP.  
2. **Modifica campi segnaposto** (`\title{}`, `\author{}`, ecc.).  
3. **Compila** → Viene visualizzato il PDF.  
4. Se lavori localmente: decomprimi → esegui `latexmk -pdf main.tex` (o `pdflatex` + `biber` come richiesto).  
5. **Esporta** il PDF o invia il codice sorgente a un repository Git per il controllo della versione.

## Insidie ​​e suggerimenti comuni

- **Pacchetti mancanti** – installa con il gestore della tua distribuzione (`tlmgr install <pkg>` o console MiKTeX).  
- **Classi obsolete** – Sul retro viene utilizzata la versione più recente di TeXLive; aggiorna regolarmente la tua installazione locale di TeX.  
- **Motore bibliografico**: molti modelli moderni si aspettano `biber`. Esegui `biber <basename>` dopo il primo passaggio LaTeX.  
- **Risorse di branding**: sostituisci loghi, PDF a colori o file ".sty" che definiscono i colori istituzionali.  
- **Comandi personalizzati**: conservali in un file `.sty` separato; è quindi possibile riutilizzare lo stesso layout su più documenti.


## Che ne dici di Aspose?

Quando è necessario manipolare i PDF generati da LaTeX (unirli, filigranarli o convertirli in altri formati) in un'applicazione .NET, Java o Python, librerie come **Aspose.TeX** forniscono un'API indipendente dal linguaggio per lavorare con file PDF senza richiedere una toolchain LaTeX completa.

---

### TL;DR Promemoria

```text
Cosa?     → Layout predefinito (classe+stile+risorse)
Uso?      → \documentclass{mytemplate} + segui README
Creare?   → Scrivere .cls o .sty → Comprimere le risorse → zip/GitHub
Ottenere? → Galleria Overleaf, CTAN, GitHub, siti universitari
Hot 10    → IEEEtran, llncs, elsarticle, modern-simple-cv,
          classicthesis, beamer, a0poster, tesi UNICAMP,
          aa.cls, Articolo di rivista accademica di base
```

Buona composizione!