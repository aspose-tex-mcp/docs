---
translation: true
template: /templates/_template-java.md
linktitle: Classes de documentos do LATEX
title: Classes de documentos do LATEX | Aspose.TeX para Java
weight: 20
url: /java/latex-document-classes/
keywords: Classe de artigo do LATEX, Latex DocumentClass, Latex Document Model, Latex Article, Latex Book, Slides de Latex, Relatório de Latex, Letter Letter, DocumentClass in Latex
description: Este artigo é um resumo conciso das classes de documentos do LATEX e suas opções. Ele também fornece alguns exemplos.
lastmod: "2026-04-21"
---

{{<section overview>}}

## O que é um documentclass no LaTeX?

O LATEX define algumas regras que todo autor do documento deve seguir. Ele também define a estrutura do arquivo de origem, que é essencialmente um programa de tipógraneo. De acordo com essa estrutura, o código -fonte do documento deve conter uma parte responsável pelo conteúdo do documento em si - *Body* - que é anexado em um par de comandos: `\begin{document}` e `\end{document}` . O LaTeX ignora qualquer coisa que siga o fim do corpo. A parte do código -fonte antes de `\Begin {document}` é chamada de *preâmbulo*.

Normalmente, o primeiro comando no preâmbulo deve ser `\documentclass`, que leva um único argumento exigido que é o nome da classe **do documento**. A classe de documento em si é um conjunto de parâmetros de formatação, métricas de layout, macros etc. que são adequados e úteis para o desenvolvimento de documentos de um determinado tipo e coletados sob o nome único. Neste artigo, discutiremos as classes de documentos predefinidas **do LATEX** que são embutidas e mostraram seus usos, diferenças e semelhanças. Também mencionaremos alguns argumentos opcionais que o comando `\documentclass` pode assumir e que personalizam a aparência do documento.

## Classes de documentos LaTeX predefinidos

O LATEX padrão contém as seguintes classes de documentos:

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | A classe LaTeX article é utilizada para criar artigos para revistas científicas, relatórios curtos, documentação de programas e, em geral, qualquer documento curto que não necessite de uma divisão complexa em capítulos e partes. |
| **report** | A classe LaTeX report é utilizada para artigos longos que podem conter vários capítulos (algo como pequenos livros e teses). |
| **book** | É utilizada para compor livros reais. Inclui todos os tipos de padrões de composição adequados para livros impressos: capítulos e partes, dois tipos de páginas, elementos iniciais, elementos finais, etc. |
| **slides** | Pode ser utilizada para produzir slides, embora exista o pacote externo [beamer](https://ctan.org/pkg/beamer) que é muito mais poderoso para este fim. |
| **letter** | Esta classe de documento é utilizada para escrever cartas. |

As duas primeiras classes de documentos são básicas. Então, comece com **article** sempre que você não tiver certeza de qual classe você precisa.

A classe **report** é muito semelhante. A principal diferença do artigo **** é que você pode inserir capítulos com o comando `\Capítulo`, enquanto a classe **** de documento não define uma unidade de secção.

## O **book** LaTeX

Os livros, em padrões tipográficos, têm a matéria da frente e a matéria traseira, que são a principal diferença entre livros e, por exemplo, relatórios ou artigos. A questão da frente de um livro geralmente consiste em uma página de meio título, uma página de título principal, uma página de direitos autorais, um prefácio ou prefácio e um conteúdo da tabela. Peças menos obrigatórias são reconhecimentos, uma dedicação, uma lista de figuras, uma lista de tabelas, uma lista de outros livros da mesma série e outros conteúdos editoriais e promocionais. A matéria traseira normalmente inclui um índice e pode conter um posfácio, bem como reconhecimentos, uma bibliografia, um colofão etc.

A classe do documento do livro oferece comandos para produzir as estruturas lógicas acima mencionadas, enquanto outras classes de documentos não podem fornecer essas ferramentas. No entanto, diferentes editores geralmente têm seus próprios pacotes com comandos adicionais para estabelecer estruturas de acordo com seu próprio estilo.

## Comandos de matéria da frente, matéria principal e traseira

A questão principal é o que inclui o corpo do livro, começando com o primeiro capítulo ou parte e terminando com os apêndices. Os assuntos da frente, principal e traseira começam com os comandos `\ FrontMatter`, `\mainmatter` e `\backmatter`, respectivamente.

> Na classe dos livros padrão, as páginas da matéria inicial são numeradas com algarismos romanos, enquanto as páginas da matéria principal e final são numeradas com algarismos árabes.

> O comando `\chapter` não produz um número de capítulo nas matérias inicial e final, embora crie uma entrada no sumário. Isto é normalmente utilizado para criar uma secção de prefácio ou agradecimentos. Dentro destes capítulos, apenas devem ser utilizadas as versões com asterisco de outros comandos de seccionamento (como `\section*` e `\subsection`).

## Um exemplo de uso da aula do livro de LaTeX

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

Abaixo está a estrutura do documento gerada por este código de LaTeX:

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-document-classes-1.png)</a>
<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Exemplo de saída](/tex/images/java/tutorial/latex-document-classes-2.png)</a>

