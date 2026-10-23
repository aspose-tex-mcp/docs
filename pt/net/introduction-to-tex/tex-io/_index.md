---
translation: true
template: /templates/_template-net.md
title: Entrada/saída de TeX <span></span>
linktitle: Tex E/S.
weight: 12
url: /net/tex-io/
description: Fundamentos de trabalho com Tex como formato de saída ou entrada dentro da API Aspose.TeX. TEX Job é executado em um arquivo explicitamente especificado.
lastmod: 2026-10-20
---

{{<section overview>}}

## Arquivo tex

Tecnicamente, qualquer arquivo pode ser um arquivo tex. Nem precisa ter a extensão *.tex*. Um mecanismo TEX lê o byte de entrada por byte tentando reconhecer comandos conhecidos por ele (ou seja, aqueles que estão em seu estado interno). Ele simplesmente relata erros sobre comandos não reconhecidos e/ou solicita correções no terminal (se estiver em execução em um [modo interativo](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)). Mas se você espera ver algo como um documento bem -sucedido, a entrada deve seguir a sintaxe Tex e, idealmente, conter apenas comandos conhecidos pelo mecanismo.

## Entrada tex

Um trabalho de Tex é executado em um arquivo tex explicitamente especificado. Portanto, incluímos esse arquivo na entrada de um determinado trabalho de Tex. Além disso, o TEX possui quatro primitivas relacionadas à entrada auxiliar:

* `\input <nome do arquivo>` requer um nome de arquivo e inicia o processamento desse arquivo assim que o processamento do arquivo contendo atingir o comando `\input`. Quando o final do arquivo auxiliar é atingido, o processamento retorna ao arquivo que contém o comando `\input`.
* `\openin <4 bit-number> = <nome do arquivo>` Também requer um nome de arquivo, mas apenas abre um arquivo e o mapeia para um número de 0 a 15.
* `\leia <número> para <sequência de controle>` requer o número para o qual um arquivo é mapeado e lê uma linha dele por vez, para que `<Sequência de controle>` corresponda à lista de tokens lidos.
* `\Closein <4 bit-number>` fecha o arquivo mapeado para o número.

Os arquivos cujos nomes são passados ​​para os comandos `\input` e `\openin` também estão incluídos na entrada Tex, e nós os chamaremos de *arquivos de entrada auxiliar* ou *dependências*, enquanto o arquivo especificado para o trabalho chamamos o arquivo *principal de entrada*.

Os quatro comandos podem ocorrer no arquivo de entrada principal ou em um arquivo de entrada auxiliar. Mas cuidado com as dependências circulares.

Ao executar em um [modo interativo](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), em caso de qualquer erro, o mecanismo TEX solicita uma correção no terminal. Neste ponto, convém substituir o comando errôneo por um novo. E isso será outra e a última maneira de fornecer informações para a TEX, que chamaremos de entrada *do terminal*.

## Saída Tex

