---
translation: true
template: /templates/_template-python-net.md
title: Interface de entrada do Aspose.TeX | Python via .NET
linktitle: Interface de entrada do Aspose.TeX
weight: 15
url: /python-net/aspose-tex-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Python com TEX, pois um formato de entrada é explicado aqui com os exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

> Para definições formais da implementação de E/S no **Aspose.TeX para Python**, consulte a [referência da API](https://reference.aspose.com/tex/python-net/aspose.tex.io/).

## A ideia por trás do diretório de entrada

Dado que as primitivas de E/S do idioma Tex só podem lidar com nomes de arquivos, **aspose.tex for python** define um diretório como um mapeamento entre nomes e coleções de dados. Essas coleções de dados podem ser arquivos, fluxos, matrizes ou qualquer outro tipo. A API permite a especificação separada dos diretórios de trabalho de entrada e saída. Ele fornece a classe Geral [InputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputworkingdirectory/), que os usuários podem implementar para suas necessidades específicas. Além disso, a API fornece implementações internas, que serão discutidas posteriormente. A interface inclui o método [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), que recupera o fluxo de dados e determina o nome completo do arquivo com base em um determinado nome, que serve como chave de mapeamento.

### Recuperando a entrada do arquivo do sistema de arquivos de disco

Aqui está a abordagem que adotaríamos:

Defina `ASPOSE_TEX_OUTPUT_DIR` como o diretório de saída (padrão: `output`). Aplique uma licença primeiro. [Licensing](/tex/pt/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.py" >}}

Defina `ASPOSE_TEX_INPUT_DIR` como a pasta com `hello-world.tex` (padrão: `input`). O exemplo usa TeX simples com `TeXConfig.object_tex()` e gera `hello-world.xps` e `hello-world.log`. Entrada:

```tex
Hello, World!
\end
```

### Recuperando a entrada do arquivo de um arquivo zip

Outra opção é armazenar os arquivos de entrada em um arquivo zip e tratá -lo como um diretório de entrada. Nesse cenário, as seguintes etapas devem ser seguidas:

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputZipDirectory.py" >}}

`ASPOSE_TEX_INPUT_ZIP` indica um arquivo com `in/hello-world.tex` (padrão: `zip-in.zip`). Abra-o no modo binário `rb` e mantenha o fluxo aberto até o término do trabalho.

Para começar, criamos o fluxo que contém o arquivo zip. Posteriormente, após a criação das opções de conversão, atribuímos uma instância da classe [inputzipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) à propriedade [input_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/input_working_directory/). O segundo parâmetro do construtor representa o caminho base dentro do arquivo. Se desejarmos todo o arquivo para funcionar como diretório de entrada, devemos fornecer uma string vazia como argumento.

## A ideia por trás do terminal de entrada

Agora vamos considerar o conceito de entrada terminal. **Aspose.TeX for python** define a interface Geral [IInputTerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputterminal/) especificamente para esse fim, que inclui uma única propriedade que retorna uma instância da implementação [TerminalReader](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalreader/). As implementações disponíveis serão discutidas mais adiante.

### Obtendo a entrada terminal do console

Para conseguir isso, precisamos atribuir uma instância da classe [InputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputconsoleterminal/) à opção [Terminal_in](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_in/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.py" >}}

O exemplo lê uma linha com `\read` e a grava em `texput.xps`. Digite, por exemplo, `Terminal input works!` no terminal ou forneça a linha pela entrada padrão. `SCROLL_MODE` permite essa solicitação de entrada.
