---
translation: true
template: /templates/_template-net.md
title: Reparo de arquivo de LaTeX | .NET
linktitle: Reparo de arquivo de LaTeX
weight: 30
url: /net/latex-repair/
description: Solução da API do Aspose.TeX para reparo de LaTeX .NET é descrito neste artigo. Aprenda os exemplos de código sobre como usar a funcionalidade.
lastmod: "2026-11-04"
---

{{<section overview>}}

## Como verificar e reparar um arquivo de LaTeX

Se você possui um arquivo de texto que acha que é um arquivo de LaTeX e deseja que ele seja digitado, mas não tem certeza se é realmente um arquivo de LaTeX (talvez você seja novo no mundo do LaTex), pode tentar usar o recurso de verificação e reparo de LaTeX fornecido pela API Aspose.TeX para .NET. No exemplo a seguir, verificaremos e repararemos um arquivo de amostra, `inválido-latex.tex`, do projeto Aspose.TeX for .Net Exemplo.

Primeiro de tudo, vale a pena mencionar que, embora o arquivo de amostra pareça usar a sintaxe Tex, ele não possui a estrutura exigida pelo LATEX. Como você deve saber, um arquivo de LaTeX deve ter um preâmbulo que começa com o comando `\documentclass` e um corpo dentro do ambiente` document ', ou seja, entre `\begin {document}` e `\end {document}`.

Agora vamos olhar para o exemplo de código C#.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_LaTeXRepairerExample" >}}

Assim como em um trabalho de TEX regular, primeiro criamos um objeto que contém as opções do processo que estamos prestes a executar. A maioria deles é a mesma que as opções de um trabalho regular de Tex. De fato, o [inputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) é o espaço do qual os arquivos de entrada devem ser lidos. Não o usamos aqui porque fornecemos o caminho completo para o arquivo de entrada principal no sistema de arquivos, e nenhum arquivo personalizado deve ser incluído no arquivo de entrada principal. Em seguida, [outputworkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) é o espaço onde os arquivos de saída devem ser gravados. [RequeriringInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), se atribuído, aponta para o espaço onde você pode armazenar pacotes de LaTeX que não estão incorporados na biblioteca Aspose.TeX. A propriedade [adivinhepackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) será discutida posteriormente.

Depois de atribuir as opções, simplesmente executamos o processo!

Então, como é o processo de verificação e reparo? Em primeiro lugar, a API pesquisa o arquivo de entrada para uma ocorrência `\documentclass`. Se falhar, pressupõe que `\documentclass {artigo}` deve ser inserido no início do arquivo. Esse fato é refletido no arquivo de relatório de reparo (`.log`).

Em seguida, ele começa a digitalizar o arquivo de entrada ajustado desde o início. O mecanismo TEX carregado com o formato do LATEX pode causar um erro em algum momento, sinalizando que nenhum `\ Begin {Document}` foi encontrado até agora, embora já deva ter ocorrido. Assim, a posição na qual `\begin {document}` deve ser inserida é definida e refletida no relatório.

À medida que o motor verifica o arquivo, ele pode encontrar comandos ou ambientes indefinidos. A API pode fazer suposições em [pacotes necessários incorporados](/tex/{{lang.url-fragment}}net/embedded-packages/) (aqueles que definem os comandos e ambientes que não são definidos até que esses pacotes estejam incluídos) para alguns dos comandos e ambientes mais comuns. No entanto, existe uma maneira de fazer essas suposições externamente, implementando a interface [iguesspackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/). Uma instância dessa classe deve ser atribuída à opção `adivinhepackageCallback`.

Aqui está um exemplo muito simples que apenas mapeia o comando `\lhead` para o pacote` FancyHdr`:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_PackageGuessingCallback" >}}

Quanto ao arquivo de amostra, o mecanismo encontra primeiro o comando `\ Capítulo`, que não está definido na classe de documentos`artigo`, mas é definido na classe de documentos `book`. A API ajusta a classe Document para que a versão final do arquivo fixo seja iniciado com `\documentclass {Book}`. Em seguida, o motor encontra o comando `\lhead` mencionado acima e decide que`\usepackage {FancyHdr} `deve ser inserido no preâmbulo. Os comandos `\href` e `\incluemGraphics` que ocorrem mais tarde para fazer o reparador inserir `\usepackage {hyperref}` e `\usepackage {gráficos}` no preâmbulo, respectivamente. Essas decisões são baseadas nos mapeamentos internos da API. Novamente, todas essas correções são registradas no arquivo de relatório.

Finalmente, o motor termina anormalmente, pois falta o final normal de um documento de LaTeX. Isso faz com que o reparador anexe `\end {document}`até o final do arquivo e reflita esse fato no relatório.

Depois que a versão fixa do arquivo original é construída, o reparador executa o trabalho Tex nele para a verificação final. Em nosso exemplo, essa execução não encontra erros críticos; portanto, a versão fixa pode ser digita mais ou menos conforme o esperado.

Aqui está o relatório completo:

```
A tentar reparar o ficheiro original...
--------------------------------------------------------------------------------
\documentclass está em falta no ficheiro original. Inserido no início.
\begin{document} está em falta no ficheiro original. Inserido na linha 3, pos. 0.
O comando \chapter na linha 3, pos. 0, é indefinido. Considere utilizar \usepackage{nome_do_pacote} no preâmbulo,
em que 'nome_do_pacote' é o nome do pacote que define este comando.
O comando \lhead na linha 5, pos. 0, é indefinido. \usepackage{fancyhdr} é inserido no preâmbulo
uma vez que o pacote 'fancyhdr' supostamente define o comando.
O comando \href na linha 8, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 17, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 20, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href da linha 27, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 32, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \includegraphics na linha 54, pos. 2, é indefinido. \usepackage{graphicx} é inserido no preâmbulo
uma vez que o pacote 'graphicx' supostamente define o comando.
O comando \href da linha 67, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 95, pos. 57, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 96, pos. 0, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
O comando \href na linha 98, pos. 100, é indefinido. \usepackage{hyperref} é inserido no preâmbulo
uma vez que o pacote 'hyperref' supostamente define o comando.
\end{document} está em falta no ficheiro original. Inserido no final.