Como mencionamos [acima](/tex/{{lang.url-fragment}}net/tex-io/#tex-input), um trabalho de Tex é executado em um arquivo explicitamente especificado. O arquivo não pode conter nenhum dados para o TypeT. Pode haver apenas sequências de controle que não produzem caracteres para digitar. Mas normalmente ele conterá esses dados, para que obtenhamos um arquivo no formato de destino que deve conter nosso texto com o tipógrafo (ou qualquer outra coisa permitida pelo mecanismo e pelo formato, se forem estendidos para ajustar recursos extras de um determinado formato de destino). O arquivo terá o mesmo nome que o arquivo especificado como a entrada. Chamaremos esse arquivo do arquivo *principal de saída*. Como mencionamos [acima](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex), para o Tex original, este será um arquivo no formato DVI. Chamaremos o nome dos arquivos de entrada e saída sem extensão do *nome da tarefa*.

Além disso, o TEX possui três primitivas relacionadas à saída auxiliar:

* `\openout <4 bit-number> = <nome do arquivo>` requer um nome de arquivo, abre um arquivo e o mapeia para um número de 0 a 15.
* `\write <número> {Lista de token}` requer o número para o qual um arquivo é mapeado e grava a `Lista de token 'no arquivo.
* `\Closeout <4 bit-number>` fecha o arquivo mapeado para o número.
 
Os arquivos cujos nomes são passados ​​para os comandos `\openout` também estão incluídos na saída TEX, e nós os chamaremos de  arquivos de saída auxiliar*.

À medida que o mecanismo TEX executa pela entrada, ele pode produzir algumas informações de depuração para o arquivo *log* ou *trascript*. Incluiremos esse arquivo na saída TEX.

Simultaneamente com a gravação no arquivo de log, o mecanismo TEX pode gerar informações menos detalhadas para o terminal. E esta é a última maneira que o mecanismo Tex grava a saída que chamaremos de saída *do terminal*.

## Modos de interação Tex

Um trabalho de Tex pode estar em execução em um dos quatro modos de interação a qualquer momento. Esses modos são alterados pelas seguintes primitivas TEX:

* `\batchmode`. O motor omite todas as paradas e omite a saída do terminal e, portanto, não requer o terminal para entrada ou saída.
* `\nonstopmode`. O motor omite todas as paradas e, portanto, requer o terminal apenas para saída.
* `\scrollmode`. O motor omite o erro para e requer o terminal para entrada e saída.
* `\errorstopmode`. O motor para em todas as oportunidades para interagir.

O Aspose.TeX nos permite especificar o modo de interação como uma opção de emprego TEX quando seu objeto está sendo criado. Esse modo será definido no estado interno do mecanismo imediatamente após o carregamento do formato Tex (se algum formato for carregado) e será alterado para outro modo assim que o mecanismo encontrar um dos quatro comandos. O valor padrão desta opção preservará o modo de interação definido pelo formato Tex. Quando nenhum formato é carregado, o modo de interação é o mesmo definido pelo comando `\errorstopmode`.

## O papel da abstracção de interfaces (`IInputWorkingDirectory` e `IOutputWorkingDirectory`)

Os motores TeX tradicionais estão inerentemente acoplados ao sistema de ficheiros do sistema operativo local, tratando os ficheiros como caminhos absolutos ou relativos no disco. O Aspose.TeX rompe com esta limitação legada introduzindo uma camada de abstração robusta construída em torno de duas interfaces principais: `IInputWorkingDirectory` e `IOutputWorkingDirectory`. Este desacoplamento permite:

- Processar documentos inteiramente em memória utilizando armazenamento baseado em fluxo.

- Lidar diretamente com ficheiros comprimidos, lendo dos fluxos ZIP sem os extrair primeiro para o disco.

- Garantir a segurança de threads em aplicações de servidor multi-tenant, isolando cada tarefa de composição tipográfica na sua própria instância de diretório de trabalho virtual.

- ### Porque é que a abstração de interfaces é importante para os desenvolvedores

Nas aplicações empresariais modernas — como microsserviços na nuvem ou filas de tarefas em segundo plano — depender de caminhos físicos em disco apresenta estrangulamentos severos:

- Vários threads a ler ou escrever no mesmo directório físico irão colidir ou sobrescrever os ficheiros temporários `. aux`, `. log` ou de saída uns dos outros.

- Escrever recursos intermédios ou strings dinâmicas de base de dados em disco apenas para que um mecanismo de composição tipográfica os leia degrada o desempenho.

- Os ambientes na nuvem (como contentores Docker ou funções sem servidor) possuem frequentemente sistemas de ficheiros de leitura apenas ou acesso restrito ao armazenamento.

Ao abstrair a entrada e a saída através de interfaces, o Aspose.TeX permite aos programadores redirecionar as operações de ficheiros para fluxos de memória, ficheiros ZIP, bases de dados ou sistemas de ficheiros virtuais personalizados sem qualquer alteração na lógica principal de composição tipográfica.