---
translation: true
template: /templates/_template-net.md
title: LaTeX-Vorlagen – Kurzanleitung
linktitle: LaTeX-Vorlagen
type: docs
weight: 100
url: /net/latex-templates/
description: Erfahren Sie, was LaTeX-Vorlagen sind, wie Sie sie verwenden und erstellen, wo Sie die beliebtesten herunterladen können und einen schnellen Workflow mit kopierfertigen Snippets.
keywords: LaTeX, Vorlage, Klasse, Stil, Overleaf, CTAN, Bibliographie, Beamer, Abschlussarbeit, Lebenslauf
lastmod: "2026-06-12"
---

{{<section overview>}}

# Leitfaden zu LaTeX-Vorlagen

## Was ist eine LaTeX-Vorlage?

Eine LaTeX-Vorlage bündelt eine **Klasse** (`.cls`), einen **Stil** (`.sty`), Beispiel-`.tex`-Dateien und unterstützende Assets (Logos, Bibliografiedateien usw.), die das Layout, die Typografie und die Struktur für einen bestimmten Dokumenttyp definieren – Zeitschriftenartikel, Abschlussarbeit, Lebenslauf, Poster, Foliensatz und mehr.

## So verwenden Sie LaTeX-Vorlagen

1. **Laden** Sie die ZIP-Datei herunter oder klonen Sie das Repository.  
2. Öffnen Sie die Hauptdatei „.tex“ (oft „main.tex“ oder „article.tex“ genannt).  
3. Laden Sie die von der Vorlage bereitgestellte Klasse oder den Stil und folgen Sie der „Struktur“ der README-Datei (Titelseite, Zusammenfassung, Abschnitte, Bibliographie).

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

Kompilieren Sie mit „pdflatex“, „latexmk -pdf“ oder der umseitigen Schaltfläche „Neu kompilieren“.

## So erstellen Sie Ihre eigene Vorlage

| **Ziel** | **Empfohlene Datei** | **Minimales Grundgerüst** |
------|------------------|-----------------|
| Volle Kontrolle über die Dokumentstruktur | **Klasse** (`.cls`) | Siehe Codeblock unten |
Nur zusätzliche Makros oder Formatierungen | **Stil** (`.sty`) | – |
| Verteilung | Zip-Archiv oder GitHub-Repository (Klasse/Stil, optional `.bib`, Logos, README) | – |

### Minimales Klassengerüst („mytemplate.cls“)

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

Verwenden Sie es mit „\documentclass{mytemplate}“ in Ihrem Dokument.

## Wo kann man LaTeX-Vorlagen herunterladen?

- **Overleaf-Galerie** – die größte öffentliche Sammlung (≈4000 kostenlose Vorlagen).  
  <https://www.overleaf.com/gallery>
- **CTAN (ComprehensiveTeXArchive Network)** – offizielles Repository für zeitschriftenspezifische Klassen.  
  <https://ctan.org/>
- **GitHub / GitLab** – viele Autoren veröffentlichen Open-Source-Abschlussarbeiten oder Konferenzvorlagen.  
- Webseiten von Universitäten/Instituten – die meisten Schulen bieten eine „offizielle“ Vorlage für Abschlussarbeiten/Dissertationen an.

## Am häufigsten verwendete/hochbewertete Vorlagen

| **#** | **Vorlage** | **Typische Verwendung** |
|---|----------|-------------|
|1 | **IEEEtran** (`ieeetran.cls`) | IEEE-Konferenz- und Zeitschriftenbeiträge |
|2 | **SpringerLNCS** (`llncs.cls`) | Lecture Notes in Computer Science |
|3 | **Elsevier-Artikel** (`elsarticle.cls`) | Elsevier-Zeitschriften |
|4 | **Moderner, einfacher Lebenslauf** | Einseitiger Lebenslauf |
|5 | **Klassische Dissertation** (`classicthesis.sty`) | Buch/Dissertation mit eleganter Typografie |
|6 | **Beamer** (`beamer.cls`) | Folienpräsentationen |
|7 | **a0poster / tikzposter** | Große wissenschaftliche Poster |
|8 | **Universitätsspezifische Dissertation** (z. B. `cambridgephd.cls`) | Institutionelle Doktor-/Masterarbeiten |
|9 | **Astronomie & Astrophysik** (`aa.cls`) | Artikel aus A&A-Zeitschriften |
|10 | **Einfacher wissenschaftlicher Zeitschriftenartikel** | Einfacher Einstieg für Artikel (Overleaf) |

## Schneller Workflow für Erstbenutzer

1. **Wählen Sie eine Vorlage aus** → klicken Sie auf „In Overleaf öffnen“ **oder** laden Sie die ZIP-Datei herunter.  
2. **Platzhalterfelder bearbeiten** (`\title{}`, `\author{}` usw.).  
3. **Kompilieren** → PDF erscheint.  
4. Wenn Sie lokal arbeiten: entpacken → „latexmk -pdf main.tex“ ausführen (oder „pdflatex“ + „biber“ nach Bedarf).  
5. **Exportieren** Sie die PDF-Datei oder übertragen Sie die Quelle zur Versionskontrolle in ein Git-Repository.

## Häufige Fallstricke und Tipps

