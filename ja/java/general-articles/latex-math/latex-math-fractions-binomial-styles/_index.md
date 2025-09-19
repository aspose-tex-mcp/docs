---
translation: true
template: /templates/_template-java.md
linktitle: 分数、二項係数、数学スタイル
title: 5。画分、二項係数、数学スタイル
weight: 50
url: /java/latex-math-fractions-binomial-styles/
keywords: ラテックス、ラテックス数学式、ラテックス数学、ラテックス数学分数、ラテックス数学の二項係数、ラテックス数学スタイル
description: 分数、二項係数などなど、そのような数学構造の植林、およびTexタイプセットの数学スタイルについて学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

数式に見られるもう1つの一般的なことは、分岐器のようなものが分母のようなものの上に配置されている分数やその他の構造です。後者の例は、二項係数です。

![分数のような数学オブジェクト](/tex/images/java/tutorial/latex-math-5-1.png)

これらの3つの式は、 `$$ 1 \ over2 $$`および `$$ n+1 \ over3 $$および$$ \ n+1 \ choice3 $$`を入力することで、表示された方程式として取得できます。

コマンド `\ over`は、式のすべてのものに適用されない限り、ブレースを備えた特定のサブフォーミュラに囲まれていない場合があります。

![分数](/tex/images/java/tutorial/latex-math-5-2.png)

同じサブフォーミュラで `\ over`を2回使用することはできません。つまり、` a \ over b \ over 2`を入力します。代わりに、何を介して何が得られるかを明示的に指定する必要があります。

![ネストされた分数](/tex/images/java/tutorial/latex-math-5-3.png)

両方の式はあまり見栄えが悪いようです。そのような場合、通常、分数を「スラッシュフォーム」に変換することが最善です。たとえば、最後の2つの式は次のように入力する必要があります。

![斬新な形の画分](/tex/images/java/tutorial/latex-math-5-4.png)

より複雑な例があります：

![斬新な形の画分](/tex/images/java/tutorial/latex-math-5-5.png)

上記の例を見ると、添え字や上付き文字にあるときに小さくなるように、分数に表示されるときに文字や他の記号が小さくなることがあることに気付いたかもしれません。テックスがシンボルのサイズを選択する方法について話しましょう。 Texには、式を処理できる8つのスタイルがあります。

* ディスプレイスタイル(自体で線に表示されるフォーミュラ用)
* テキストスタイル(テキストに埋め込まれた式用)
* スクリプトスタイル(上付き文字または添え字として使用されるサブフォーグラー用)
* ScriptScript スタイル（2 次上付き文字または下付き文字用）
そして、上付き文字と下付き文字があまり盛り上がらない点を除けばほぼ同じ 4 つの「Cramped」スタイル。これら 8 つのスタイルを *D*、*D'*、*T*、*T'*、*S*、*S'*、*SS*、*SS'* と呼びます。*D* は表示スタイル、*D'* は Cramped 表示スタイル、*T* はテキストスタイルなどです。TeX では、数式を入力する際に​​、テキストサイズ、Script サイズ、ScriptScript サイズの 3 つのサイズも使用します。

テキストを実行する式の式を整理するには、 `$ ... $`;に囲みます。これにより、スタイル *t *の式が生成されます。または、表示された式を取得するために `$$ ... $$`で囲むこともできます。これにより、スタイル *d *の式が表示されます。フォーミュラのサブフォーミュラは、異なるスタイルである場合があります。スタイルがわかったら、Texが使用するタイプのサイズを決定できます。

![サイズマッピングのスタイル](/tex/images/java/tutorial/latex-math-5-6.png)

このような小さなシンボルはScriptScriptのものよりも読みやすくなるため、「*sss*」スタイルはありません。

![フォーミュラスタイルに応じて、添え字とスーパーセクタップのスタイル](/tex/images/java/tutorial/latex-math-5-7.png)

