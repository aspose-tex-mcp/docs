---
translation: true
template: /templates/_template-java.md
linktitle: Schema di selezione dei caratteri
title: Schema di selezione dei caratteri in LaTeX
weight: 60
url: /java/latex-font-selection/
keywords: Font in LaTeX, LaTeX, selezione dei caratteri in LaTeX, NFSS
description: Questo articolo descrive brevemente l'uso dei caratteri in LaTeX nei documenti di elaborazione. Menta anche le metriche dei font Tex e le forme dei personaggi.
lastmod: "2025-06-13"
---

{{<section overview>}}


Durante l'elaborazione del documento di origine, il sistema di composizione in LaTeX non ha molte conoscenze sul carattere che sta utilizzando. Calcola solo le posizioni dei personaggi, senza dover conoscere le forme. Le informazioni più cruciali che richiedono sono le scatole nere *black boxes*, che sono definite dalle loro larghezze, altezze e profondità. Queste dimensioni sono archiviate in un file esterno separato noto come file di font tex (`.tfm`) per ciascun carattere.

Le cappelle del personaggio entrano in gioco più tardi. Se un sistema in LaTeX produce un file `.dvi`, un programma * driver * combina i dati di posizionamento dei caratteri dal file` .dvi` con informazioni sulle forme dei caratteri dal file `.pk` o dalle descrizioni del contorno (come PostScript) per produrre l'immagine dei caratteri sul mezzo di output. Tuttavia, altri sistemi in LaTeX come **pdf tex** o **vtex** bypassano la produzione di un file `.dvi` e generano invece direttamente **pdf** o **postcast** output. In tal caso, le forme del personaggio sono incorporate quando il formatter corrispondente produce l'output finale.