---
translation: true
template: /templates/_template-net.md
title: Grundlagen der TikZ-Nutzung | Aspose.TeX .NET
linktitle: Grundlagen von TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: TikZ-Grundlagen, TikZ-Grundlagen, TikZ-Tutorial
description: Lernen Sie die grundlegenden Prinzipien und Befehle von TikZ kennen, um Grafiken für Ihre TeX- und LaTeX-Dokumente zu erstellen.
lastmod: "2026-04-22"
---

{{<section overview>}}

In diesem Kapitel lernen Sie die grundlegenden Prinzipien und Befehle von TikZ kennen. Wenn Sie diese Grundlagen verstehen, können Sie klare und ausdrucksstarke Grafiken für Ihre Dokumente erstellen.

## Koordinatensystem in TikZ

TikZ-Grafiken basieren auf Koordinaten. Koordinaten definieren Positionen innerhalb Ihrer Zeichnungen und können auf verschiedene Arten angegeben werden:

- **Kartesische Koordinaten (x,y)**:

```tex
\draw (0,0) -- (2,2);
```

- **Polarkoordinaten (Winkel:Radius)**:

```tex
\draw (0,0) -- (45:2);
```

Koordinaten können innerhalb einer Zeichnung beliebig gemischt werden, um das gewünschte grafische Ergebnis zu erzielen.

## Grundlegende Formen zeichnen

TikZ ermöglicht die einfache Erstellung grundlegender geometrischer Formen:

- **Linien und Polylinien**:

```tex
\draw (0,0) -- (1,1) -- (2,0);
```

- **Rechtecke**:

```tex
\draw (0,0) rectangle (2,1);
```

- **Kreise und Ellipsen**:

```tex
\draw (1,1) circle (0.5);
\draw (3,1) ellipse (1 and 0.5);
```

## Farben und Füllmuster

Farben und Füllungen verbessern die visuelle Klarheit deutlich. Sie können Farben direkt festlegen oder vordefinierte Namen verwenden:

```tex
\draw[red, thick] (0,0) rectangle (1,1);
\draw[fill=blue!20] (2,0) circle (0.5);
```

Die Syntax „blue!20“ steht für eine blaue Farbe mit 20 % Intensität.

## Linienarten und -stärke

Mit TikZ können Sie Linienarten und -stärke anpassen, um die grafische Darstellung zu verbessern:

- **Linienstärke**:

```tex
\draw[ultra thick] (0,0) -- (1,1);
\draw[thin] (1,0) -- (2,1);
```

- **Gestrichelte und gepunktete Linien**:

```tex
\draw[dashed] (0,0) -- (2,2);
\draw[dotted] (2,0) -- (4,2);
```

## Knoten und Beschriftungen

Mit Knoten können Sie ganz einfach Textanmerkungen hinzufügen:

```tex
\draw (0,0) -- (1,1) node[midway, above] {label};
```

Sie können Beschriftungen präzise relativ zu Ihren Grafikelementen positionieren und so die Lesbarkeit verbessern.

## Pfade und Kurven

TikZ-Pfade können gerade Linien oder Kurven sein. Kurven werden mit einer einfachen Syntax erstellt:

```tex
\draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Kontrollpunkte formen die Krümmung intuitiv.

## Gruppieren von Elementen

Das Gruppieren von Grafikelementen vereinfacht Transformationen (wie Skalierung und Drehung):

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Elemente innerhalb des Gültigkeitsbereichs werden gemeinsam gedreht und skaliert, wobei die Ausrichtung erhalten bleibt.

---

Die Beherrschung dieser grundlegenden TikZ-Konzepte und -Befehle bildet die Grundlage für die Erstellung anspruchsvoller Grafiken für Ihre Dokumente.

**Entdecken Sie außerdem unsere kostenlose [Web-App](https://products.aspose.app/tex/conversion/latex/) basierend auf der [Aspose.TeX für .NET API](https://products.aspose.com/tex/net/) für schnelle und einfache TeX-Konvertierungen.**
