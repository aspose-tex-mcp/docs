---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LATEX
title: 1. Einführung in AMS-LATEX | LaTeX-Handbuch
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, amsmath-Optionen, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: Dieser Artikel ist eine kurze Einführung in das amsmath-Paket und geht kurz auf seine Optionen sowie verfügbare Unterpakete und Erweiterungen ein.
lastmod: "2024-09-26"
---

{{<section overview>}}


*AMS*-LATEX Version 1.0 wurde 1990 veröffentlicht und stellte die ursprüngliche Konvertierung der mathematischen Fähigkeiten in Michael Spivaks *AMS*-TEX durch Frank Mittelbach und Rainer Schopf, die als Berater des *AMS* arbeiteten, mit Unterstützung von in LaTeX dar Michael Downes vom *AMS*-Technikteam. 1994 erfolgte die weitere Arbeit mit David M. Jones.

Das *Amsmath*-Paket akzeptiert einige Optionen, die sich hauptsächlich auf die Positionierung von *Grenzwerten* für verschiedene mathematische Operatoren oder die Positionierung von Gleichungs-Tags auswirken.

## Verfügbare *amsmath*-Paketoptionen

Die folgenden drei Optionen können als globale Dokumentoptionen (angegeben im Befehl `\documentclass`) oder als *amsmath*-Paketoptionen verwendet werden, wenn sie mit dem Befehl `\usepackage` geladen werden.

|||
|---|---|
| `reqno` **(Standard)** | Gleichungsnummern (Tags) rechts platzieren. |
| `leqno` | Gleichungsnummern (Tags) links platzieren (Standard, wenn die *AMS*-LATEX-Dokumentklassen verwendet werden). |
| `fleqn` | Gleichungen mit einem festen Einzug vom linken Rand positionieren, anstatt zentriert in der Textspalte. |

## Verfügbare Unterpakete

In der *AMS*-LATEX-Distribution finden Sie auch Komponenten, die unabhängig voneinander mit dem Befehl `\usepackage` geladen werden können. Die folgenden kleineren Pakete bieten einige Funktionen des *amsmath*-Pakets:

|||
|---|---|
| `amsopn` | Stellt `\DeclareMathOperator` zum Definieren neuer Operatornamen wie `\Ker` und `\esssup` bereit. |
| `amstext` | Stellt den Befehl `\text` zum Setzen eines Textfragments in der richtigen Schriftgröße bereit. |

## Erweiterungspakete

Die unten aufgeführten Pakete stellen zusätzliche Funktionen bereit und müssen explizit geladen werden.

|||
|---|---|
| `amscd` | Definiert einige Befehle, um die Generierung kommutativer Diagramme zu erleichtern. |
| `amsthm` | Stellt eine Methode zum Deklarieren theoremähnlicher Strukturen bereit und bietet eine `proof`-Umgebung. |
| `amsxtra` | Stellt bestimmte Kleinigkeiten bereit, die für die historische Kompatibilität erforderlich sind, wie `\fracwithdelims`, `\accentedsymbol` und Befehle zum Platzieren von Akzenten als hochgestellte Zeichen. |
| `upref` | Bewirkt, dass `\ref` Querverweisnummern kontextunabhängig in aufrechter/römischer Schriftart druckt. |