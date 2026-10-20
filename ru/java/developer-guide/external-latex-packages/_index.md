---
translation: true
template: /templates/_template-java.md
title: Внешние пакеты LaTeX | Aspose.TeX для Java
linktitle: Внешние пакеты LaTeX
weight: 30
url: /java/external-latex-packages/
description: API Aspose.TeX для Java позволяет использовать внешние пакеты, то есть те, которые не включены в саму библиотеку, например пакеты Fancybox или pgfplots.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Внешние пакеты LaTeX

Существует ряд [общих пакетов LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/), включенных в библиотеку **Aspose.TeX** для Java. Таким образом, вам не нужно заботиться о том, как предоставить эти пакеты движку TeX библиотеки. Но иногда (возможно, часто) вашему файлу LaTeX может потребоваться пакет, выходящий за рамки «изначально» поддерживаемого «пакета» пакетов. В этом случае вы можете попытаться предоставить требуемые входные данные, то есть исходные файлы требуемого пакета, используя метод [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) экземпляра класса [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Мы увидим, как это работает, на двух примерах.

Укажите в `inputFile` полный путь к соответствующему документу LaTeX, а в `outputDirectory` — существующую папку вывода. Оба примера преобразования создают PNG с разрешением 150 DPI. Импортируйте классы Aspose.TeX из выбранного примера, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions`, а для ввода из ZIP — `java.io.InputStream` и `java.nio.file.Files`. Обрабатывайте или объявляйте исключения в вызывающем методе. Примените лицензию согласно [руководству по лицензированию](/tex/{{lang.url-fragment}}java/licensing/).

### Распакованный требуемый ввод (пакет «fancybox»)

Допустим, у нас есть следующий простой файл LaTeX, который называется `required-input-fs.tex` из нашего [примера решения](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

Третья строка требует внешний пакет `fancybox`. Укажите в `packagesDirectory` локальную папку с `fancybox.sty` и его зависимостями. Полный пример ниже назначает эту папку параметру `RequiredInputDirectory` и создаёт изображение PNG. Устройство и рабочие папки остаются открытыми до завершения задания, затем освобождаются или закрываются.

![Выходной документ](/tex/images/java/Conversion-RequiredInputFs.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-FileSystem.java" >}}

### Заархивированные необходимые данные (пакет pgfplots)

Давайте теперь предположим, что у нас есть следующий также довольно простой файл LaTeX, который называется `required-input-zip.tex` из нашего примера решения:


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

В третьей строке мы видим, что для файла требуется пакет pgfplots, который также не поддерживается «изначально». Опять же, мы предполагаем, что у нас есть исходные файлы пакета pgfplots. Это довольно большой набор файлов, которые разделены между двумя местами, если вы найдете их в каталоге установки любого приложения для набора текста LaTeX. Вы можете найти папку pgfplots в папках `\tex\generic` и `\tex\latex`. И содержимое обеих этих папок должно быть предоставлено в качестве входных данных для библиотеки Aspose.TeX. Мы хотим, чтобы эти исходные файлы были упакованы в ZIP-архив, поэтому вот макет архива:

![макет архива](/tex/images/java/pgfplots-zip-layout.png)

Укажите в `packagesZip` значение `java.nio.file.Path`, указывающее на архив с generic- и LaTeX-исходниками пакета. Полный Java-пример ниже открывает его через `Files.newInputStream(...)` и назначает `InputZipDirectory` параметру `RequiredInputDirectory`. Пустой аргумент базового пути выбирает весь архив. Держите ZIP-поток и папку открытыми до завершения задания TeX, затем закройте их. Результат — изображение PNG с двумя графиками.

![Выходной документ](/tex/images/java/Conversion-RequiredInputZip.png)

Вот полный исходный код примера:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-Zip.java" >}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### Использование внешних пакетов шрифтов

Обычно дистрибутивы LaTeX поставляются с набором шрифтов по умолчанию, которые можно использовать для набора текста. В дополнение к этим шрифтам **Aspose.TeX** предлагает несколько нестандартных пакетов шрифтов, таких как «amsfonts», «eurosym» и «wasysym». Как упоминалось ранее, **Aspose.TeX** также поддерживает использование внешних пакетов, хотя мы в основном фокусировались на пакетах, не включающих шрифты.
Расширение движка *Object TeX* в **Aspose.TeX** требует карт шрифтов, которые представляют собой текстовые файлы с расширением `.map`, которые определяют физические шрифты, соответствующие внутреннему имени шрифта каждого TeX. Эти карты шрифтов необходимо загрузить в память TeX на этапе инициализации и включить в файлы пакета. Поскольку движку неизвестны названия всех карт шрифтов, он ищет любые файлы с расширением `.map`. Следовательно, реализация интерфейса [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), используемого в качестве значения опции [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--), должна предоставлять способ доступа к коллекциям имен файлов на основе их расширения. В частности, эта реализация также должна реализовывать интерфейс [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Стандартные реализации [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) и [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/) уже удовлетворяют этому требованию.

Следующий пользовательский `RequiredInputDirectory` реализует оба интерфейса и читает явно зарегистрированные локальные файлы. Сохраните его как `RequiredInputDirectory.java` вместе с включёнными импортами. Зарегистрируйте каждый файл через `storeFileName(...)`, назначьте экземпляр через `options.setRequiredInputDirectory(...)` и закройте его после задания. Это плоский реестр: имена файлов должны быть уникальными при запросе без полного пути. Расширения сравниваются без учёта регистра; необязательный путь сбора выбирает папку файловой системы. Зарегистрируйте все необходимые файлы пакета, карты шрифтов, метрики и физические файлы шрифтов. Сбор файлов делает карты доступными для обнаружения, но не предоставляет недостающие данные шрифтов.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInputDirectory.java" >}}

### Ограничения

Пакет, необходимый для вашего файла LaTeX, может быть разработан под ядром *LaTeX3e*. Такой пакет, скорее всего, не будет работать с библиотекой **Aspose.TeX**, поскольку последняя основана на ядре *LaTeX2e*.

Кроме того, пакет, необходимый для вашего файла LaTeX, может напрямую вызывать зависящие от устройства примитивные команды, которые не поддерживаются механизмом *Object TeX* библиотеки **Aspose.TeX**. Такой пакет, к сожалению, точно не подойдет.