E aqui está o índice em detalhes:

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Índice](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## **odd** e **even** páginas em livros

Nos livros, **ímpar** e **até** páginas não parecem iguais. As margens, e geralmente cabeçalhos e rodapés, diferem para tornar o livro mais legível quando está vinculado. A classe de documentos do LATEX lida com isso, e você pode achar que:
- **Esquerda (par)** As páginas têm uma margem esquerda maior, o número da página está no canto superior direito da página e o título do capítulo atual está à direita;
- **Right (Odd)** As páginas têm uma margem direita maior e apenas o número da página no canto superior direito da página.

Observe que novos capítulos sempre começam na página certa, onde a cabeça da página está vazia, deixando apenas o número da página no centro do pé.

## **Resumo** Falta seção

Artigos acadêmicos, como artigos ou relatórios, geralmente incluem uma seção introdutória chamada **"Resumo"**. Seu objetivo é fornecer uma visão geral rápida do tópico abordado no documento. Você pode achá -lo impresso logo após o título e antes do índice, com o título "Resumo" em negrito. No LATEX, essa estrutura é implementada como o ambiente "Resumo".

O ambiente **Resumo** não é fornecido pela classe de documentos do livro, e essa é outra diferença das classes do artigo e do relatório.

## LATEX **Letra** Classe

Atualmente, a classe de documentos da carta parece ser um tanto antiquada (o mesmo acontece com a classe de documentos do slide, na verdade). Se você precisar fazer cartas tradicionais, para colocá -las em envelopes e enviá -las por correio, esta classe de documentos provavelmente será útil para você. Embora esse seja um tipo de maneira obsoleta de comunicação, ainda há casos em que você pode precisar preparar um documento semelhante a uma carta. Por exemplo, uma carta de recomendação ou uma carta de apresentação.

Então, aqui está a breve visão geral da classe.

Você pode gerar qualquer número de letras com um único arquivo de entrada. Seu nome e endereço, que normalmente são os mesmos para todas as letras, geralmente são especificados no preâmbulo do documento. O endereço de retorno é declarado por um comando `\endereço`, que aceita várias linhas separadas por `\\`(o comando de interrupção da linha do LATEX) como o argumento. Da mesma forma, o comando `\Signature`aceita várias linhas, incluindo seu nome, título, etc. No entanto, você pode alterar o endereço de retorno e a assinatura a qualquer momento.

Cada letra é gerada por um ambiente `letra` separado que requer o nome e o endereço do destinatário como argumento. A carta começa com um comando `\abertura`, produzindo a saudação e termina com um comando `\fechando`, produzindo a frase e a assinatura de fechamento. O corpo da letra é a entrada normal de LaTeX.

Todos esses comandos são fáceis de usar e muito poderosos, pois o LaTeX cuida automaticamente da formatação das letras. Portanto, não deixe o número de comandos assustá -lo ou confundir.

O exemplo abaixo demonstra como tudo isso funciona.

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![Um exemplo de classe de documento de carta](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

Observe que a data atual também é produzida automaticamente. No entanto, você pode redefinir o comando `\today` para alterar a data em suas cartas. Aqui está como você faz isso:

```tex
\renewcommand{\today}{01th of March of 2492}
```

Se você inserir essa declaração em um determinado ambiente de 'letra', isso mudará a data apenas para essa carta. Caso contrário, se você o inserir no preâmbulo, ele estará em vigor para todas as cartas geradas pelo arquivo de entrada (a menos que seja inserido em um certo ambiente de 'letra').

## Opções de aula de documentos do LATEX

Agora vamos dar uma olhada nas opções de comando `\documentclass` mencionadas no início do artigo.

### Tamanho da fonte

O tamanho da fonte é controlado por três opções: 10pt, 11pt, 12pt. Por padrão, 10pt está em vigor. Essas opções determinam o tamanho da fonte base usado em todo o documento, a menos que tenha sido alterado em algum momento. Eles também afetam os fatores de escala para algumas dimensões de formatação.

```tex
\documentclass[12pt]{article}
```

> These options are not recognizable by the `slides` class.

### Tamanho do papel

"Tamanho do papel" aqui refere-se ao tamanho da folha de papel na qual **planeia** imprimir o documento. Isto não afeta o tamanho da representação da página na saída de sistemas de composição como o **PDF TeX**. É controlado por 6 opções: `papel carta` (8,5 pol x 11 pol), `papel ofício` (8,5 pol x 14 pol), `papel executivo` (7,25 pol x 10,5 pol), `papel A4` (210 mm x 297 mm), `papel A5` (148 mm x 210 mm) e `papel B5` (176 mm x 250 mm). O predefinido é `papel carta`.

```tex
\documentclass[a4paper]{article}
```

### Orientação da página

A opção `Landscape` torna a saída formatada para impressão de paisagem no tamanho do papel selecionado. Efetivamente, torna o intercâmbio de LaTeX a dimensão de largura e altura, onde quer que sejam usados ​​ao longo do processo de composição. A opção `retrato` não tem esse efeito e é usada por padrão.

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### Modo de rascunho

Sempre que a Tex não pode fazer uma quebra de linha suficientemente boa (ele tem um algoritmo de estimativa de 'bondade') ao longo do processo de construção de parágrafos, produz uma linha que se espalha pela borda direita da área de texto. Ele também relata esses incidentes no arquivo de transcrição (e no terminal) com os avisos de 'Overfull Boxes'. A opção `draft` faz com que o LATEX marque essas linhas com caixas pretas na saída. A opção `final` não produz caixa preta e é usada por padrão.

### Impressão lateral de duas

A opção `Openany` permite que os capítulos iniciem em qualquer página, enquanto a opção` OpenRight` faz com que todos os capítulos comecem em uma página à direita. O padrão é `Openany` na classe` relatório` e `Openright` na classe` book`. Ambas as opções não são reconhecidas em outras classes de documentos.

### Página para o título

Com a opção `titlePage`, o LATEX faz uma página separada para o título produzido pelo comando`\maketitle`. Ele também faz com que o ambiente `abstrato` inicie o resumo em uma nova página e faça uma pausa na página após ele. O padrão é `titlePage` para todas as classes, exceto`artigo ', para o qual é `notitlePage`. 

> Estas opções não são reconhecidas pela classe `letter`.

### Fórmulas exibidas numeradas

A opção `leqno` faz com que o LATEX coloque os números da equação (fórmula matemática exibida) ou tags, no lado esquerdo, em vez do lado direito, que é o comportamento padrão.

### Alinhamento de fórmulas exibido

A opção `fleqn`alinhava fórmulas exibidas à esquerda. Caso contrário, eles são centralizados por padrão.
