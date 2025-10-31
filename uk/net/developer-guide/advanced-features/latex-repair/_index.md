---
translation: true
template: /templates/_template-net.md
title: Ремонт файлів LaTeX | .NET
linktitle: Відновлення файлів LaTeX
weight: 30
url: /net/latex-repair/
description: У цій статті описано рішення Aspose.TeX API для відновлення .NET LaTeX. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Як перевірити та відновити файл LaTeX

Якщо у вас є текстовий файл, який, на вашу думку, є файлом LaTeX, і ви хочете, щоб він був набраний, але ви не впевнені, чи це справді файл LaTeX (можливо, ви новачок у світі LaTeX), ви можете спробувати використати перевірку і відновлення функції LaTeX, наданої API Aspose.TeX для .NET. У наступному прикладі ми перевіримо та відновимо зразок файлу `invalid-latex.tex` із прикладу проекту Aspose.TeX для .NET.

Перш за все, варто зазначити, що хоча файл зразка, здається, використовує синтаксис TeX, він не має структури, необхідної для LaTeX. Як ви, можливо, знаєте, файл LaTeX повинен мати преамбулу, яка починається з команди `\documentclass`, і тіло в середовищі `document`, тобто між `\begin{document}` і `\end{document}`.

Давайте тепер розглянемо зразок коду C#.

{{< gist "aspose-com-gists""7f54d335270200ebf5987d071bad028a""Examples_LaTeXRepairerExample" >}}

Як і у випадку зі звичайним завданням TeX, ми спочатку створюємо об’єкт, який містить параметри процесу, який ми збираємося запустити. Більшість із них такі самі, як і параметри звичайної роботи TeX. Дійсно, [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) — це простір, з якого слід читати вхідні файли. Ми не використовуємо його тут, тому що ми надаємо повний шлях до основного вхідного файлу у файловій системі, і жодні спеціальні файли не повинні включатися в головний вхідний файл. Тоді [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) — це простір, куди мають бути записані вихідні файли. [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), якщо його призначено, вказує на простір, де ви можете зберігати пакети LaTeX, які не вбудовані в бібліотеку Aspose.TeX. Властивість [GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) буде обговорено пізніше.

Після призначення параметрів ми просто запускаємо процес!

Отже, як виглядає процес перевірки та ремонту? По-перше, API шукає у вхідному файлі `\documentclass`. Якщо це не вдається, передбачається, що `\documentclass{article}` має бути вставлено на самому початку файлу. Цей факт відображається у файлі звіту про ремонт (`.log`).

Потім він починає сканувати налаштований вхідний файл із самого початку. Механізм TeX, який працює у форматі LaTeX, може в якийсь момент видати помилку, сигналізуючи про те, що `\begin{document}` не знайдено, хоча це вже повинно було статися. Таким чином, позиція, у яку має бути вставлений `\begin{document}`, визначається та відображається у звіті.

Під час подальшого сканування файлу механізм може виявити невизначені команди чи середовища. API може зробити припущення щодо [вбудованих необхідних пакетів](/tex/{{lang.url-fragment}}net/embedded-packages/) (тих, що визначають команди та середовища, які не визначені, доки ці пакети не включено) для деяких із найпоширеніших команд і середовищ. Однак існує спосіб зробити такі припущення зовні, реалізувавши інтерфейс [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/). Екземпляр такого класу слід призначити параметру `GuessPackageCallback`.

Ось дуже простий приклад, який просто відображає команду `\head` на пакет `fancyhdr`:


{{< gist "aspose-com-gists""7f54d335270200ebf5987d071bad028a""Examples_PackageGuessingCallback" >}}

Що стосується файлу зразка, система спочатку зустрічає команду `\chapter`, яка не визначена в класі документа `article`, але визначена в класі документа `book`. API налаштовує клас документа так, щоб остаточна версія фіксованого файлу починалася з `\documentclass{book}`. Потім механізм знаходить вищезгадану команду `\lhead` і вирішує, що `\usepackage{fancyhdr}` потрібно вставити в преамбулу. Команди `\href` і `\includegraphics`, які з’являються пізніше, змушують Repairer вставляти `\usepackage{hyperref}` і `\usepackage{graphics}` у преамбулі відповідно. Ці рішення ґрунтуються на внутрішніх зіставленнях API. Знову ж таки, усі такі виправлення реєструються у файлі звіту.

Нарешті, механізм ненормально завершує роботу, оскільки відсутнє звичайне закінчення документа LaTeX. Це змушує Repairer додавати `\end{document}` у кінець файлу та відображати цей факт у звіті.

Після створення фіксованої версії оригінального файлу Repairer запускає завдання TeX для остаточної перевірки. У нашому прикладі цей запуск не знаходить критичних помилок, тому виправлена ​​версія може бути набрана більш-менш так, як очікувалося.

Ось повний звіт:


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

**Ви також можете ознайомитися з нашою безкоштовною веб-програмою [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer), яка створена на основі функції, реалізованої в [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) і включає більш просунуту реалізація інтерфейсу `IGuessPackageCallback`.**