---
translation: true
template: /templates/_template-java.md
linktitle: Equação de LaTeX alinhe e exibir
title: 2. Exibição e alinhamento para equações de LaTeX
weight: 10
url: /java/latex-structures-for-equations/
keywords: AMS-LATEX, AMSMATH, AMSMATH OPÇÕES, Alinhamento da equação de LaTeX, LEQNO, EQNO, FLEQN, etiqueta de equação de LaTeX, etiqueta de equação de LaTeX, equações de alinhamento de LaTeX
description: Esta é uma introdução nas equações de LaTeX de digitação com pacotes AMS-Latex e fornece alguns exemplos e suas explicações. LATEX ALINEM EQUIÇÕES.
lastmod: "2025-06-16"
---

{{<section overview>}}


O pacote *amsmath* contém uma série de definições de ambientes para digitar fórmulas de matemática exibidas. Eles podem ser classificados pelo número de linhas de materiais (únicas ou múltiplas) e pelo número de pontos de alinhamento.

> Nesta secção, utilizaremos o termo *equação* da seguinte forma: para nos referirmos a uma parte *lógica* distinta de uma apresentação matemática, que é geralmente numerada para referência e também rotulada (por exemplo, pelo seu número entre parênteses). Estes rótulos também são chamados de *tags*.

A lista a seguir contém os ambientes de exibição mais populares. Quando apropriado, eles estrelaram formas nas quais não há marcação das equações.