A verificar o ficheiro reparado...
--------------------------------------------------------------------------------
Não existem erros críticos no ficheiro corrigido.
```

## Construir um Agente de IA para Reparação de Sintaxe LaTeX

Este fluxo de trabalho combina a validação estrutural da API de reparação nativa do Aspose.TeX com a inferência contextual de um núcleo LLM para alcançar um pipeline de renderização à prova de erros. Pode ser um Agente separado para verificar e corrigir erros em ficheiros LaTeX existentes ou parte do processo de escrita matemática.

### Arquitetura de workflow para um Agente de IA que repara a sintaxe LaTeX

![Esquema de blocos para o workflow de reparação de LaTeX com IA](/tex/images/net/tutorial/blockscheme-for-math-repairing.png)

1. Processamento sintático e extração de intenções (camada LLM)
O utilizador fornece instruções conversacionais, excertos de texto em bruto, fórmulas copiadas ou um ficheiro `.latex`. O Agente solicita ao LLM que extraia as intenções matemáticas principais e gera um bloco matemático LaTeX focado.

2. Correção automática da estrutura nativa (reparador Aspose.TeX)
O fragmento matemático gerado é encaminhado pelo ciclo de vida de reparação nativo do Aspose.TeX para construir limites estruturais padrão sem que os programadores tenham de escrever wrappers de expressões regulares codificados.

O agente salva o fragmento em um arquivo e executa `LaTeXRepairer` nele. O Repairer insere os `\documentclass`, `\begin{document}` e `\end{document}` ausentes e grava o arquivo corrigido (`-fixed.tex`) e o relatório (`.log`) no diretório de saída. Ele não muda para o modo matemático, portanto a fórmula já deve estar entre delimitadores matemáticos, como `$...$`.

3. Execução e geração de recursos/relatórios (mecanismo de renderização)
`LaTeXRepairer.Run()` retorna o resultado do arquivo original, portanto o agente lê a verificação do arquivo corrigido no relatório. Se não houver erros críticos, o agente cria um relatório ou converte o arquivo corrigido nos formatos visuais de destino executando um `TeXJob`.

**Você também pode conferir nosso aplicativo Web GRATUITO [** AI LATEX **](https://products.aspose.ai/tex/latex-repairer), que é construído com base no recurso implementado no [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/) e envolve uma implementação mais avançada da interface `iguesspackagecallback`.**
