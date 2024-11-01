---
translation: true
template: /templates/_template-net.md
title: Внешние пакеты LaTeX | Aspose.TeX для .СЕТЬ
linktitle: Внешние пакеты LaTeX
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX API для .NET позволяет использовать внешние пакеты, т.е. те, которые не включены в саму библиотеку, например пакеты Fancybox и pgfplots.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Внешние пакеты LaTeX

Библиотека **Aspose.TeX** включает ряд [общих пакетов LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Поэтому вам не придется беспокоиться о том, как предоставить эти пакеты движку TeX библиотеки. Но иногда (или довольно часто) вашему файлу LaTeX может потребоваться пакет, выходящий за рамки «изначально» поддерживаемого «пакета» пакетов. В этом случае вы можете попытаться предоставить требуемые входные данные, то есть исходные файлы требуемого пакета, с помощью опции [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) экземпляра класса [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Мы увидим, как это работает, на двух примерах.

### Распакованный требуемый ввод (пакет «fancybox»)

Допустим, у нас есть следующий простой файл LaTeX, который называется `required-input-fs.tex` из нашего [примера решения](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

В третьей строке мы видим, что для файла требуется пакет «fancybox», который «изначально» не поддерживается. Предположим также, что у нас есть исходный файл пакета «fancybox». Это простой пакет, поэтому он фактически состоит из одного файла. Мы можем разместить этот файл в любом месте нашей файловой системы и указать путь к каталогу, как показано ниже:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

После запуска задания TeX с этой опцией (не забудьте настроить другие параметры по мере необходимости) мы получим выходной документ (т. е. изображение PNG).

![Выходной документ](/tex/images/net/Conversion-RequiredInputFs.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.cs" >}}

### Заархивированные необходимые данные (пакет pgfplots)

Предположим теперь, что у нас есть следующий также довольно простой файл LaTeX, который называется `required-input-zip.tex` из нашего примера решения:


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```


В третьей строке мы видим, что для файла требуется пакет pgfplots, который также не поддерживается «изначально». Опять же, мы предполагаем, что у нас есть исходные файлы пакета pgfplots. Это довольно большое количество файлов, которые разделены между двумя местами, если вы найдете их в каталоге установки любого приложения для набора текста LaTeX. Вы можете найти папку pgfplots в папках `\tex\generic` и `\tex\latex`. И содержимое обеих этих папок должно быть предоставлено в качестве входных данных для библиотеки Aspose.TeX. Мы хотим, чтобы эти исходные файлы были упакованы в ZIP-архив, поэтому вот макет архива:

![Макет архива](/tex/images/net/pgfplots-zip-layout.png)

И вот как мы указываем доступ к этим исходным файлам:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

После запуска задания TeX с этой опцией мы получим выходной документ:

![Выходной документ](/tex/images/net/Conversion-RequiredInputZip.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.cs" >}}

> **_ПРИМЕЧАНИЕ:_** Результат был проверен с использованием пакета `pgfplots` версии 1.18.1. В то время как версия пакета `pfg`, включенного в библиотеку **Aspose.TeX**, - 3.1.9a.

### Использование внешних пакетов шрифтов

Как правило, дистрибутивы LaTeX предоставляют набор шрифтов по умолчанию, доступных для верстки. Помимо этих шрифтов, **Aspose.TeX** включает в себя ряд нестандартных пакетов шрифтов. Например, «amsfonts», «eurosym» и «wasysym». Как мы видели выше, Aspose.TeX также позволяет использовать внешние пакеты. Но в основном мы говорили о пакетах, не содержащих шрифты.
Расширению движка *Object TeX* **Aspose.TeX** требуются карты шрифтов (которые по соглашению представляют собой текстовые файлы определенного формата с расширением `.map`), чтобы определить, какие физические шрифты соответствуют внутреннему имени каждого шрифта TeX. . Эти карты шрифтов должны быть загружены в память TeX на этапе инициализации. И, конечно же, они должны присутствовать среди файлов подключаемого вами пакета. Поскольку движок не знает названия всех карт шрифтов, он ищет все файлы с расширением `.map`. Таким образом, реализация интерфейса [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), который используется в качестве значения опции [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/), должна предоставлять способ доступа к коллекциям имен файлов по расширению. Более конкретно, эта реализация также должна реализовывать интерфейс [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Стандартные реализации — [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) и [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) — уже это делают.

Ниже мы приводим наглядный пример пользовательского обязательного входного каталога, который также реализует интерфейс [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Сосредотачиваясь на сборе имен файлов по расширению, мы намеренно опускаем детали хранения и поиска файлов.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInputDirectory.cs" >}}

### Ограничения

Может случиться так, что пакет, необходимый для вашего файла LaTeX, разработан под ядром *LaTeX3e*. Такой пакет, скорее всего, не будет работать с библиотекой **Aspose.TeX**, поскольку последняя основана на ядре *LaTeX2e*.

Также может случиться так, что пакет, необходимый для вашего файла LaTeX, напрямую вызывает зависящие от устройства примитивные команды, которые не поддерживаются механизмом *Object TeX* библиотеки **Aspose.TeX**. Такой пакет, к сожалению, точно не подойдет.