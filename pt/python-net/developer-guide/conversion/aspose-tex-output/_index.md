---
translation: true
template: /templates/_template-python-net.md
title: Interface de saída do Aspose.TeX | Python
linktitle: Interface de saída do Aspose.TeX
weight: 16
url: /python-net/aspose-tex-output/
description: Aqui está uma explicação da funcionalidade de conversão da solução ASPPE.TEX API para Python, com Tex como o formato de saída, com exemplos de código.
lastmod: "2025-06-16"
---

{{<section overview>}}


> Para definições formais de implementação de E/S, consulte a [referência API](https://reference.aspose.com/tex/python-net/aspose.tex.io/) do **Aspose.TeX para Python**.

## A ideia por trás do diretório de saída

O Aspose.TeX define um diretório como um mapeamento entre nomes e volumes de dados, onde os maiores de dados podem ser arquivos, fluxos, matrizes ou outros tipos de dados. A API permite a especificação de diretórios de trabalho de entrada e saída separados. Para a saída, a API fornece a interface Geral [ioutputworkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/), que pode ser implementada pelo usuário para suas necessidades específicas. Além disso, a API fornece implementações prontas para uso, que serão discutidas abaixo. A interface *ioutputworkingDirectory* estende [iinputworkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/), pois o mecanismo pode primeiro criar e escrever um arquivo e depois leia -o de volta. A interface inclui o método [get_output_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputworkingdirectory/get_output_file/#str), que retorna o fluxo para gravar, em contraste com o método [get_file()](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/get_file/#str-bool), que retorna o fluxo para ler.

### Salvando a saída como um arquivo no sistema de arquivos de disco

Como mencionado [acima](/tex/{{lang.url-fragment}}net/latex-to-image/), o [output_working_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/output_working_directory/) é comumente definido como uma instância da classe [outputFilesystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputfilesystemdirectory/).

Aqui está como nós o definiríamos:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.py" >}}

Esse caso de uso específico é direto, portanto, não há necessidade de se aprofundar nele ainda mais.

### Salvando a saída como um arquivo de arquivo zip.

Outra opção é criar um arquivo ou fluxo e usá -lo como um arquivo zip para armazenar os arquivos de saída. Aqui está um exemplo:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.py" >}}

Para começar, criamos um fluxo de saída para o arquivo zip. Então, depois de criar as opções de conversão, definimos a opção *output_working_directory* para ser uma instância da classe [outputzipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputzipdirectory/).

## A ideia por trás do terminal de saída

A saída do terminal é outro aspecto importante da saída. Para isso, **Aspose.TeX para python** define a interface Geral [ioutputMerminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/ioutputterminal/), que possui uma única propriedade que retorna uma instância da implementação [TerminalWriter](https://reference.aspose.com/tex/python-net/aspose.tex.io/terminalwriter/). As implementações disponíveis serão discutidas abaixo.

### Escrevendo a saída do terminal no console

Para conseguir isso, precisamos definir a opção [terminal_out](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/terminal_out/) como uma instância da classe [outputConsoleterminal](https://reference.aspose.com/tex/python-net/aspose.tex.io/outputconsoleterminal/).

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.py" >}}

Mais uma vez, esse é o valor padrão da opção; portanto, não há necessidade real de especificá -lo. Portanto, esta seção é fornecida apenas para fins de demonstração.

### Escrevendo a saída do terminal em um arquivo

Em contraste com o terminal de entrada, **Aspose.TeX para Python** inclui uma implementação da interface*ioutputMerminal*que nos permite escrever a saída do terminal em um arquivo em um diretório de saída especificado.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.py" >}} 

Nesse caso, instruímos o mecanismo Tex a escrever a saída do terminal em um arquivo chamado [<Job_Name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .TRM, que estará localizado no mesmo diretório de saída do restante da saída. No entanto, isso não é obrigatório. Também podemos fornecer qualquer outra instância de uma implementação do *ioutputMerminal* ao construtor.