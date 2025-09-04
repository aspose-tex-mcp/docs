---
translation: true
template: /templates/_template-java.md
title: Reparo de arquivo de LaTeX | Aspose.TeX para java
linktitle: Reparo de arquivo de LaTeX
weight: 30
url: /java/latex-repair/
description: O recurso de reparador de arquivos de LaTeX dentro da API Aspose.TeX para Java é descrito neste artigo. Aprenda os exemplos de código de como usar a funcionalidade.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Como verificar e reparar um arquivo de LaTeX

Se você não tiver certeza se um arquivo de texto é um arquivo de LaTeX e deseja que ele seja digitado, pode utilizar o recurso de verificação e reparo do LaTeX oferecido pela API Aspose.TeX para Java. No exemplo abaixo, verificaremos e repararemos um arquivo de amostra, `inválido-latex.tex`, do projeto Aspose.TeX for java.

Para começar, é importante observar que o arquivo de amostra parece empregar a sintaxe Tex, mas carece da estrutura exigida pelo LaTeX. Como você deve saber, um arquivo de LaTeX deve incluir um preâmbulo que começa com o comando \ documentClass, bem como um corpo envolto no ambiente do documento, especificamente entre \ begin {document} e \ end {document}.

Agora vamos olhar para a amostra de código Java.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Semelhante a um trabalho de TEX regular, começamos criando um objeto que mantém as opções para o processo que estamos prestes a executar. A maioria dessas opções é a mesma que as de um emprego de Tex regular. De fato, chamando o método [setInputWorkingDirectory ()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), especificamos o espaço do qual os arquivos de entrada devem ser lidos. No entanto, neste exemplo, não o usamos aqui porque fornecemos o caminho completo para o arquivo de entrada principal no sistema de arquivos, e nenhum arquivo personalizado deve ser incluído no arquivo de entrada principal. Em seguida, chamamos o método [setOutputWorkingDirectory ()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) para especificar o espaço onde os arquivos de saída devem ser gravados. Se chamado, o método [setRequiredInputDirectory ()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) faz as opções apontam para o espaço onde você pode armazenar pacotes de LaTeX que não estão incorporados na biblioteca Aspose.TeX. Finalmente, o método [setGuessPackageCallback ()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) será discutido posteriormente.

Depois que as opções forem atribuídas, podemos prosseguir com a execução do processo.

Então, como é o processo de verificação e reparo? Começa com a pesquisa de API por uma ocorrência `\documentclass` no arquivo de entrada. Se não for encontrado, a API assume que `\documentclass {Article}` deve ser inserida no início do arquivo. Esta informação é registrada no arquivo de relatório de reparo (.log).

Em seguida, o processo começa a digitalizar o arquivo de entrada ajustado desde o início. O mecanismo TEX equipado com o formato do LATEX pode, em algum momento, lançar um erro indicando que `\ Begin {Document}`ainda não foi encontrado quando deveria já ter. Dessa forma, a posição na qual `\begin {document}` deve ser inserida é definida e refletida no relatório.

Ao digitalizar ainda mais o arquivo, o mecanismo pode encontrar comandos ou ambientes indefinidos. Nesses casos, a API pode fazer suposições em [Pacotes necessários incorporados](/tex/{{lang.url-fragment}}net/embedded-packages/) (aqueles que definem os comandos e ambientes que não são definidos até que esses pacotes estejam incluídos) para alguns dos comandos e ambientes mais comuns. No entanto, é possível fazer essas suposições externamente por uma classe que implementa a interface [iguesspackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). Depois de desenvolver essa classe, uma instância deve ser passada para o processo chamando o método `setGuessPackageCallback ()`.

Aqui está um exemplo básico que simplesmente mapeia o comando `\head` para o pacote` FancyHdr`:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

Quanto ao ficheiro de exemplo, o mecanismo encontra primeiro o comando `\chapter`, que não está definido na classe de documento `article`, mas sim na classe de documento `book`. A API ajusta a classe de documento para que a versão final do ficheiro reparado comece por `\documentclass{book}`. De seguida, o motor encontra o comando `\lhead` mencionado anteriormente e determina que `\usepackage{fancyhdr}` deve ser introduzido no preâmbulo. Os comandos `\href` e `\includegraphics`, que ocorrem posteriormente no ficheiro, fazem com que o Reparador introduza `\usepackage{hyperref}` e `\usepackage{graphics}` no preâmbulo, respetivamente. Estas decisões são tomadas com base nos mapeamentos internos da API. Como antes, todos estes reparos são registados no ficheiro de relatório.

Finalmente, o motor termina anormalmente porque a conclusão adequada de um documento de LaTeX está faltando. Como resultado, o reparador anexa `\end {document}`ao final do arquivo e inclui essas informações no relatório.

Depois de criar a versão fixa do arquivo original, o reparador executa um trabalho de Tex nele para a verificação final. Em nosso exemplo, essa execução não detecta erros críticos; portanto, a versão fixa pode ser digita mais ou menos conforme o esperado.

Aqui está o relatório completo:


2,545 / 5,000
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

**Você também pode conferir nosso aplicativo Web GRATUITO [** AI LATEX **](https://products.aspose.ai/tex/latex-repairer), que é construído com base no recurso implementado no [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/) e envolve uma implementação mais avançada da interface `iguesspackagecallback`.**