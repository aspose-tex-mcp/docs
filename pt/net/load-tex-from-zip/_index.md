---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Carregando TeX de ZIP | Solução de API .NET
url: /net/load-tex-from-zip/
description: "Solução de API .NET para trabalhar com TeX. Aprenda no exemplo como carregar um arquivo TeX de ZIP com algumas linhas de código C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Carregar arquivos de origem TeX de ZIP
h2: "Solução de API .NET para carregar arquivos TeX do arquivo ZIP"
---

{{<section overview>}}
---
p1: "O TeX é conhecido como uma linguagem de composição. Isso significa que você não formata seu texto no documento, mas insere o texto simples junto com os comandos. Como saída, você obterá o arquivo formatado do formato necessário (especificado). Para entender melhor a entrada e saída do TeX, aprenda o [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) da Documentação."
p2: "Como se sabe, o principal objetivo do TeX é ajudar a criar textos matemáticos ou técnicos. Mas antes de qualquer manipulação, o arquivo deve ser carregado primeiro. Aqui você encontrará trechos de código explicando como carregar arquivos fonte TeX de ZIP usando diretórios ZIP para entrada e saída, saída para dispositivo PDF, gravação de saída de terminal para console."
p3: "Para carregar arquivos .tex precisamos:"
p4: "Aspose.TeX for .NET API, que é uma API de conversão e manipulação de documentos rica em recursos, poderosa e fácil de usar para a plataforma C#."
p5: "Abra o gerenciador de pacotes NuGet, procure por Aspose.TeX e instale. Você também pode usar o seguinte comando do Console do Gerenciador de Pacotes."
---

{{<section feature1>}}
---
title: "Etapas para carregar o TeX de um arquivo ZIP C#:"
h3: "Código C# para carregar o TeX"
item1: "Abra o fluxo no arquivo ZIP para usá-lo como o diretório de trabalho de entrada."
item2: "Abra o fluxo no arquivo ZIP para usá-lo como o diretório de trabalho de saída."
item3: "Crie opções de conversão para o formato padrão do ObjectTeX na extensão do mecanismo ObjectTeX usando [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Método de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item4: "Especifique um diretório de trabalho do arquivo ZIP para a entrada ou/e especifique um caminho dentro do arquivo. Use construtores da classe [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) para isso."
item5: "Especifique um diretório de trabalho do arquivo ZIP para a saída ou/e especifique um caminho dentro do arquivo. Use construtores da classe [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) para isso."
item6: "Especifique o console como o terminal de saída usando a classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Defina as opções de salvamento usando a classe [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Execute o trabalho [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Método para [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Refine a saída.
---