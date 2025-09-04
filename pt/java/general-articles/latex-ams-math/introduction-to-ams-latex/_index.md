---
translation: true
template: /templates/_template-java.md
linktitle: AMS-Latex
title: 1. Introdução ao AMS-Latex | Manual de LaTeX
weight: 10
url: /java/introduction-to-ams-latex/
keywords: AMS-LATEX, AMSMATH, AMSMATH OPÇÕES, AMSOPN, AMSTEXT, AMSCD, AMSTHM, AMSXTRA, UPREF
description: Este artigo é uma breve introdução no pacote da Amsmath e abrange brevemente suas opções, bem como subpackagens e extensões disponíveis.
lastmod: "2025-06-16"
---

{{<section overview>}}


*AMS*-LATEX A versão 1.0 foi lançado em 1990 e apresentou a conversão original em LaTeX dos recursos de matemática no*ams*-tex de Michael Spivak, de Frank Mittelbach e Rainer Schopf, que trabalhavam como consultores do*AMS*, com a assistência de Michael Downes of the*AMS*Tech Staff. Em 1994, o trabalho adicional foi realizado com David M. Jones.

* O pacote AMSMATH* aceita algumas opções que afetam principalmente o posicionamento de* limites* em vários operadores de matemática ou no posicionamento das tags de equação.

## Disponível * AMSMATH * Opções do pacote

As três opções a seguir podem ser usadas como opções globais de documentos (especificadas no comando `\documentclass`) ou como *amsmath* opções de pacote quando for carregado com o comando `\usepackage`.

|||
|---|---|
| `reqno` **(padrão)** | Posiciona os números das equações (tags) à direita. |
| `leqno` | Posiciona os números das equações (tags) à esquerda (padrão, quando se utilizam as classes de documento *AMS*-LATEX). |
| `fleqn` | Posiciona as equações com um recuo fixo da margem esquerda, em vez de estarem centradas na coluna de texto. |

## Subpackagens disponíveis

Na distribuição *ams*-latex, você também pode encontrar componentes que podem ser carregados independentemente pelo comando `\usepackage`. Os pacotes menores a seguir fornecem alguns recursos do pacote *amsmath*:

|||
|---|---|
| `amsopn` | Fornece `\DeclareMathOperator` para definir novos nomes de operadores, como `\Ker` e `\esssup`. |
| `amstext` | Fornece o comando `\text` para compor um fragmento de texto no tamanho de letra correcto. |

## Pacotes de extensão

Os pacotes listados abaixo fornecem recursos adicionais e devem ser carregados explicitamente.

|||
|---|---|
| `amscd` | Define alguns comandos para facilitar a geração de diagramas comutativos. |
| `amsthm` | Fornece um método para declarar estruturas semelhantes a teoremas e oferece um ambiente de `prova`. |
| `amsxtra` | Fornece certos detalhes necessários para a compatibilidade histórica, como `\fracwithdelims`, `\accentedsymbol` e comandos para colocar acentos como sobrescritos. |
| `upref` | Faz com que `\ref` imprima números de referência cruzada em tipo de letra vertical/romano, independentemente do contexto. |