For example, if `x^{a_b}` is to be typeset in style *D*, the `a_b` will be set in style *S*, and `b` in style *SS*; the result is ![任意の程度のルーツ](/tex/images/java/tutorial/latex-math-5-8.png)

スタイル *d*と *t*の違いはまだありません。それぞれの場合にはスクリプトサイズが使用されていますが、実際には指数の位置にわずかな違いがあります。しかし、画分の場合、スタイル *d*と *t*には大きな区別があります。

![分母のスタイルと分数スタイルに応じて分子](/tex/images/java/tutorial/latex-math-5-9.png)

したがって、 `$ 1 \ over2 $`(テキスト内)と入力すると、スタイル *s*s ' *を取得します。ただし、「$$ 1 \ over2 $$」と入力すると、表示されている式にスタイル *t* t ' *を入力します。

最後に、「\ underline」はスタイルを変えません。数学のアクセント、およびコマンド「\ sqrt」と `\ overline`は、cr屈なスタイルを保持しているcr屈なカウンターパートに非クラープのスタイルを変更します。
Texが独自のルールに従って選択するスタイルが気に入らないことがあります。 `\ displaystyle`または「\ textStyle」または `\ ScriptStyle`または` \ ScriptScriptStyle`を入力することにより、目的のスタイルを自由に指定できます。選択したスタイルは、式またはサブフォーミュラの終了まで、または別のスタイルを選択するまで適用されます。たとえば、 `$$ n+\ scriptStyle n+\ scriptscriptStyle n。$$`次の表示が得られます。

![マニュアルスタイルコントロール](/tex/images/java/tutorial/latex-math-5-10.png)

スタイルが変化するにつれてプラス記号も小さくなり、テックスがスクリプトスタイルにスペースを置かないことを示しています。

別の例、つまり継続的な分数を見てみましょう。

![継続的な分数](/tex/images/java/tutorial/latex-math-5-11.png)

入力して入手できます

```tex
$$a_0+{1\over\displaystyle a_1+
        {\strut 1\over\displaystyle a_2+
          {\strut 1\over\displaystyle a_3+
            {\strut 1\over a_4}}}}$$
```

この式に「\ strut」と `\ displaystyle`がなければ、結果は異なります。

![トリックを美しくすることなく、継続的な割合](/tex/images/java/tutorial/latex-math-5-12.png)

LaTexは、別の構文を使用して画分を指定できるマクロ `\ frac`を定義します：` \ frac {a} {b} `は` a \ over b`に相当し、 `\ frac12`は` 1 \ over2`に相当します。

Texには別の操作「\ atop」があります。これは、分数線を描画しないことを除いて「\ over」のようなものです。

![\ atopコマンド](/tex/images/java/tutorial/latex-math-5-13.png)

ラテックス形式は「\ choice」も定義します。これは「\ atop」のようなものですが、結果を括弧で囲んでいます。

![マクロを選択します](/tex/images/java/tutorial/latex-math-5-14.png)

「\ choice」と呼ばれます。なぜなら、それは * n *のものから * k *物を選択する方法がいくつあるかを示す二項係数の一般的な表記であるためです。

コマンド「\ over」、 `\ atop`、および` \ choice`は互いに混合できません。たとえば、 `$$ n \ over 2 $ $`を選択します `は違法です。グループ化を使用して、 `$$ {n \ choose k} \ over2 $$`または `$$ n \ seoce {k \ over2} $$`を取得する必要があります。

Texには、 `\ over`と` \ atop`の一般化バージョンである「上記のコマンド」があります。このコマンドでは、<dimen> `の上の\を入力することにより、行ルールの正確な厚さを指定します。例えば、 

```tex
$$\displaystyle{\frac{a}{b}\above1pt\displaystyle{\frac{c}{d}}$$
```

分子と分母の分数の間に1ptの厚いルールで複合分数を生成します。

![\above マクロ](/tex/images/java/tutorial/latex-math-5-15.png)