- **Fehlende Pakete** – installieren Sie mit dem Manager Ihrer Distribution („tlmgr install <pkg>“ oder der MiKTeX-Konsole).  
- **Veraltete Klassen** – Overleaf verwendet das neueste TeXLive; Aktualisieren Sie regelmäßig Ihre lokale TeX-Installation.  
- **Bibliographie-Engine** – viele moderne Vorlagen erwarten „Biber“. Führen Sie „biber <basename>“ nach dem ersten LaTeX-Durchlauf aus.  
- **Branding-Assets** – Ersetzen Sie Logos, Farb-PDFs oder „.sty“-Dateien, die institutionelle Farben definieren.  
- **Benutzerdefinierte Befehle** – bewahren Sie sie in einer separaten „.sty“-Datei auf; Sie können dann dasselbe Layout für mehrere Dokumente wiederverwenden.


## Was ist mit Aspose?

Wenn Sie die aus LaTeX generierten PDFs in einer .NET-, Java- oder Python-Anwendung bearbeiten müssen (zusammenführen, mit Wasserzeichen versehen oder in andere Formate konvertieren), bieten Bibliotheken wie **Aspose.TeX** eine sprachunabhängige API für die Arbeit mit PDF-Dateien, ohne dass eine vollständige LaTeX-Toolchain erforderlich ist.

---

### TL;DR Spickzettel

```text
Was?       → Vorgefertigtes Layout (Klasse + Stil + Assets)
Verwenden? → \documentclass{mytemplate} + README befolgen
Erstellen? → .cls- oder .sty-Datei schreiben → Assets packen → zip/GitHub
Beziehen?  → Overleaf-Galerie, CTAN, GitHub, Universitätsseiten
Top 10     → IEEEtran, llncs, elsarticle, modern‑simple‑cv,
             classicthesis, beamer, a0poster, UNICAMP thesis, aa.cls, Basic Academic Journal Article
```

Viel Spaß beim Setzen!


## Entwicklung eines KI-Agenten zur Erstellung von LaTeX-Vorlagen

Wenn Sie einen eigenen KI-Agenten zur Erstellung von LaTeX-Vorlagen mithilfe der Aspose.TeX-API entwickeln möchten, finden Sie hier einen Vorschlag für einen möglichen Workflow:

*Die technische Herausforderung besteht darin, sicherzustellen, dass die Vorlage den Standard-Kompilierungsmechanismen der LaTeX2e-Layoutregeln fehlerfrei entspricht.*

![Blockschema für den KI-Workflow zur Darstellung von LaTeX-Abbildungen](/tex/images/net/tutorial/blockscheme-ai-for-latex-template-creation.png)

1. Erfassung der Layoutanforderungen (LLM-Intent-Layer)
Der Benutzer gibt allgemeine Designvorgaben oder Formatierungsanweisungen vor (z. B. „Erstellen Sie ein zweispaltiges Zeitschriftenlayout mit 1,5 cm Seitenrändern, Times New Roman-Schriftart, roten Überschriften und einem eleganten Autorenfeld am oberen Rand“). Anschließend ordnet der LLM diese semantischen visuellen Details strukturellen programmatischen Anforderungen zu.

Die Intent-Matrix entscheidet, ob die Anfrage eine komplett neue, eigenständige Klassendatei (`.cls`) für einen benutzerdefinierten Dokumenttyp erfordert oder lediglich einen angepassten Style-Wrapper (`.sty`), der in Standardklassen wie Artikel oder Bericht eingebunden wird.

2. Ausrichtung des Vererbungsbaums und Klassengenerierung (Strukturschicht)
Der Agent erstellt die Strukturcodeblöcke für die `.cls`-Datei basierend auf einer starren Strukturmatrix:
- Fügt automatisch `\NeedsTeXFormat{LaTeX2e}` und einen dynamischen Metadaten-Header `\ProvidesClass{...}[...]` ein.
- Ordnet den Ziel-Designarchetyp über `\LoadClass{...}` einer Basisklasse zu.
- Konvertiert natürlichsprachliche Komponenten in native Makros (z. B. die Umwandlung einer „Autorenbox“-Anfrage in einen benutzerdefinierten `\renewcommand{\maketitle}{...}`-Definitionsblock).

3. Paketfabrik und Asset-Sammlung (Abhängigkeitsschicht)
Abhängig von den im ersten Schritt extrahierten Designanweisungen benötigt die Layout-Engine spezielle Makro-Tools von Drittanbietern (z. B. `geometry` für Randanpassungen, `xcolor` für benutzerdefinierte Markenfarben oder `fontspec` für moderne Schriftkonfigurationen).

Der Agent fungiert als Linting-Filter. Er fügt dynamisch die erforderlichen `\RequirePackage{...}`-Anweisungen in das Klassen- oder Stil-Bundle ein.

4. Verifizierung und Validierung (Aspose.TeX-Kompilierungsknoten)
Der Agent erstellt dynamisch eine Testdatei (`sample.tex`), die die Vorlage lädt.

Anschließend startet der Agent über Aspose.TeX einen impliziten `TeXJob`, um den Vorlagencode zu kompilieren. Schlägt die Kompilierung fehl, liest der Agent die Fehlerprotokolle (`.log`) und leitet die Trace-Protokolle zur automatischen Syntaxkorrektur an den LLM zurück. Bei erfolgreicher Kompilierung wird das Asset-Bundle verifiziert.