---
translation: true
template: /templates/_template-net.md
title: Installation und Grundkonfiguration | Aspose.TeX .NET
linktitle: Installation und Konfiguration
weight: 18
url: /net/installation-and-basic-configuration/
keywords: TikZ installieren, TikZ konfigurieren, TikZ einrichten
description: Schritt-für-Schritt-Anleitung zur Installation und Konfiguration von TikZ für Ihre TeX- und LaTeX-Dokumente.
lastmod: "2025-06-29"
---

{{<section overview>}}

Dieses Kapitel behandelt die Installation und Grundkonfiguration der TikZ-Erweiterung für TeX und LaTeX. Wir bieten Ihnen eine klare Schritt-für-Schritt-Anleitung, die Ihnen den schnellen Einstieg in die Grafikerstellung mit TikZ erleichtert.

## TikZ installieren

TikZ ist in gängigen TeX-Distributionen wie **TeX Live** und **MiKTeX** vorinstalliert. Wenn Sie diese Distributionen verwenden, ist TikZ wahrscheinlich bereits installiert. Andernfalls folgen Sie diesen Anweisungen:

### TeX Live-Benutzer

1. Öffnen Sie den TeX Live Manager (`tlmgr`).
2. Aktualisieren Sie die Paketliste:

   ```bash
   tlmgr update --self --all
   ```
3. Installieren Sie TikZ (Teil des Pakets `pgf`):

   ```bash
   tlmgr install pgf
   ```

### MiKTeX-Benutzer

1. Öffnen Sie die MiKTeX-Konsole.
2. Navigieren Sie zum Reiter **Pakete**.
3. Geben Sie `pgf` in die Suchleiste ein.
4. Wählen Sie das Paket `pgf` aus und installieren Sie es, falls es noch nicht installiert ist.

## Installation überprüfen

Sie können die erfolgreiche Installation von TikZ mit diesem einfachen Testdokument überprüfen:

```tex
\documentclass{article}
\usepackage{tikz}

\begin{document}

Testing TikZ:
\begin{tikzpicture}
  \draw (0,0) rectangle (2,1);
\end{tikzpicture}

\end{document}
```

Kompilieren Sie dieses Dokument mit `pdflatex` oder einem LaTeX-kompatiblen Editor (z. B. TeXworks oder Overleaf). Im resultierenden PDF sollte ein kleines Rechteck angezeigt werden.

## Grundkonfiguration von TikZ

TikZ erfordert nur minimale Konfiguration. Sie können jedoch globale Optionen zur Steuerung des Grafikverhaltens festlegen:

- **Grafiken global skalieren**:

  ```tex
  \tikzset{every picture/.style={scale=1.5}}
  ```

- **Standardfarben und Linienstile festlegen**:

  ```tex
  \tikzset{
    every path/.style={thick, blue},
    every node/.style={font=\small}
  }
  ```

Fügen Sie diese Befehle in die Präambel Ihres Dokuments ein, um eine einheitliche Formatierung zu gewährleisten.

## Empfohlene Editoren für TikZ

Für komfortables Bearbeiten und Echtzeitkompilieren empfehlen wir die folgenden LaTeX-Editoren:

- **TeXstudio** – Kostenloser, funktionsreicher Editor mit integrierter TikZ-Vorschau.
- **Overleaf** – Cloudbasierter, kollaborativer Editor mit hervorragender TikZ-Unterstützung.
- **Visual Studio Code** mit der Erweiterung **LaTeX Workshop** – Moderner, schlanker Editor mit TikZ-Unterstützung.

Wählen Sie einen Editor entsprechend Ihren Präferenzen und Workflow-Anforderungen.

---

Mit dieser Anleitung haben Sie TikZ erfolgreich eingerichtet und können beeindruckende Grafiken für Ihre TeX- und LaTeX-Dokumente erstellen.

**Entdecken Sie außerdem unsere kostenlose [Web-App](https://products.aspose.app/tex/conversion/latex/), die auf [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) basiert, für schnelle und einfache TeX-Konvertierungen.**