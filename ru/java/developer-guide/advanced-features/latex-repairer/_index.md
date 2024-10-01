---
translation: true
template: /templates/_template-java.md
title: Восстановление файлов LaTeX | Java
linktitle: восстановление файлов LaTeX
weight: 30
url: /java/latex-repair/
description: Функция восстановления файлов LaTeX в API Aspose.TeX для Java описана в этой статье. Изучите примеры кода, показывающие, как использовать эту функциональность.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Как проверить и восстановить файл LaTeX

Если вы не уверены, является ли текстовый файл файлом LaTeX, и хотите, чтобы он был набран, вы можете использовать функцию проверки и восстановления LaTeX, предлагаемую API Aspose.TeX для Java. В приведенном ниже примере мы проверим и исправим образец файла invalid-latex.tex из примера проекта Aspose.TeX для Java.

Для начала важно отметить, что в примере файла используется синтаксис TeX, но ему не хватает структуры, требуемой LaTeX. Как вы, возможно, знаете, файл LaTeX должен включать преамбулу, которая начинается с команды \documentclass, а также тело, заключенное в среду документа, в частности, между \begin{document} и \end{document}.

Давайте теперь посмотрим на пример кода Java.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Как и в обычном задании TeX, мы начинаем с создания объекта, содержащего параметры процесса, который мы собираемся запустить. Большинство этих опций такие же, как и для обычного задания TeX. Действительно, вызывая метод [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), мы указываем пространство, из которого должны читаться входные файлы. Однако в этом примере мы не используем его, поскольку мы указываем полный путь к основному входному файлу в файловой системе, и никакие пользовательские файлы не должны включаться в основной входной файл. Затем мы вызываем метод [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-), чтобы указать пространство, в которое должны быть записаны выходные файлы. При вызове метод [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) указывает параметры на пространство, где вы можете хранить пакеты LaTeX, которые не встроены в библиотеку Aspose.TeX. Наконец, метод [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) будет обсуждаться позже.

После того, как параметры были назначены, мы можем приступить к запуску процесса.

Итак, каков же процесс проверки и ремонта? Все начинается с того, что API ищет вхождение `\documentclass` во входном файле. Если он не найден, API предполагает, что `\documentclass{article}` должен быть вставлен в начало файла. Эта информация записывается в файл отчета о ремонте (.log).

Далее процесс начинает сканирование скорректированного входного файла с самого начала. Движок TeX, оснащенный форматом LaTeX, может в какой-то момент выдать ошибку, указывающую, что `\begin{document}` еще не найден, хотя он уже должен был быть найден. Таким образом, позиция, в которой необходимо вставить `\begin{document}`, определяется и отражается в отчете.

При дальнейшем сканировании файла движок может встретить неопределенные команды или среды. В таких случаях API может делать предположения относительно [встроенных необходимых пакетов](/tex/{{lang.url-fragment}}net/embedded-packages/) (тех, которые определяют команды и среды, которые не определены до тех пор, пока эти пакеты не будут включены) для некоторых из наиболее распространенных команд и сред. Однако такие предположения можно сделать извне с помощью класса, реализующего интерфейс [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). После того как вы разработали такой класс, его экземпляр следует передать процессу, вызвав метод setGuessPackageCallback().

Вот базовый пример, который просто сопоставляет команду `\head` с пакетом `fancyhdr`:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}
Что касается файла примера, движок сначала встречает команду `\chapter`, которая не определена в классе документа `article`, но определена в классе документа `book`. API корректирует класс документа так, чтобы окончательная версия восстановленного файла начиналась с `\documentclass{book}`. Затем движок находит вышеупомянутую команду `\lhead` и определяет, что `\usepackage{fancyhdr}` необходимо вставить в преамбулу. Команды `\href` и `\includegraphics`, которые встречаются позже в файле, заставляют Repairer вставлять `\usepackage{hyperref}` и `\usepackage{graphics}` в преамбулу соответственно. Эти решения принимаются на основе внутренних сопоставлений API. Как и прежде, все эти ремонты фиксируются в файле отчета.

Наконец, механизм аварийно завершает работу, поскольку отсутствует правильное заключение документа LaTeX. В результате Repairer добавляет `\end{document}` в конец файла и включает эту информацию в отчет.

После создания исправленной версии исходного файла Repairer запускает для него задание TeX для окончательной проверки. В нашем примере этот прогон не обнаруживает каких-либо критических ошибок, поэтому исправленную версию можно набрать более или менее так, как ожидалось.

Вот полный отчет:

```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**Вы также можете воспользоваться нашим бесплатным веб-приложением [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer), которое создано на основе функции, реализованной в [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) и включает в себя более продвинутый реализация интерфейса IGuessPackageCallback.**