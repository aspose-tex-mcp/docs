---
translation: true
template: /templates/_template-python-net.md
title: Outras opções de gerenciamento de Tex | Python via .NET
linktitle: Outras opções
weight: 17
url: /python-net/other-options/
description: Solução da API do Aspose.Tex para Python Inclui funcionalidade de conversão que permite definir o modo de interação inicial no qual o motor inicia.
lastmod: "2025-06-16"
---

{{<section overview>}}

Os exemplos geram arquivos XPS. Aplique primeiro uma [licença](/tex/{{lang.url-fragment}}python-net/licensing/) e defina `ASPOSE_TEX_OUTPUT_DIR` como a pasta de saída (padrão: `output`). Use uma pasta diferente para cada exemplo para preservar todos os resultados.

## Definindo o modo de interação

Como mencionado [na interação Tex paraprófita](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX for python** fornece a capacidade de definir o modo de interação inicial no qual o motor inicia. Aqui está um exemplo de como isso pode ser feito:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-InteractionMode.py" >}}

## Definindo o nome do trabalho

Quando o arquivo de entrada principal é fornecido como um nome de arquivo, os arquivos de saída resultantes terão o mesmo nome, mas com extensões diferentes. O mecanismo TEX refere -se ao nome do arquivo de entrada como o nome *do trabalho* e o usa para os arquivos de saída. A exceção são arquivos auxiliares com nomes de arquivos explicitamente especificados. No entanto, quando o arquivo de entrada principal é passado como um [stream](/tex/{{lang.url-fragment}}python-net/other-ways-of-main-input/#supplying-the-main-input-file-as-a-stream), o mecanismo TEX usa o nome do trabalho padrão, que é *texput*. Nos dois cenários, substituindo o nome do trabalho atribuindo a opção de conversão apropriada é possível.

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-JobName.py" >}}

## "Tempo de parada"

Para gerar automaticamente um título a partir de certas definições no preâmbulo, o LATEX oferece um recurso que normalmente inclui a data atual. No entanto, pode haver casos em que queremos corrigir a data para um valor específico. Aqui está um método para conseguir isso:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-DateTime.py" >}}

## Ignorando pacotes ausentes

Se tivermos um arquivo de LaTeX que inclua referências a pacotes que não são suportados pela biblioteca **Aspose.TeX para Python**, o mecanismo Tex encontrará um erro e parará ao tentar carregar esses pacotes. Para evitar isso, podemos utilizar a seguinte opção:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-IgnoreMissingPackages.py" >}}

## Como evitar a construção de ligaduras

Por padrão, o Tex Engine constrói ligantes para pares de caracteres específicos se a fonte contiver os dados necessários. No entanto, podemos instruir o motor a ignorar a construção da ligadura usando o seguinte código:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-NoLigatures.py" >}}

## Repetindo o trabalho

Como mencionado [no parágrafo do arquivo de entrada do LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-input-file), rótulos e referências, há situações em que podemos precisar executar o mesmo trabalho duas vezes. Aqui está um método para realizar isso:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-Repeat.py" >}}

## Transformando fórmulas de matemática em imagens rasters

Se houver necessidade de converter fórmulas matemáticas em imagens rasters em vez de renderizá -las com fontes, a opção a seguir poderá ser usada para esse fim:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeFormulas.py" >}}

## Transformando gráficos em imagens rasters

O mecanismo ObjectTex fornece a capacidade de incluir arquivos gráficos em formatos de raster, como PNG e JPG, bem como formatos de PS (EPS) e XPS (OXPS). Os dois últimos formatos normalmente contêm elementos e texto vetoriais. Se quisermos rasterizar e incluí -los como imagens sólidas, podemos utilizar a seguinte opção:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RasterizeIncludedGraphics.py" >}}

O exemplo de gráficos lê `Typesetting/triangle.eps` em `ASPOSE_TEX_INPUT_DIR` (padrão: `input`). Preserve esse subdiretório ao preparar os recursos.

## Subconjunto de fontes
Se desejarmos diminuir o tamanho do arquivo de saída, podemos empregar subconjuntos de fontes, o que implica que as fontes no documento resultante não incluirão dados para os glifos que não estão presentes no documento. Aqui está uma solução para conseguir isso:

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-SubsetFonts.py" >}}