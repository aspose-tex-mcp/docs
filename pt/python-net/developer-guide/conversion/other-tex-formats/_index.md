---
translation: true
template: /templates/_template-python-net.md
title: Outros formatos de saída de conversão Tex | Python
linktitle: Outros formatos de Tex
weight: 18
url: /python-net/other-tex-formats/
description: A solução API Aspose.TeX para Python fornece funcionalidade que permite converter arquivos de LaTeX e arquivos tex personalizados. Aqui estão alguns exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}

É improvável que você precise converter um arquivo tex escrito em um formato que não seja o LATEX. No entanto, se você estiver estudando o idioma Tex ou os internos da TEX por qualquer motivo, ainda é possível. De qualquer forma, **Aspose.TeX for python** permite converter arquivos escritos no formato*PLAIN TEX*e também permite criar formatos personalizados e documentos digitados projetados nesses formatos.

Para começar, criaremos um formato personalizado.

## Criando um formato personalizado

Lembre -se de que o arquivo de formato é uma representação binária do estado interno do mecanismo Tex.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

Como você pode ver, o código tem uma semelhança com o código para converter um arquivo tex. No entanto, existem algumas distinções.

Em primeiro lugar, neste caso, utilizamos o trabalho [texconfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/). Essa configuração garante que o estado do mecanismo seja "virgem", o que significa que os parâmetros internos têm seus valores padrão e o conjunto de sequências de controle se alinha ao conjunto de primitivas. Em nosso exemplo, o conjunto de primitivas é expandido [no artigo Aspose.TeX e Object tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Depois disso, prosseguimos com a configuração dos diretórios de trabalho de entrada e saída, como de costume. O diretório de trabalho de entrada deve incluir o arquivo de origem do formato principal e todas as suas dependências.

E a segunda grande diferença é o método pelo qual executamos o trabalho. Nesse caso, utilizamos o método estático [create_format ()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions), que, em conjunto com as opções, requer o nome do arquivo de origem principal para ser idêntico ao nome do formato.

## Tipando um arquivo tex em seu formato personalizado

Agora que criamos nosso próprio formato TEX, podemos prosseguir para digitar um arquivo tex escrito neste formato. Aqui está o código:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

Para especificar o formato, precisamos criar uma instância da classe [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/). No construtor de opções, usamos a configuração [texconfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider), que requer nosso provedor de formato como argumento e carrega o formato na parte superior do estado "virgem" do motor.

O código restante deve ser familiar para você, pois utiliza os recursos discutidos anteriormente neste [guia](/tex/{{lang.url-fragment}}net/conversion/).

## Tipando um arquivo tex no formato PLAin Tex

Se removermos o provedor de formato do código mostrado acima, o motor carregará o formato padrão, que é [objeto tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) em seu quarto sentido. Portanto, se você tiver um arquivo tex escrito no formato Plear Tex, poderá convertê -lo em qualquer formato de destino suportado usando essa abordagem.