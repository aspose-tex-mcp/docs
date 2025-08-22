---
translation: true
template: /templates/_template-net.md
title: Installation et configuration de base | Aspose.TeX .NET
linktitle: Installation et configuration
weight: 18
url: /net/tikz-installation-and-basic-configuration/
keywords: installer tikz, configurer tikz, installer tikz
description: Guide étape par étape pour installer et configurer TikZ pour une utilisation dans vos documents TeX et LaTeX.
lastmod: "2025-06-29"
---

{{<section overview>}}

Ce chapitre décrit l'installation et la configuration de base de l'extension TikZ pour TeX et LaTeX. Nous vous fournirons des instructions claires et détaillées pour vous aider à démarrer rapidement avec la création graphique avec TikZ.

## Installation de TikZ

TikZ est préinstallé avec les distributions TeX les plus populaires, telles que **TeX Live** et **MiKTeX**. Si vous utilisez ces distributions, TikZ est probablement déjà installé. Sinon, suivez ces instructions :

### Utilisateurs de TeX Live

1. Ouvrez le gestionnaire TeX Live (`tlmgr`).
2. Mettez à jour la liste des paquets :

   ```bash
   tlmgr update --self --all
   ```

3. Installez TikZ (partie du package `pgf`) :

   ```bash
   tlmgr install pgf
   ```

### Utilisateurs MiKTeX

1. Ouvrez la console MiKTeX.
2. Accédez à l'onglet **Packages**.
3. Saisissez « pgf » dans la barre de recherche.
4. Sélectionnez et installez le paquet « pgf » s'il n'est pas déjà installé.

## Vérification de l'installation

Vous pouvez vérifier la réussite de l'installation de TikZ avec ce document de test simple :

```tex
\documentclass{article}
\usepackage{tikz}

\begin{document}

Test de TikZ :

\begin{tikzpicture}
  \draw (0,0) rectangle (2,1);
\end{tikzpicture}

\end{document}
```

Compilez ce document avec « pdflatex » ou tout autre éditeur compatible LaTeX (comme TeXworks ou Overleaf). Vous devriez voir un petit rectangle dans le PDF obtenu.

## Configuration de base de TikZ

TikZ nécessite une configuration minimale. Vous pouvez cependant définir des options globales pour contrôler le comportement des graphiques :

- **Mise à l'échelle globale des graphiques** :

  ```tex
  \tikzset{every picture/.style={scale=1.5}}
  ```

- **Définir les couleurs et les styles de ligne par défaut** :

  ```tex
  \tikzset{
    every path/.style={thick, blue},
    every node/.style={font=\small}
  }
  ```

Incluez ces commandes dans le préambule de votre document pour un style cohérent.

## Éditeurs recommandés pour TikZ

Pour une édition confortable et une compilation en temps réel, nous recommandons les éditeurs LaTeX suivants :

- **TeXstudio** – Éditeur gratuit et riche en fonctionnalités avec aperçu TikZ intégré.
- **Overleaf** – Éditeur collaboratif basé sur le cloud avec une excellente prise en charge de TikZ.
- **Visual Studio Code** avec l'extension **LaTeX Workshop** – Éditeur moderne et léger prenant en charge TikZ.

Choisissez un éditeur en fonction de vos préférences et de vos exigences en matière de flux de travail.

---

En suivant ces instructions, vous aurez configuré TikZ avec succès et serez prêt à créer de superbes graphismes pour vos documents TeX et LaTeX.

**De plus, explorez notre [application Web](https://products.aspose.app/tex/conversion/latex/) gratuite basée sur [l'API Aspose.TeX pour .NET](https://products.aspose.com/tex/net/) pour des conversions TeX rapides et faciles.**