---
translation: true
template: /_templates/_output-to-disk-net.md
title: Gravar a saída do TeX no disco | API .NET
url: /net/output-to-disk/
description: "Solução de API .NET para trabalhar com TeX. Aprenda no exemplo como criar uma saída personalizada para o arquivo TeX com algumas linhas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Gravar a saída do TeX no disco
h2: "Salve o resultado da conversão do arquivo TeX como disco via C# .NET"
---

{{<section overview>}}
---
p1: "O TeX é conhecido como uma linguagem de composição, o que significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos. Como é conhecido no artigo [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação, o trabalho TeX é executado em um arquivo TeX explicitamente especificado. Lá você também pode encontrar informações sobre os modos de interação do TeX e primitivas relacionadas à entrada e saída do TeX."
p2: "O principal uso do TeX é ajudar na criação de textos matemáticos ou técnicos. Mas quando o arquivo já está criado e você não deseja mais nenhuma manipulação, você pode querer convertê-lo para um formato diferente e mais popular."
p3: "Nesta página, você encontrará um exemplo de código explicando o uso de diretórios do sistema de arquivos para entrada e saída, saída para o dispositivo XPS, substituição do nome do trabalho, gravação da saída do terminal no disco. Em palavras simples, é uma conversão com a gravação da saída no disco. Para executar tal operação, precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: "Etapas para gravar a saída do terminal no disco C#:"
h3: "Código C# para converter TeX e gravar a saída no disco"
item1: "Crie opções de conversão na extensão do mecanismo ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Class."
item2: "Especifique um nome de trabalho se não quiser que o primeiro argumento do construtor TeXJob seja considerado como um nome de trabalho."
item3: "Especifique um diretório de trabalho do sistema de arquivos para a entrada. Use a classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) para isso."
item4: "Especifique um diretório de trabalho do sistema de arquivos para a saída com a ajuda das entidades da classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Especifique que a saída do terminal deve ser gravada em um arquivo no diretório de trabalho de saída."
item6: "Execute o trabalho [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---