---
translation: true
template: /templates/_template-net.md
linktitle: Objeto tex
title: Aspose.TeX e objeto tex | Aspose.TeX para .NET
weight: 11
url: /net/aspose-tex-and-object-tex/
description: O TEX é um formato de entrada e saída desta solução de API, então aqui vamos explicar o objeto Tex e como ele é transformado em um formato de destino.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Objeto tex

Agora vamos considerar o formato de saída.

O Tex original foi capaz de produzir arquivos * DVI * (Independente do dispositivo) somente o formato. Aconteceu que o formato DVI não define métricas de uma mídia na qual um arquivo será impresso-o tamanho da página e a posição do canto superior esquerdo de todo o conteúdo da página. Depois de decidirmos tornar o mecanismo TEX capaz de produzir arquivos, digamos, no formato PDF, precisamos definir essas métricas. Assim, precisamos incluir novos primitivos no conjunto original do Tex Engine. E isso seria uma extensão do próprio motor.

Isso é o que *objeto* tex é. Novamente, **, por um lado, é uma linguagem de programação com o conjunto de primitivos da Virtex, expandida com novos primitivos impostos por novos requisitos de saída. Por outro lado, é um mecanismo Tex estendido que também entende novas primitivas. E, por terceira mão, o objeto tex é um novo sistema de tipo de composição no todo.**

Aí está a quarta mão. O formato Tex Object também é um formato baseado no PLAIN TEX que contém definições que envolvem novas primitivas, por exemplo, atribuem valores padrão às métricas de mídia.

## Aspose.TeX

E Aspose.TeX é apenas uma API para o sistema Tex do objeto.

## Por que o novo Tex é objeto?

Então, por que usamos "objeto" em nome do sistema? O motivo é que a saída real do mecanismo TEX objeto não é um arquivo no formato de saída, mas algum modelo intermediário *objeto*, que é então transformado em um formato de destino.