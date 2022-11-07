---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Funcionalidade de composição do TeX | API .NET
url: /net/typeset-tex-files/
description: "Solução de API .NET para trabalhar com TeX. Aprenda no exemplo como criar conjuntos de tipos TeX com algumas linhas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Formatar arquivos TeX
h2: "Digite um arquivo TeX usando um formato personalizado TeX C# .NET"
---

{{<section overview>}}
---
p1: "TeX é conhecido como uma das linguagens de marcação de dados e/ou uma linguagem de composição ao mesmo tempo. Isso significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos. Como saída, você obterá o arquivo formatado do formato necessário (especificado). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) é o núcleo central do sistema de conjunto de publicações (computação tipográfica)."
p2: "Para entender melhor a composição tipográfica do TeX, aprenda o [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação. E nesta página você encontrará trechos de código explicando como compor um arquivo TeX usando um formato TeX personalizado."
p3: "Para executar os exemplos, precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: Etapas para compor o TeX usando C#.
h3: "Código C# para escrever TeX"
item1: "Crie o provedor de formato usando a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Crie opções de conversão para um formato personalizado na extensão do mecanismo ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item3: "Especifique o diretório de trabalho de entrada se a entrada principal não for fornecida como um fluxo. Use a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para isso."
item4: "Especifique um diretório de trabalho do sistema de arquivos para a saída. Use a classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) para isso."
item5: "Execute o trabalho [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Refine a saída.
---