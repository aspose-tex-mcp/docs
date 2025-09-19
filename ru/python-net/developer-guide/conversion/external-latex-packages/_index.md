---
translation: true
template: /templates/_template-python-net.md
title: Внешние пакеты LaTeX | Python через .NET
linktitle: Внешние пакеты LaTeX
weight: 19
url: /python-net/external-latex-packages/
description: Aspose.TeX API для Python поддерживает использование внешних пакетов, которые не включены в саму библиотеку, таких как пакеты Fancybox и pgfplots.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Внешние пакеты LaTeX

Библиотека **Aspose.TeX** поставляется с множеством [общих пакетов LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/), поэтому нет необходимости вручную предоставлять эти пакеты движку TeX. Однако могут возникнуть ситуации, когда вашему файлу LaTeX потребуется пакет, который не включен в «набор» пакетов библиотеки. В таких случаях вы можете попробовать предоставить необходимые входные данные, например исходные файлы требуемого пакета, через опцию [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) экземпляра класса [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Мы рассмотрим, как это работает, на двух примерах.

### Необходимые данные предоставляются в распакованном виде (пакетfancybox).

Предположим, у нас есть следующий базовый файл LaTeX с именем `required-input-fs.tex`, который является частью нашего [примера решения](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

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

Третья строка файла указывает на то, что требуется пакет «fancybox», который не входит в «родную» поддержку. Предположим, у нас есть исходный файл пакетаfancybox. Поскольку это простой пакет, состоящий из одного файла, мы можем разместить этот файл в любом месте нашей файловой системы и указать путь к каталогу следующим образом:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Как только мы запустим задание TeX с этой опцией (не забудьте при необходимости настроить другие параметры), мы получим выходной документ, который в данном случае представляет собой изображение PNG.

![Выходной документ](/tex/images/python-net/Conversion-RequiredInputFs.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Предоставление необходимых данных в заархивированном виде (пакет pgfplots)

Теперь предположим, что у нас есть следующий файл LaTeX с именем `required-input-zip.tex`, который также является простым файлом из нашего примера решения:


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

В третьей строке можно заметить, что для файла необходим пакет pgfplots, который не поддерживается «изначально». Еще раз, если предположить, что у нас есть исходные файлы для пакета `pgfplots`, эти файлы довольно многочисленны и расположены в двух разных каталогах внутри каталога установки любого приложения для набора текста LaTeX. Папку pgfplots можно найти как в каталогах `\tex\generic`, так и в `\tex\latex`. Для корректной работы библиотеки Aspose.TeX необходимо предоставить в качестве входных данных содержимое обеих этих папок. Для этого мы хотим упаковать эти исходные файлы в ZIP-архив. Ниже желаемый макет архива:

![Макет архива](/tex/images/python-net/pgfplots-zip-layout.png)

А вот метод, которым мы определяем доступность к этим исходным файлам:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

После запуска задания TeX с этой опцией мы получим выходной документ:

![Выходной документ](/tex/images/python-net/Conversion-RequiredInputZip.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_ПРИМЕЧАНИЕ:_** Результат был проверен с использованием пакета `pgfplots` версии 1.18.1. В то время как версия пакета `pfg`, включенного в библиотеку **Aspose.TeX**, - 3.1.9a.

<!--
### Использование внешних пакетов шрифтов

Обычно дистрибутивы LaTeX поставляются с предопределенным набором шрифтов, которые можно использовать для набора текста. Однако, в дополнение к этим шрифтам по умолчанию, **Aspose.TeX** также включает несколько нестандартных пакетов шрифтов, таких как `amsfonts`, `eurosym` и `wasysym`. Как мы уже обсуждали ранее, Aspose.TeX также поддерживает использование внешних пакетов, хотя большая часть нашего предыдущего обсуждения была сосредоточена на пакетах, которые не включают шрифты.

Расширение движка *Object TeX* **Aspose.TeX** требует карт шрифтов, которые представляют собой текстовые файлы в определенном формате с расширением `.map`, чтобы определить соответствующие физические шрифты для каждого внутреннего имени шрифта TeX. Эти карты шрифтов необходимо загрузить в память TeX во время фазы инициализации, и их следует включить в используемый вами пакет. Так как движок не знает имен всех карт шрифтов, он ищет файлы с расширением `.map`. Поэтому при указании значения для параметра [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) реализация интерфейса [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) должна разрешать доступ к коллекциям имен файлов по расширению. Кроме того, эта реализация должна также реализовывать интерфейс [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Стандартные реализации, такие как [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) и [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), уже соответствуют этим требованиям.

Ниже приведен пример пользовательского требуемого входного каталога, демонстрирующий, как реализовать интерфейс [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Этот пример фокусируется на сборе имен файлов по расширению и намеренно опускает детали хранения и извлечения файлов.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}
-->

### Ограничения

Если вы встретите пакет, разработанный под ядром *LaTeX3e* и необходимый для вашего файла LaTeX, он вряд ли будет работать с библиотекой **Aspose.TeX**. Это связано с тем, что библиотека основана на ядре *LaTeX2e*.

Кроме того, могут быть случаи, когда пакет, требуемый вашим файлом LaTeX, напрямую использует зависящие от устройства примитивные команды, которые не поддерживаются механизмом *Object TeX* библиотеки **Aspose.TeX**. В таких случаях пакет не будет работать с библиотекой.