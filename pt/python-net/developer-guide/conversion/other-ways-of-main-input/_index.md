---
translation: true
template: /templates/_template-python-net.md
title: Métodos alternativos para fornecer o arquivo de entrada TEX principal | Python via .NET
linktitle: Outras maneiras de fornecer o principal arquivo de entrada tex
weight: 14
url: /python-net/other-ways-of-main-input/
description: Solução da API do Aspose.TeX para Python inclui um construtor que aceita um fluxo como o primeiro argumento, fornecendo funcionalidade de conversão.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Fornecendo o arquivo de entrada principal ao mecanismo TEX usando um fluxo

Até agora, aprendemos apenas a fornecer o [arquivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) ao mecanismo TEX como nome de arquivo, seja em sua forma completa ou em uma forma reduzida, com ou sem uma extensão. No entanto, existe [outro construtor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponível na classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) que aceita um fluxo como o primeiro argumento. Isso é útil se, por algum motivo, o principal arquivo de entrada não estiver na forma de um arquivo no sistema de arquivos de disco. Aqui está um exemplo de como ele pode ser implementado:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Observe que todos os arquivos de saída serão nomeados `Texput`. Isso ocorre porque o mecanismo não tem acesso a nenhum outro nome. `texput` é o nome da tarefa padrão. Você pode encontrar informações mais detalhadas sobre os nomes de empregos [saída Tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [como definir o nome do trabalho](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) parágrafos.

## Entrando o principal arquivo de entrada Tex através do terminal

Há [mais um construtor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponível na classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) que não nos permite especificar a entrada. Você pode estar se perguntando o que esse trabalho de Tex processaria. Nesse caso, precisaríamos usar um terminal de entrada. O mecanismo TEX nos levará a inserir o nome do arquivo no terminal.

Aqui está o código:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Assim que for executado, o motor pausa e aguardará a inserção do nome do arquivo (com ou sem caminho, e com ou sem uma extensão):


![Janela do terminal](/tex/images/python-net/.png)

E aqui está como ele apareceria no terminal de saída (console):

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