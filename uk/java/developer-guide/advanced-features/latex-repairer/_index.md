---
translation: true
template: /templates/_template-java.md
title: Ремонт файлів LaTeX | Aspose.TeX для Java 
linktitle: Відновлення файлів LaTeX
weight: 30
url: /java/latex-repair/
description: У цій статті описано функцію відновлення файлів LaTeX в API Aspose.TeX для Java. Ознайомтеся з прикладами коду, як використовувати цю функцію.
lastmod: 2024-09-20
---

{{<section overview>}}

## Як перевірити та відновити файл LaTeX

Якщо ви не впевнені, чи є текстовий файл файлом LaTeX, і хочете, щоб він був набраний, ви можете скористатися функцією перевірки та відновлення LaTeX, яку пропонує Aspose.TeX API для Java. У наведеному нижче прикладі ми перевіримо та відновимо зразок файлу `invalid-latex.tex` із прикладу проекту Aspose.TeX для Java.

Для початку важливо зазначити, що файл зразка, здається, використовує синтаксис TeX, але йому бракує структури, необхідної для LaTeX. Як ви, мабуть, знаєте, файл LaTeX повинен містити преамбулу, яка починається з команди \documentclass, а також тіло, укладене в середовище документа, зокрема між \begin{document} і \end{document}.

Давайте тепер розглянемо зразок коду Java.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Подібно до звичайного завдання TeX, ми починаємо зі створення об’єкта, який містить параметри процесу, який ми збираємося запустити. Більшість із цих параметрів такі самі, як і для звичайної роботи TeX. Дійсно, викликаючи метод [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), ми вказуємо простір, з якого слід читати вхідні файли. Однак у цьому прикладі ми не використовуємо його тут, оскільки ми надаємо повний шлях до основного вхідного файлу у файловій системі, і жодні спеціальні файли не повинні включатися в основний вхідний файл. Далі ми викликаємо метод [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-), щоб вказати простір, куди повинні бути записані вихідні файли. Якщо викликати метод [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-), параметри вказують на простір, де ви можете зберігати пакети LaTeX, які не вбудовані в бібліотеку Aspose.TeX. Нарешті, метод [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) буде обговорено пізніше.

Після призначення параметрів ми можемо продовжити запуск процесу.

Отже, як виглядає процес перевірки та ремонту? Він починається з того, що API шукає `\documentclass` у вхідному файлі. Якщо його не знайдено, API припускає, що `\documentclass{article}` має бути вставлено на початку файлу. Ця інформація записується у файл звіту про ремонт (.log).

Далі процес починає сканування скоригованого вхідного файлу з самого початку. Механізм TeX, обладнаний форматом LaTeX, може в якийсь момент видати помилку, яка вказує на те, що `\begin{document}` ще не знайдено, хоча він уже мав бути. Таким чином, позиція, у яку потрібно вставити `\begin{document}`, визначається та відображається у звіті.

Під час подальшого сканування файлу механізм може натрапити на невизначені команди чи середовища. У таких випадках API може зробити припущення щодо [вбудованих необхідних пакетів](/tex/{{lang.url-fragment}}net/embedded-packages/) (тих, що визначають команди та середовища, які не визначені, доки ці пакети не включено) для деяких із найпоширеніших команд і середовищ. Однак можна зробити такі припущення ззовні за допомогою класу, який реалізує інтерфейс [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). Після того, як ви розробили такий клас, його екземпляр слід передати процесу за допомогою виклику методу `setGuessPackageCallback()`.

Ось базовий приклад, який просто відображає команду `\head` на пакет `fancyhdr`:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}
Що стосується файлу зразка, система спочатку зустрічає команду `\chapter`, яка не визначена в класі документа `article`, але визначена в класі документа `book`. API налаштовує клас документа так, щоб остаточна версія виправленого файлу починалася з `\documentclass{book}`. Потім механізм знаходить вищезгадану команду `\lhead` і визначає, що `\usepackage{fancyhdr}` потрібно вставити в преамбулу. Команди `\href` і `\includegraphics`, які з’являються пізніше у файлі, змушують Repairer вставляти `\usepackage{hyperref}` і `\usepackage{graphics}` у преамбулі відповідно. Ці рішення приймаються на основі внутрішніх зіставлень API. Як і раніше, усі ці ремонти реєструються у файлі звіту.

Нарешті, механізм ненормально завершує роботу, оскільки відсутній належний висновок документа LaTeX. У результаті Repairer додає `\end{document}` у кінець файлу та включає цю інформацію у звіт.

Після створення фіксованої версії оригінального файлу Ремонтник запускає над ним завдання TeX для остаточної перевірки. У нашому прикладі цей запуск не виявляє жодних критичних помилок, тому виправлену версію можна надрукувати більш-менш так, як очікувалося.

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