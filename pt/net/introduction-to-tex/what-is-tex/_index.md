---
translation: true
template: /templates/_template-net.md
title: O que é Tex? | Aspose.TeX .net
linktitle: O que é Tex?
weight: 10
url: /net/what-is-tex/
keywords: O que é Tex
description: Esta página responde brevemente à pergunta "O que é Tex?" É uma das linguagens de programação ou é considerado um formato de documento?
lastmod: "2025-06-16"
---

{{<section overview>}}

## O que Tex não é

Tex definitivamente não é um formato.

## O que é Tex?

Então, o que é Tex? Bem, essa é a questão, como Hamlet [^1] disse. Vamos tentar responder o mais simplesmente possível.

Imagine que temos uma linguagem de programação que consiste em dois comandos elementares (chamados *seqüências de controle*) ou *primitivas*, `\a` e `\b`. E nesse idioma, podemos escrever programas para documentos (livros, artigos etc.). Vamos chamar esse idioma **(L1)**. Para que esses programas sejam executados de uma certa maneira, temos um certo mecanismo que interpreta os comandos desse idioma.

Agora, vamos supor que, ao escrever um programa de composição para algum documento, descobrimos que a subseqüência `\a \ b \ a` ocorre com bastante frequência. E também suponha que em nosso idioma exista outro `\def`, que nos permite definir sub -rotinas ou macros. Vamos chamar esse idioma **(l2)**. Nessas circunstâncias, podemos definir a macro `\def \ c {\ a \ b \ a}` no início do programa e substituir cada ocorrência da subsequência com `\c`ambos para melhor legibilidade e redução.

Agora, se quisermos compensar outro documento, no programa do qual essa subseqüência de comandos também ocorre com frequência, teremos que definir essa macro novamente. Mas vamos supor que nosso mecanismo seja capaz de carregar a macro `\c` em seu estado interno e, em seguida, salvar esse estado como um arquivo binário (a *despejo*), que será carregado automaticamente (" no topo "do que o conjunto de idiomas **(L2)** é necessário. Chamaremos o conjunto de primitivas estendidas pelo formato `\ C` Macro A *. Assim, nosso formato é uma *extensão macro* da linguagem primitiva de baixo nível **(L2)**.

O mecanismo também contém vários registros internos, ou *parâmetros internos*, que podem ser acessados ​​usando sequências de controle. Além das definições de macro, um formato pode conter expressões de inicialização para esses parâmetros.

Aconteceu que <a href = "https://en.wikipedia.org/wiki/donald_knuth" Target = _blank rel = "Nofollow"> Donald E. Knuth </a>, definiu um idioma semelhante a **(l2)**, mas com um conjunto muito amplo de primitivas, que ele chamou de Tex. Ele também criou um mecanismo que entendeu (e ainda faz) o idioma Tex. Ele também chamou de Tex.

Felizmente, essas não eram as únicas coisas que ele fez. Ele também propôs a extensão macro, ou formato, chamou *Plain* tex, que tornou os programas de redação mais convenientes. O conjunto inicial das primitivas da TEX às vezes é chamado de Virtex ("Vir" para "Virgin") e, formalmente, também é um formato, quando considerado junto com os padrões de parâmetros internos.

**Então, por um lado, Tex é uma linguagem de programação. E, por outro lado, é um mecanismo de intérprete que entende esse idioma. E, por terceira mão, Tex é um conceito mais geral, que significa um sistema de digitação no todo.**

A única coisa que resta a ser observada aqui é que, de fato, os caracteres do próprio texto que estão com o TypeT também são comandos que forçam o mecanismo TEX a digitar caracteres correspondentes (levando em consideração a codificação de entrada atual) usando as configurações de fonte atual (que, por sua vez, são controláveis ​​por sequências de controle). Assim, ao definir macros, também podemos usar caracteres.

Esperamos que a partir de agora na pergunta "O que é Tex?" não existe mais em sua mente.
[^1]: 1 