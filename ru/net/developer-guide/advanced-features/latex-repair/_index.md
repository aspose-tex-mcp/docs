---
translation: true
template: /templates/_template-net.md
title: Восстановление файлов LaTeX | .NET 
linktitle: восстановление файлов LaTeX
weight: 30
url: /net/latex-repair/
description: Решение Aspose.TeX API для восстановления .NET LaTeX описано в этой статье. Изучите примеры кода о том, как использовать эту функциональность.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Как проверить и восстановить файл LaTeX

Если у вас есть текстовый файл, который, по вашему мнению, является файлом LaTeX, и вы хотите, чтобы он был набран, но вы не уверены, действительно ли это файл LaTeX (возможно, вы новичок в мире LaTeX), вы можете попробовать использовать проверку и восстановление функции LaTeX, предоставляемой API Aspose.TeX для .NET. В следующем примере мы проверим и исправим образец файла invalid-latex.tex из примера проекта Aspose.TeX для .NET.

Прежде всего, стоит отметить, что, хотя файл примера использует синтаксис TeX, он не имеет структуры, требуемой LaTeX. Как вы, возможно, знаете, файл LaTeX должен иметь преамбулу, которая начинается с команды `\documentclass` и тело внутри среды `document`, то есть между `\begin{document}` и `\end{document}`.

Давайте теперь посмотрим на пример кода C#.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-LaTeXRepairer.cs" >}}

Как и в обычном задании TeX, мы сначала создаем объект, содержащий параметры процесса, который мы собираемся запустить. Большинство из них такие же, как и в обычном задании TeX. Действительно, [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) — это пространство, из которого следует читать входные файлы. Мы не используем его здесь, поскольку мы указываем полный путь к основному входному файлу в файловой системе, и никакие пользовательские файлы не должны включаться в основной входной файл. Затем [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) — это пространство, куда должны быть записаны выходные файлы. [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), если назначено, указывает на пространство, где вы можете хранить пакеты LaTeX, которые не встроены в библиотеку Aspose.TeX. Свойство [GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) будет обсуждаться позже.

После назначения опций мы просто запускаем процесс!

Итак, каков же процесс проверки и ремонта? Во-первых, API ищет во входном файле вхождение `\documentclass`. Если это не удается, предполагается, что `\documentclass{article}` должен быть вставлен в самое начало файла. Этот факт отражается в файле отчета о ремонте (`.log`).

Затем он начинает сканирование скорректированного входного файла с самого начала. Движок TeX, использующий формат LaTeX, может в какой-то момент выдать ошибку, сигнализируя, что `\begin{document}` пока не найден, хотя это уже должно было произойти. Таким образом, позиция, в которой необходимо вставить `\begin{document}`, определяется и отражается в отчете.

По мере дальнейшего сканирования файла механизм может обнаружить неопределенные команды или среды. API может делать предположения относительно [встроенных необходимых пакетов](/tex/{{lang.url-fragment}}net/embedded-packages/) (тех, которые определяют команды и среды, которые не определены до тех пор, пока эти пакеты не будут включены) для некоторых наиболее распространенных команд и сред. Однако есть способ сделать такие предположения извне, реализовав интерфейс [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/). Экземпляр такого класса должен быть назначен опции GuessPackageCallback.

Вот очень простой пример, который просто сопоставляет команду `\head` с пакетом `fancyhdr`:


{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.cs" >}}

Что касается файла примера, движок сначала встречает команду `\chapter`, которая не определена в классе документа `article`, но определена в классе документа `book`. API корректирует класс документа так, чтобы окончательная версия фиксированного файла начиналась с `\documentclass{book}`. Затем движок находит вышеупомянутую команду `\lhead` и решает, что `\usepackage{fancyhdr}` необходимо вставить в преамбулу. Команды `\href` и `\includegraphics`, которые появляются позже, заставляют Repairer вставлять `\usepackage{hyperref}` и `\usepackage{graphics}` в преамбулу соответственно. Эти решения основаны на внутренних сопоставлениях API. Опять же, все подобные исправления записываются в файл отчета.

Наконец, механизм аварийно завершает работу, поскольку нормальное окончание документа LaTeX отсутствует. Это заставляет Repairer добавлять `\end{document}` в конец файла и отражать этот факт в отчете.

После того как исправленная версия исходного файла будет создана, Repairer запускает для него задание TeX для окончательной проверки. В нашем примере этот запуск не обнаружил никаких критических ошибок, поэтому исправленная версия может быть набрана более или менее так, как ожидалось.

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