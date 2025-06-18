---
translation: true
template: /templates/_template-java.md
linktitle: Esquema de seleção de fontes
title: Esquema de seleção de fontes de LaTeX | Aspose.TeX para java
weight: 60
url: /java/latex-font-selection/
keywords: LATEX, fontes de LaTeX, seleção de fontes de LaTeX, NFSS
description: Este artigo descreve brevemente o uso de fontes de LaTeX nos documentos de processamento. Também menciona métricas de fonte Tex e formas de personagens.
lastmod: "2025-06-16"
---

{{<section overview>}}


Ao processar o documento de origem, o sistema de tipógrafo de LaTeX não possui muito conhecimento sobre a fonte que está usando. Ele apenas calcula as posições dos caracteres, sem precisar conhecer formas. As informações mais cruciais necessárias são as caixas pretas dos caracteres *, que são definidas por suas larguras, alturas e profundidades. Essas dimensões são armazenadas em um arquivo externo separado, conhecido como um arquivo Tex Font Metric (`.tfm`) para cada fonte.

As capas de personagem entram em jogo mais tarde. Se um sistema de LaTeX produzir um arquivo `.dvi`, um programa *driver* combina dados de colocação de caracteres do arquivo` .dvi` com informações sobre formas de caracteres do arquivo `.pk` ou de descrições de esboço (como PostScript) para produzir a imagem do caractere no meio de saída. No entanto, outros sistemas de LaTeX como **pdf tex** ou **vtex** ignoram a produção de um arquivo `.dvi` e, em vez disso, geram diretamente **pdf** ou **PostScript** Saída. Nesse caso, as formas de caracteres são incorporadas quando o formatador correspondente produz a saída final.