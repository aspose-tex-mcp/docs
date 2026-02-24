---
translation: true
template: /templates/_template-java.md
linktitle: 区切り文字
title: 7. 区切り文字 | LaTeX マニュアル
weight: 70
url: /java/latex-math-delimiters/
keywords: latex、latex 数式、latex 数式、latex 数式区切り文字、latex 数式中括弧、latex 数式大括弧、latex 数式小括弧
description: この記事では、異なる種類の区切り文字を使って数式を論理的に分割する方法について説明します。
lastmod: "2026-02-24"
---

{{<section overview>}}

どれほど大きな数式であっても、TeX には記号を十分に大きくして見栄えよく表示する手段があります。たとえば次のように入力した結果

```tex
$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$
```

は、利用可能なさまざまな根号（平方根）記号を示しています。

![Radicals of different sizes](/tex/images/java/tutorial/latex-math-7-1.png)

ここで一番大きい 3 つの記号は同一で、必要なサイズになるまで垂直部分が繰り返し描かれています。一方、より小さな記号は TeX の数式フォントから取られた別個の文字です。

括弧やいわゆる「区切り記号」も同様です。区切り記号は数学において重要で、複雑な式の構造を視覚的に示す手がかりを与えてくれます。言い換えれば、個々の部分式の境界を限定する役割を果たします。以下は LaTeX が提供する 22 個の基本区切り記号です。

![The 22 basic delimiters defined in LaTeX](/tex/images/java/tutorial/latex-math-7-2.png)

これらの記号をほんの少し大きくしたい場合は、開く区切りには `\bigl`、閉じる区切りには `\bigr` と入力すれば OK です。これにより、入れ子になった区切りを含む式が読みやすくなります。

![The examples of using \big delimiters](/tex/images/java/tutorial/latex-math-7-3.png)

`\big` 区切りは普通のものより少しだけ大きく、差が分かりやすい程度でありながら、段落中の本文に使用できるだけの大きさです。

![The \big delimiters compared to the normal ones](/tex/images/java/tutorial/latex-math-7-4.png)

さらに大きな記号が必要なときは、`\bigl` と `\bigr` の代わりに `\Bigl` と `\Bigr` を使います。

![The \Big delimiters](/tex/images/java/tutorial/latex-math-7-5.png)

これらは前段階の 1.5 倍の高さです。ディスプレイ数式では、`\big` の 2 倍の大きさの区切りがしばしば使われますが、`\biggl` と `\biggr` を入力すれば取得できます。

![The \bigg delimiters](/tex/images/java/tutorial/latex-math-7-6.png)

最後に、`\Biggl` と `\Biggr` を使うと、`\bigl` と `\bigr` の 2.5 倍の高さになります。

![The \Bigg delimiters](/tex/images/java/tutorial/latex-math-7-7.png)

LaTeX には、数式の途中で使用できる `\bigm`, `\Bigm`, `\biggm`, `\Biggm` といったコマンドも用意されています。これらの区切りは関係記号のように振る舞うため、TeX はその両側に少量の空白を自動的に入れます。

![Delimiters in the middle of formulas](/tex/images/java/tutorial/latex-math-7-8.png)

また、`\big`, `\Big`, `\bigg`, `\Bigg` だけを単独で使って、普通の変数と同様に振る舞う区切りを作ることも可能です。このようなコマンドは主にスラッシュやバックスラッシュと組み合わせて使用されます。

![Big ordinary symbols](/tex/images/java/tutorial/latex-math-7-9.png)

TeX には、与えられた部分式を囲むのに必要な区切りの高さを自動的に計算するアルゴリズムが実装されています。自分で `\big` か `\bigg` かを決める代わりに、次のように書くだけで済みます。

```tex
\left<delim1><subformula>\right<delim2>
```

TeX はこの記述に基づき、左側と右側に指定した区切りを付けて部分式を組版し、区切りのサイズは部分式をちょうど覆うだけの大きさになります。

