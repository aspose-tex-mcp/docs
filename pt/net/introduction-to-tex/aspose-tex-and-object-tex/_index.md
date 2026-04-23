---
translation: true
template: /templates/_template-net.md
linktitle: Object TeX
title: Aspose.TeX e Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: O TeX é um formato de entrada e saída desta solução de API, então aqui vamos explicar o Object TeX e como ele é transformado em um formato de destino.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Object TeX

Agora vamos considerar o formato de saída.

O TeX original foi capaz de produzir arquivos * DVI * (Independente do dispositivo) somente o formato. Aconteceu que o formato DVI não define métricas de uma mídia na qual um arquivo será impresso-o tamanho da página e a posição do canto superior esquerdo de todo o conteúdo da página. Depois de decidirmos tornar o mecanismo TeX capaz de produzir arquivos, digamos, no formato PDF, precisamos definir essas métricas. Assim, precisamos incluir novos primitivos no conjunto original do TeX Engine. E isso seria uma extensão do próprio motor.

Isso é o que *Object* TeX é. Novamente, **, por um lado, é uma linguagem de programação com o conjunto de primitivos da VirTeX, expandida com novos primitivos impostos por novos requisitos de saída. Por outro lado, é um mecanismo TeX estendido que também entende novas primitivas. E, por terceira mão, Object TeX é um novo sistema de tipo de composição no todo.**

Aí está a quarta mão. O formato Object TeX também é um formato baseado no PLAIN TeX que contém definições que envolvem novas primitivas, por exemplo, atribuem valores padrão às métricas de mídia.

## Aspose.TeX

E Aspose.TeX é apenas uma API para o sistema Object TeX.

## Por que o novo TeX é Object?

Então, por que usamos "objeto" em nome do sistema? O motivo é que a saída real do mecanismo TeX objeto não é um arquivo no formato de saída, mas algum modelo intermediário *objeto*, que é então transformado em um formato de destino.