||
| --- | --- | --- |
| `equação` | `equação*` | Uma linha, uma equação |
| `multline` | `multline*` | Uma equação de linha múltipla não alinhada, um número da equação |
| `Gather` | `Gather` | Várias equações sem alinhamento |
| `align` | `alinhe*` | Várias equações com múltiplos alinhamentos |
| `flalign` | `flalign*` | Várias equações: Spreads em horizontalmente se espalham de `alinhamento '|
| `split` | | Um alinhamento simples dentro de uma equação de múltiplas linhas |

Todos os exemplos deste capítulo são digitados com o material matemático centrado e os números de equações (tags) à direita. Para visualizar o posicionamento, apresentamos linhas verticais azuis na saída que representam as margens esquerda e direita, bem como a linha central. No código-fonte do LATEX, usamos o `% -----...` Comente para separar linhas que devem ser colocadas no preâmbulo do documento daquelas que devem ser colocadas no corpo.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![Leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

Se você deseja posicionar a matemática em um recuo fixo da margem esquerda, em vez de centralizado na coluna de texto, a opção `fleqn` estará disponível. Você pode especificar o tamanho do recuo no preâmbulo, definindo o valor do comprimento da borracha `\mathindent`. Seu valor padrão é o mesmo que o recuo de uma lista de primeiro nível. Se você estiver contente com esse valor, poderá pular a configuração do comprimento `\mathindent`.


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![Fleqn, Reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

Não há necessidade de passar na opção `reqno`aqui (como é o padrão), mas substitui as configurações da classe de documentos, para que o número da equação seja forçado à direita, o que quer que aconteça.

No LATEX padrão, `&` e `\\` são usados ​​para separação de coluna e linha dentro de alinhamentos exibidos. Os detalhes de sua mudança de uso nos ambientes `amsmath`.

## 2.1. Comparação com LaTeX padrão

Alguns dos ambientes de exibição de várias linhas permitem alinhar partes da fórmula. Comparado aos ambientes de LaTeX padrão `eqnarray` e` eqNarray*`, as estruturas definidas no pacote`amsmath` fornecem uma maneira ligeiramente diferente e mais simples de marcar os pontos de alinhamento. No LATEX padrão, `eqNarray*` é semelhante a um ambiente `Array` com` {rcl} `como o preâmbulo, o que significa que dois chars são necessários para indicar os dois pontos de alinhamento. No pacote `amsmath`, as estruturas equivalentes têm apenas um único ponto de alinhamento (como se`array` tivesse um `{rl}` preâmbulo), então você precisava colocar apenas um `&` `` char à esquerda do símbolo (geralmente uma relação) que deve ser alinhada.

O ambiente `eqNarray` produz espaço extra nos pontos de alinhamento, dependendo das configurações de parâmetros para`Array`. As estruturas `amsmath`, ao mesmo tempo, dão espaçamento fixo. A diferença é claramente ilustrada pelo próximo exemplo. A mesma equação é digitada usando os ambientes `equação`, `align` e `eqNarray`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![Amsmath comparado ao LaTeX padrão](/tex/images/java/tutorial/latex-ams-math-2-3.png)

Observe que os espaços no ambiente `eqNarray` são amplos demais para os padrões convencionais de composição matemática.
Como no LATEX padrão, as linhas em uma tela `amsmath` são marcadas com `\\ `(ou o fim do ambiente). Como a quebra de linha em uma exibição matemática geralmente requer uma compreensão profunda da estrutura da fórmula, ela é comumente considerada além dos recursos de software de hoje.

## 2.2. Uma única equação em uma linha

Uma única equação pode ser produzida pelo ambiente 'Equação'. Uma tag é gerada e colocada automaticamente na extrema esquerda ou direita de acordo com a opção em uso. O ambiente `equação*` produz a mesma equação sem uma tag. O LATEX padrão também possui `equação`, mas não` equação*`, pois o último é semelhante ao ambiente matemático exibido padrão.

Um fato notável é que a presença da tag não afeta o posicionamento do conteúdo. A tag será deslocada para cima ou para baixo, caso não haja espaço suficiente para ela em uma linha: para a linha anterior quando as tags de equação estão à esquerda e para a próxima linha quando as tags estiverem à direita.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![Uma única equação em uma linha](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. Uma única equação em várias linhas sem alinhamento

Uma variação do ambiente `Equação` é o ambiente` multline`. É usado apenas para equações que não se encaixam em uma única linha. O char `\` deve ser usado para marcar as quebras da linha, pois elas não são encontradas automaticamente.

A primeira linha do `MultLine` será alinhada em um recuo da margem esquerda e a última no mesmo recuo da margem direita. O valor do comprimento `\multlineGap` define o tamanho desse indentação.

Cada linha que não a primeira e a última é centrada individualmente dentro da largura da exibição (a menos que a opção `fleqn` seja usada). No entanto, se você adicionar o comando `\shoveleft` ou `\shoveright` dentro de uma linha, essa linha será forçada para a esquerda ou para a direita.

Um ambiente `multline` possui uma única tag, pois logicamente é uma única equação. Portanto, nenhuma das linhas individuais pode ser alterada pelo uso de `\tag` ou`\notag`. A tag, se presente, é colocada descarrega direita/esquerda na última/primeira linha quando a opção `reqno`/` leqno` for usada.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![Uma única equação em várias linhas](/tex/images/java/tutorial/latex-ams-math-2-5.png)

O próximo exemplo mostra como `\multlineGap`afeta o resultado. No primeiro caso, a formação "*dy*", que parece uma tag está faltando na primeira linha da equação. Quando `\multlineGap` está definido como `0`, o espaço à esquerda da segunda linha não muda devido à tag, enquanto a primeira linha é deslocada para a margem esquerda, deixando claro que essa é uma única equação.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![O efeito \ multlineGAP](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. Uma única equação em várias linhas com alinhamento

Quando você precisa alinhar uma única equação multilina, o ambiente `Split` está ao seu serviço. Basta usar um único `&` char em cada linha para marcar os pontos de alinhamento.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![Uma única equação com alinhamento simples](/tex/images/java/tutorial/latex-ams-math-2-7.png)

Um `split` não cria uma tag de equação (portanto, a variante estrelada não é necessária), porque é sempre usada como o conteúdo de uma única equação. Para esse fim, você pode colocá -lo em um ambiente externo.

Por padrão, a tag (assim como qualquer parte da equação fora do `split`) está centrada verticalmente na altura total do material de ambiente` split`. Esse comportamento corresponde à opção `Centertags`. Quando você especifica a opção `TBTAGS`, a tag é colocada na última linha do `split` quando a tag está à direita e na primeira linha quando a tag estiver à esquerda.


```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![Uma única equação com alinhamento simples e a tag na última linha](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. Grupos de equações sem alinhamento

Quando você precisa colocar duas ou mais equações em uma única exibição sem alinhamento entre as equações, você pode usar o ambiente `coleta`. Ele também centraliza separadamente cada equação dentro da largura da exibição e equipa com uma tag individual, se necessário. Cada linha de um `coletor` é logicamente uma equação única.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Grupo de equações sem alinhamento](/tex/images/java/tutorial/latex-ams-math-2-9.png)

