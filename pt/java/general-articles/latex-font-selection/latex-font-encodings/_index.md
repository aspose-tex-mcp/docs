---
translation: true
template: /templates/_template-java.md
linktitle: 1. Entrada e saída
title: Codificações de entrada e saída | Aspose.TeX para java
weight: 10
url: /java/latex-font-encodings/
keywords: LATEX, fontes de LaTeX, codificações de fontes de LaTeX, NFSS
description: Este artigo explica brevemente os conceitos de codificação de entrada e saída no LaTeX. Também menciona o novo esquema de seleção de fontes (NFSS).
lastmod: "2025-06-16"
---

{{<section overview>}}

Se pressionarmos uma tecla em um teclado, algum código numérico será gerado representando um determinado caractere. Uma entrada que codifica mapeia um caractere para o código correspondente. Por exemplo, em um teclado alemão, caracteres acentuados (como o caráter 'A-UMLAUT') podem ser mapeados para diferentes códigos sob diferentes sistemas operacionais.

Um documento armazenado em um arquivo de computador contém apenas códigos de caracteres, mas as informações sobre a codificação de entrada não estão explicitamente incluídas. Portanto, se você transferir um arquivo para um ambiente diferente, como, do United declarado para o Reino Unido, poderá descobrir que os sinais de dólar em seu documento são de repente interpretados como símbolos de libra quando você vê seu arquivo com algum programa que faz com que a suposição errada sobre a codificação de entrada.

O pacote `inputenc`, desenvolvido pela equipe do Projeto LATEX, pretendia ajudar com problemas de codificação de entrada. Ele permite que os usuários especifiquem explicitamente a codificação de entrada usada para documentos ou partes de documentos. Esse mecanismo torna seguro transferir documentos de uma instalação de LaTeX para outro, obtendo resultados impressos idênticos.

O pacote `inputenc` interpreta os códigos de caracteres no arquivo e os mapeia para uma *representação interna do LaTex*, que abrange exclusivamente todos os caracteres representáveis ​​no LATEX. Durante um processamento adicional, como escrever para algum arquivo auxiliar, o LATEX usa essa representação interna, evitando assim qualquer interpretação errônea.

No entanto, mais cedo ou mais tarde, o LaTeX precisa associar essas representações internas de caracteres a *Glyphs* (formas de caracteres em certas fontes), para que outro mapeamento seja necessário. Existem no máximo 256 glifos em qualquer fonte Tex. Esses glifos não são abordados pelo nome, mas por números de 8 bits representando as posições dos glifos na fonte. Isso significa que temos que mapear de um grande espaço de nomeação exclusiva em vários pequenos, e essas posições de glifos podem variar amplamente, o que não é surpreendente.

Portanto, embora tenhamos preservado o significado do sinal de dólar do arquivo externo para os internos do LATEX, ainda podemos encontrar formas erradas no papel se selecionarmos uma fonte para impressão que tenha um glifo inesperado na posição que assumimos que fosse reservado para um sinal de dólar. Uma das tarefas de **nfss** (o novo esquema de seleção de fontes do LATEX **) é garantir que qualquer representação interna do caractere de LaTeX seja renderizada corretamente ou, se isso for impossível, por algum motivo, que o usuário receba uma mensagem de erro adequada.

Se uma fonte contiver caracteres acentuados como glifos individuais, em vez de apenas caracteres base mais sotaques (dos quais a Tex constrói caracteres acentuados internamente), o uso desses glifos é preferível, pois eles geralmente têm uma aparência melhor. Outra razão (técnica) para usar esses glifos compostos é que a `\accent` primitiva suprimirá a hifenação.

Para se adequar a diferentes casos, um comando como `\ 'e` (representação interna do LaTex para o personagem' E-Aguda ') às vezes precisa iniciar ações complicadas envolvendo o `\acentuar` primitivo e, às vezes, apenas informa ao construtor de parágrafos que precisa do glifo de um certo *slot* (posição) na fontra atual.

Tudo isso é alcançado através do conceito de codificações *de saída*, que são mapeamentos das representações internas de caracteres do LateX para posições de glifos apropriadas ou para ações de construção de glifos, dependendo dos glifos reais disponíveis na fonte usada para digitar.

Os seguintes artigos discutem a versão 2 do NFSS, que se tornou parte do LaTex padrão em 1994.