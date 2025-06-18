---
translation: true
template: /templates/_template-cpp.md
title: Outras opções de gerenciamento de Tex | C ++
linktitle: Outras opções
weight: 17
url: /cpp/other-options/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para C ++ Vamos definir o modo de interação inicial no qual o mecanismo inicia. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Como definir o modo de interação

Como mencionamos [aqui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para C ++** Permite definir o modo de interação inicial no qual o motor inicia. Aqui está como fazemos isso:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Como definir o nome do trabalho

Quando passamos o arquivo de entrada principal como um nome de arquivo, obtemos arquivos de saída com o mesmo nome, embora com outras extensões. O mecanismo TEX chama o nome do arquivo de entrada de *nome do trabalho* e o usa para arquivos de saída, exceto nos casos em que os arquivos auxiliares com outros nomes especificados explicitamente são gravados. Quando passamos pelo arquivo de entrada principal como um [Stream](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), o mecanismo TEX usa o nome da tarefa padrão, que é *texput*.
Nos dois casos, podemos substituir o nome do trabalho atribuindo a opção de conversão apropriada.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## Como repetir o trabalho

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) em relação a rótulos e referências, há casos em que gostaríamos de executar o mesmo trabalho duas vezes. Aqui está como isso pode ser feito:
```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```