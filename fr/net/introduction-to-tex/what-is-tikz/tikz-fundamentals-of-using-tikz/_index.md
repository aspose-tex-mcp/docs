---
translation: true
template: /templates/_template-net.md
title: Principes fondamentaux de TikZ | Aspose.TeX .NET
linktitle: Principes fondamentaux de TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: Principes fondamentaux de TikZ, Principes fondamentaux de TikZ, Tutoriel TikZ
description: Explorez les principes fondamentaux et les commandes de base de TikZ pour créer des graphiques pour vos documents TeX et LaTeX.
lastmod: "2026-04-22"
---

{{<section overview>}}

Dans ce chapitre, nous explorons les principes et commandes fondamentaux de TikZ. Comprendre ces bases vous permettra de créer des graphiques clairs et expressifs pour vos documents.

## Système de coordonnées dans TikZ

Les graphiques TikZ sont créés à partir de coordonnées. Les coordonnées définissent des positions dans vos dessins et peuvent être spécifiées de différentes manières :

- **Coordonnées cartésiennes (x, y)** :

```tex
\draw (0,0) -- (2,2);
```

- **Coordonnées polaires (angle : rayon)** :

```tex
\draw (0,0) -- (45:2);
```

Les coordonnées peuvent être librement combinées dans un dessin pour obtenir le résultat graphique souhaité.

## Dessin de formes simples

TikZ permet de créer facilement des formes géométriques simples :

- **Lignes et polylignes** :

```tex
\draw (0,0) -- (1,1) -- (2,0);
```

- **Rectangles**:

```tex
\draw (0,0) rectangle (2,1);
```

- **Cercles et ellipses** :

```tex
\draw (1,1) circle (0.5);
\draw (3,1) ellipse (1 and 0.5);
```

## Couleurs et motifs de remplissage

Les couleurs et les motifs de remplissage améliorent considérablement la clarté visuelle. Vous pouvez spécifier les couleurs directement ou utiliser des noms prédéfinis :

```tex
\draw[red, thick] (0,0) rectangle (1,1);
\draw[fill=blue!20] (2,0) circle (0.5);
```

La syntaxe « blue!20 » désigne une couleur bleue d'intensité 20 %.

## Styles et épaisseurs de ligne

TikZ vous permet de modifier les styles et l'épaisseur des lignes pour améliorer la présentation graphique :

- **Épaisseur de ligne** :

```tex
\draw[ultra thick] (0,0) -- (1,1);
\draw[thin] (1,0) -- (2,1);
```

- **Lignes pointillées et en pointillés** :

```tex
\draw[dashed] (0,0) -- (2,2);
\draw[dotted] (2,0) -- (4,2);
```

## Nœuds et étiquettes

Les nœuds vous permettent d'ajouter facilement des annotations textuelles :

```tex
\draw (0,0) -- (1,1) node[midway, above] {label};
```

Vous pouvez positionner précisément les étiquettes par rapport à vos éléments graphiques, améliorant ainsi leur lisibilité.

## Tracés et courbes

Les tracés TikZ peuvent être des lignes droites ou des courbes. Les courbes sont créées à l'aide d'une syntaxe simple :

```tex
\draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Les points de contrôle façonnent la courbure de manière intuitive.

## Regroupement d'éléments

Le regroupement d'éléments graphiques simplifie les transformations (comme la mise à l'échelle et la rotation) :

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Les éléments de la « portée » pivotent et se redimensionnent ensemble, préservant ainsi l'alignement.

---

La maîtrise de ces concepts et commandes TikZ fondamentaux vous permettra de créer des graphiques sophistiqués pour vos documents.

**De plus, découvrez notre application web gratuite basée sur l'API Aspose.TeX pour .NET pour des conversions TeX rapides et faciles.**