Pode ser necessário suprimir o número da equação para uma determinada linha. O comando `\notag`, colocado na linha lógica, é a resposta. O ambiente `Gather` não identifica as equações.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Grupo de equações com tags omitidas](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. Grupos de equações com alinhamento simples

Quando você precisa digitar mais de uma equação em uma única exibição e alinhá -los verticalmente, o ambiente `alinhado` vem em socorro. No caso mais simples, você usa um único `&` em cada linha para marcar o ponto de alinhamento.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![Grupos de equações com alinhamento simples](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. Múltiplos alinhamentos

Um ambiente `alinhado` pode definir vários pontos de alinhamento. O layout contém tantos pares de colunas forem necessários e é semelhante a uma `array` com o preâmbulo` {rlrl ...} `semelhante a. Supondo que consista em pares de colunas *n*tais `rl`, o número de` & `'por linha será *2n-1 *: um para alinhamento dentro de cada par de colunas doando *n*; e * n - 1 * `&` 'para separar os pares de colunas.

O ambiente `ALIGN` espalha o material uniformemente pela largura da tela. Se houver espaço extra, ele será distribuído igualmente entre pares de colunas adjacentes e as duas margens de exibição.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![Múltiplos alinhamentos](/tex/images/java/tutorial/latex-ams-math-2-12.png)

O layout do `Flalign` é semelhante, mas não há espaço nas margens. No próximo exemplo, você pode ver que a equação (3) se encaixa em uma única linha devido a esse fato (enquanto a equação (2) ainda não o faz).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![flalign](/tex/images/java/tutorial/latex-ams-math-2-13.png)

Nos dois casos, o espaço mínimo entre os pares de colunas pode ser definido alterando `\minalignsep`. O valor padrão é `10pt` e pode ser alterado com `\renewCommand`, pois é um comando macro em vez de um parâmetro de comprimento. O próximo exemplo demonstra o efeito de alterar `\minalignsep`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![\ Minalignsep Efeito](/tex/images/java/tutorial/latex-ams-math-2-14.png)

O próximo exemplo ilustra um uso muito comum para `alinhamento`. Observe o uso de `\text` para produzir texto normal dentro do material matemático.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![O uso de \ texto](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. Displays de interrupção: `\Intertext`

Você pode colocar um pequeno pedaço de texto entre as linhas de um alinhamento de exibição. Isso é feito com o comando `\Intertext`. É muito importante que todas as propriedades de alinhamento permaneçam não afetadas pelo texto, enquanto o próprio texto é composto como um parágrafo normal definido para a largura da exibição. O alinhamento não funcionará se você apenas terminar a tela e iniciar um novo após o texto. Este comando deve sempre seguir imediatamente um comando `\\` ou `\\*` `.


``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![O comando \intertext](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> The words "and finally" are outside the alignment, at the left margin, but all three equations are aligned.

## 2.9. Numeração de equações e tags

No LATEX, as tags para equações são normalmente geradas automaticamente e são essencialmente uma representação impressa da "equação" do contador de LaTeX. Isso é feito pelo LATEX em três etapas: definindo o valor do contador `equação`; formatando a tag; e imprimi -lo na posição correta.

As duas primeiras etapas estão intimamente vinculadas, porque o valor do contador `equação` é aumentado apenas quando a tag correspondente é impressa automaticamente. Vamos dar uma olhada em um ambiente de exibição que estrelou e as formas não se Wharred. Somente o formulário não marcado altera o valor do contador de `equação`, pois ele marca automaticamente cada equação lógica enquanto o formulário estrelado não.

Quando você precisa suprimir a configuração de uma tag para uma certa equação lógica dentro do formulário não setrado, você coloca `\notaG` (ou`\não tumber`) *antes* do `\\`. Você também pode substituir as tags padrão por suas próprias design usando o comando `\tag` *antes* do` \\ `. O argumento deste comando pode ser um texto normal arbitrário, com os parênteses, como a tag para essa equação.
Observe que o incremento do valor do contador também é suprimido quando `\tag` é usado. Isso significa que a configuração de tag padrão é visualmente a mesma que `\tag {\ theEquation}`; Eles não são equivalentes. O formulário estrelado, `\tag*`, digita o texto em seu argumento sem os parênteses (e sem nenhuma outra coisa que de outra forma possa ser adicionada com uma classe de documento específica).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\ tag, \ tag*, \ nãog, \ Label e \ ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Note como os comandos `\label` e `\ref` são utilizados para fornecer algum tipo de "numeração relativa" para as equações.

## 2.10. Sequências de numeração subordinada

O pacote * AMSMATH * também suporta a chamada "Sub-Número de Equação". O ambiente de `Subequações` produz tags da forma (2a), (2b), (2c) e assim por diante. Esse esquema de numeração é baseado em dois contadores normais de LaTeX: `ParentEquation` e `equação`. Todas as equações marcadas em um ambiente de `subamques` usam esse esquema.

O exemplo a seguir mostra que a tag pode ser redefinida até certo ponto, mas observe que a redefinição para `\theEquation` deve ser colocada no ambiente de `subequações`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}

\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![Sequências de numeração subordinada](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> O ambiente `subequations` deve aparecer *fora* dos ecrãs que afecta. Ele também não deve estar aninhado dentro de si mesmo. O contador de equações "principal" é incrementado a cada utilização deste ambiente. Um comando `\label` dentro do ambiente `subequations`, mas fora de qualquer equação individual (lógica), produzirá um `\ref` para o número pai (por exemplo, para 2 em vez de 2i).

## 2.11. Redefinindo o contador de equações

É prática comum ter equações numeradas dentro de seções ou capítulos com tags do formulário (1.1), (1.2), ..., (2.1), (2.2), .... O pacote `amsmath` fornece uma maneira fácil de configurar isso com a declaração`\numberWithin`.

Por exemplo, para obter tags de equação, incluindo o número da seção, com o contador de equações sendo redefinido automaticamente para cada seção, coloque essa declaração no preâmbulo: `\numberWithin {equação} {seção}`.

## Apêndice A. Renderizando equações de LaTeX com API Aspose.TeX

Agora, veremos a maneira como a API Aspose.TeX permite obter equações de LaTeX como figuras independentes.

Digamos que você precise obter uma equação como uma imagem raster para que você possa usá-la em alguma publicação não-TEX (uma página da web, por exemplo). Usando a API Aspose.TeX, você pode fazê -lo da seguinte forma:


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

Como você pode ver, a API também é capaz de converter uma equação de LaTeX em um arquivo SVG. E esse foi um exemplo de uso do Aspose.TeX para .Net. Abaixo está o código equivalente para a versão Java.


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.aspose.tex.PngMathRendererOptions options = new com.aspose.tex.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.aspose.tex.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

Você pode encontrar detalhes sobre o uso de opções de renderizador no artigo sobre a renderização de fórmulas de matemática do LaTeX com [Aspose.TeX para .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) ou [Aspose.TeX para java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/). Mas um deles é importante para nós aqui. Usando esta opção, você pode especificar o preâmbulo do documento LATEX que precisaria obter o resultado desejado. (Daqui em diante, apresentaremos apenas a versão C# do código -fonte.)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

Você também pode usar esta opção quando precisar estabelecer uma equação em uma área mais estreita do que o LATEX `\textWidth` define por padrão. Você tem duas opções para atingir esse objetivo:


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Na API Aspose.TeX, o preâmbulo a seguir é usado por padrão; portanto, a menos que você precise passar opções para o pacote `amsmath` ou alterar o padrão `\textWidth` ou outra coisa, não há necessidade de especificar o preâmbulo nas opções do renderizador:


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Apêndice B. Renderizando equações de LaTeX com o aplicativo Web de equação de LaTeX Aspose

Há também o [App Web do Editor de Equações de Latex](https://products.aspose.app/tex/equation-editor) que permite editar e visualizar as equações do LATEX. Você pode inserir sua equação no campo de texto e clicar no botão * View * para ver o resultado. Ou você pode usar o painel de controle acima do campo para construir a equação selecionando uma categoria de subexpressão e subexpressão e editando o argumento, se houver. Você pode encontrar o preâmbulo e outras opções abaixo do campo *Fórmula*.