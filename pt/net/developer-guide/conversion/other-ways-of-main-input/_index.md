---
translation: true
template: /templates/_template-net.md
title: Outras maneiras de fornecer o principal arquivo de entrada TeX principal | .NET
linktitle: Outras maneiras de fornecer o principal arquivo de entrada TeX
weight: 14
url: /net/other-ways-of-main-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para .NET possui um construtor que aceita um fluxo como o primeiro argumento. Aqui estão alguns exemplos de código.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Fornecendo o arquivo de entrada principal para o mecanismo TeX como um fluxo

Até este ponto, sabíamos apenas como passar o [arquivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#TeX-input) para o mecanismo TeX como nome de arquivo, totalmente especificado ou de curta forma, seja com uma extensão ou sem ele. Mas há outro [construtor](https://reference.aspose.com/tex/net/aspose.tex/TeXJob/TeXJob/) da classe `TeXJob`, que leva um fluxo como o primeiro argumento. Isso é conveniente se, por algum motivo, tivermos o arquivo de entrada principal em um formulário que não seja um arquivo no sistema de arquivos de disco. Veja como pode ser implementado:

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-StreamInput-LaTeX.cs" >}}

Observe que todos os arquivos de saída terão o nome *texput*. Isso porque o motor não pode obter nenhum outro nome em nenhum lugar. *texput* é o nome da tarefa padrão. [Aqui](/tex/{{lang.url-fragment}}net/tex-io/#TeX-output) e [aqui](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) são detalhes sobre nomes de trabalho.

## Entrando no principal arquivo de entrada TeX do terminal

Há ainda outro [construtor](https://reference.aspose.com/tex/net/aspose.tex/TeXJob/TeXJob/) da classe `TeXJob`, que não nos permite especificar a entrada. Então, o que é um trabalho tão TeX que vai processar, você pode se perguntar? Desta vez, precisaremos de um terminal de entrada. O mecanismo TeX nos pedirá para inserir o nome do arquivo no terminal.

Aqui está o código:

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-MainInputTerminal.cs" >}}

Assim que é executado, o motor gruda, esperando que insira o nome do arquivo (com ou sem um caminho, com ou sem uma extensão):


![Janela do terminal](/tex/images/net/Conversion-MainInputTerminal.png)

E é assim que ficaria no terminal de saída, que é o console:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```
