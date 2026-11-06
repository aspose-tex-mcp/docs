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

Defina `ASPOSE_TEX_OUTPUT_DIR` como o diretório de saída (padrão: `output`). Aplique uma licença primeiro. [Licensing](/tex/pt/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Codifique um documento LaTeX completo em um fluxo binário `BytesIO` e passe-o a `TeXJob` com `TeXConfig.object_latex`. Mantenha o fluxo aberto durante o trabalho. Resultado: `texput.xps` e `texput.log`.

Observe que todos os arquivos de saída serão nomeados `Texput`. Isso ocorre porque o mecanismo não tem acesso a nenhum outro nome. `texput` é o nome da tarefa padrão. Você pode encontrar informações mais detalhadas sobre os nomes de empregos [saída Tex](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [como definir o nome do trabalho](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) parágrafos.

## Entrando o principal arquivo de entrada Tex através do terminal

Há [mais um construtor](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponível na classe [Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) que não nos permite especificar a entrada. Você pode estar se perguntando o que esse trabalho de Tex processaria. Nesse caso, precisaríamos usar um terminal de entrada. O mecanismo TEX nos levará a inserir o nome do arquivo no terminal.

Aqui está o código:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Salve o texto TeX simples abaixo como `hello-world.tex` em `ASPOSE_TEX_INPUT_DIR` (padrão: `input`). O exemplo usa `TeXConfig.object_tex()`. Quando solicitado, digite `hello-world.tex` e pressione Enter, ou forneça o nome pela entrada padrão. Resultado: `hello-world.xps` e `hello-world.log`.

```tex
Hello, World!
\end
```
