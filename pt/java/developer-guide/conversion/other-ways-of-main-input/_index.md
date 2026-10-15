---
translation: true
template: /templates/_template-java.md
title: Outras maneiras de fornecer o principal arquivo de entrada tex principal | Java
linktitle: Outras maneiras de fornecer o principal arquivo de entrada tex
weight: 14
url: /java/other-ways-of-main-input/
description: Funcionalidade de conversão do Aspose.TeX Solução da API para Java possui um construtor que aceita um fluxo como o primeiro argumento. Aqui estão alguns exemplos de código.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Fornecendo o arquivo de entrada principal para o mecanismo TEX como um fluxo

Até este ponto, sabíamos apenas como passar o [arquivo de entrada principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) para o mecanismo TEX como nome de arquivo, totalmente especificado ou de curta forma, seja com uma extensão ou sem ele. Mas há outro [construtor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) da classe `texjob`, que aceita um fluxo como o primeiro argumento. Isso é conveniente se, por algum motivo, tivermos o arquivo de entrada principal em um formulário que não seja um arquivo no sistema de arquivos de disco. Aqui está como podemos lidar com isso:

Defina `outputDirectory` como uma pasta de saída existente. Importe as classes Aspose.TeX usadas nos exemplos, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` e, para entrada por fluxo, `java.io.ByteArrayInputStream` e `java.nio.charset.StandardCharsets`. O método chamador deve tratar ou declarar as exceções. Aplique uma licença conforme o [guia de licenciamento](/tex/{{lang.url-fragment}}java/licensing/) para evitar as restrições de avaliação. O exemplo de fluxo contém um documento LaTeX completo e não precisa de um diretório de trabalho de entrada. Os fluxos e dispositivos permanecem abertos até o término do trabalho e depois são fechados ou liberados.

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

Quando a entrada por fluxo não tem um nome de trabalho atribuído explicitamente, o mecanismo usa o nome padrão *texput*. Este exemplo cria `texput.xps` e `texput.log`. Use `options.setJobName(...)` para escolher outro nome de trabalho. Consulte [aqui](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [aqui](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) para obter detalhes sobre os nomes de trabalho.

## Entrando no principal arquivo de entrada tex do terminal

Há ainda outro [construtor](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  da classe `texjob`, que não nos permite especificar a entrada. Então, o que é um trabalho tão tex que vai processar, você pode se perguntar? Desta vez, precisaremos de um terminal de entrada. O mecanismo TEX nos pedirá para inserir o nome do arquivo no terminal.

Defina `inputDirectory` como uma pasta que contenha um documento LaTeX completo chamado `hello-world.ltx`, e `outputDirectory` como uma pasta de saída existente. Execute o exemplo em um console, digite `hello-world.ltx` no prompt `**` e pressione Enter. Ele cria `hello-world.xps` e escreve a saída do terminal no console. Ambos os exemplos usam `NonstopMode` no processamento, mas o construtor do terminal ainda precisa do nome de arquivo inicial. Para execução sem intervenção, forneça uma implementação de `IInputTerminal` ou use entrada por arquivo ou fluxo.

Aqui está o código:

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

Assim que é executado, o motor gruda, esperando que insira o nome do arquivo (com ou sem um caminho, com ou sem uma extensão):


![Janela do terminal](/tex/images/java/Conversion-MainInputTerminal.png)

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