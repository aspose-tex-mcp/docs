---
translation: true
template: /templates/_template-net.md
title: Entrada/saída de LaTeX
linktitle: E/O do LATEX
weight: 17
url: /net/latex-io/
description: Esta página descreve brevemente as peculiaridades de trabalhar com o LATEX como um formato de saída ou entrada e o arquivo * .aux * como parte obrigatória do LATEX.
keywords: LATEX IO, LATEX I, LATEX O, LATEX INPUT FILE, entrada no LATEX
lastmod: "2025-06-16"
---

{{<section overview>}}

## Arquivo de LaTeX

Se tivermos um [Tex File](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) que tenha a seguinte estrutura, chamaremos esse arquivo de arquivo *LATEX*:


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

onde `<uma classe de documento>` é um nome de uma [classe de documento](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes), que é um arquivo tex de entrada que define a aparência das páginas e macros do documento de saída que são mais adequadas para um certo tipo de documento.

Para ser sincero, você pode inserir sequências de controle primitivo antes de `\documentclass {}`, como `\não -estopmode`, etc. Mas cada macro de LaTeX verifica se está localizado em uma parte adequada de um arquivo.

Vale a pena notar algumas coisas sobre Tex [entrada](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) e [saída](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) no contexto do trabalho com arquivos de LaTeX.

## Arquivo de saída de LaTeX

Um trabalho típico de LaTeX cria um arquivo de saída auxiliar com o [nome do trabalho](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) como nome e extensão *.aux*. Esse arquivo geralmente contém dados de referência que o mecanismo coleta ao longo da execução do trabalho, se você, digamos, define rótulos para fórmulas de matemática (equações) e, em seguida, se refere a eles em algum lugar do texto. Caso você não use nada desse tipo, este arquivo contém apenas a sequência de controle `\relax` (que é uma das primitivas TEX). Portanto, não se surpreenda.

Embora os primitivos `\openout`, ` \ write` e `\closeout` não sejam proibidos, os pacotes são o local mais adequado para eles. Portanto, você deve usá -los melhor em seus próprios pacotes personalizados se estiver desenvolvendo -os.

Outras partes da saída são arbitrárias, também seguem o conceito Geral [Tex Output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e dependem do que exatamente o seu arquivo tex (programa) deve fazer, quais pacotes (veja abaixo) que você está usando, etc.

## Arquivo de entrada de LaTeX

O arquivo *.aux* acima mencionado é uma parte obrigatória da entrada no LaTeX ao mesmo tempo. Algoritmicamente, o LaTeX não pode realizar essas tarefas relacionadas a referência em uma única execução; portanto, o mesmo trabalho precisa ser executado duas vezes-a primeira vez para coletar dados, na segunda vez para usar esses dados. Muitos sistemas de software baseados em LaTeX executam trabalhos de LaTeX duas vezes automaticamente. Spoiler: Existe uma [opção](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) na API Aspose.TeX que nos permite controlar esse comportamento.

Outra parte obrigatória é uma [classe de documento](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). O arquivo da classe de documentos, por sua vez, pode depender implicitamente de outros arquivos, que também são incluídos na entrada do LaTeX.

Se você deseja usar os recursos além do escopo do LaTeX básico e de suas classes de documentos, mas suportados por uma determinada implementação do mecanismo Tex, normalmente usa um pacote, sobre o qual deve notificar o mecanismo no preâmbulo. A *pacote de LaTeX* é um arquivo ou um grupo de arquivos montados com um nome, que fornece esses recursos. Para notificar o mecanismo, você precisa usar o comando `\usepackage` com o nome do pacote e opções omitíveis, se o pacote definir algum.

Por exemplo,


```tex
\usepackage[a6paper,landscape]{geometry}
```

Embora `\input`, `\Openin`, `\read` e `\Closein` Primitivos não sejam proibidos, os pacotes são o local mais adequado para eles. Portanto, você deve usá -los melhor em seus próprios pacotes personalizados se estiver desenvolvendo -os.

Outras partes da entrada são arbitrárias, também seguem o conceito Geral [TEX INTRUPT](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) e dependem do que exatamente o seu arquivo tex (programa) deve fazer, quais pacotes você está usando, etc.