![Delimiters set by \left and \right commands](/tex/images/java/tutorial/latex-math-7-10.png)

`\left` と `\right` を使う場合は、必ずペアで出現させなければなりません。中括弧がグループを作るのと同様です。ある部分式で `\left`、別の部分式で `\right` を使うことはできません。また、`\left(...{...\right...}` や `\left(...\begingroup...\right)...\endgroup` のように書くこともできません。これは、TeX が `\left` と `\right` の間にある部分式を先に組版し、その後で区切りの大きさを決定する必要があるためです。`\left` と `\right` を使用しない場合は、丸括弧や角括弧を必ずしも一致させる必要はありません。したがって、たとえば次のように書くことが許容されます。

`$[0,1)$

しかし、`\left` と `\right` を使用していても、必ずしも同じ記号で対になる必要はなく、`\left)` や `\right(` のように書いてもエラーにはなりません。

---

### なぜ `\bigl` や `\bigr` 系列を学ぶ必要があるのか？

TeX が自動的に `\left` と `\right` のサイズを計算できるので、必ずしも手動でサイズを選ぶ必要はありません。しかし、次のようなケースでは自分で区切りのサイズを決めたくなることがあります。

1. **可読性の比較**  
   以下の 2 つの式を比べてみてください。

   ![\left と \right と \bigl と \bigr（縦棒）](/tex/images/java/tutorial/latex-math-7-11.png)

   ` \left` と `\right` を使うと必ずしも最適なサイズにならず、可読性が損なわれることがあります。

2. **過大な区切り**  
   大きな演算子がディスプレイ数式に含まれると、`\left` と `\right` が過大な区切りを選んでしまうことがあります。

   ![\left と \right と \bigl と \bigr（総和）](/tex/images/java/tutorial/latex-math-7-12.png)

   この場合、`\bigg` 区切りを使う方が見た目がすっきりします。

3. **複数行にわたる大きな式**  
   巨大なディスプレイ数式を複数行に分割する際、開始行と終了行で同じサイズの区切りを保ちたいが、`\left` は最初の行で、`\right` は最後の行でしか使用できません。解決策は、最初の行で `\Biggl`（例）を、最後の行で `\Biggr` を使うことです。

> `\left` と `\right` は任意に大きな区切りを生成できますが、スラッシュや山括弧には最大サイズが存在します。非常に大きなバージョンを要求すると、利用可能な最大サイズが出力されます。

### 空白（null）区切りの作り方

ある式で視覚的に「大きな区切りが一つだけ」必要な場合があります。そのようなときに使えるのが「null（空）区切り」です。例として

![null 区切りの例](/tex/images/java/tutorial/latex-math-7-13.png)

は左側に `{` があり右側に `}` が無い形です。次のように書くことで実現できます。

```tex
$|x|=\left\{ ... \right.$ 
```

ここで `\right.` が右側の空白区切りを生成します。

### 追加の区切り記号

LaTeX には基本の 22 個に加えて、特殊な用途向けの区切りもいくつか用意されています。`\arrowvert`, `\Arrowvert`, `\bracevert` はそれぞれ垂直矢印、二重垂直矢印、太い中括弧の繰り返し部分だけから作られ、矢尻や中括弧の丸みはありません。`\vert` や `\Vert` と似た結果になりますが、余白が多く、太さも異なります。さらに `\lgroup`, `\rgroup`（中身のない中括弧）、`\lmoustache`, `\rmoustache`（大きな中括弧の上半分・下半分）というコマンドもあります。以下は `\Big` と `\bigg` バージョンの `\vert`, `\Vert` とこれら 7 つの特殊区切りを示す例です。

![Additional delimiters provided by LaTeX](/tex/images/java/tutorial/latex-math-7-14.png)

`\lgroup` と `\rgroup` は太めの丸括弧に似ており、角が鋭くなるため大きなディスプレイで見栄えが良くなります。ただし、`\Big` 以上のサイズでしか使用できない点に注意してください。
