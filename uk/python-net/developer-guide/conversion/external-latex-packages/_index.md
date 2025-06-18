---
translation: true
template: /templates/_template-python-net.md
title: Зовнішні пакети LaTeX | Aspose.TeX для Python
linktitle: Зовнішні пакети LaTeX
weight: 19
url: /python-net/external-latex-packages/
description: API Aspose.TeX для Python підтримує використання зовнішніх пакетів, які не входять до самої бібліотеки, наприклад пакетів fancybox і pgfplots
lastmod: "2025-06-13"
---

{{<section overview>}}

## Зовнішні пакети LaTeX

Бібліотека **Aspose.TeX** постачається з різними [поширеними пакетами LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/), тому немає необхідності вручну надавати ці пакети механізму TeX. Однак можуть виникнути ситуації, коли для вашого файлу LaTeX потрібен пакунок, який не входить до «набору» пакунків бібліотеки. У таких випадках ви можете спробувати надати необхідні вхідні дані, такі як вихідні файли необхідного пакунка, за допомогою параметра [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) екземпляра класу [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Ми розглянемо, як це працює, на двох прикладах.

### Необхідні вхідні дані надаються в розпакованому вигляді (пакет `fancybox`).

Припустімо, що у нас є такий базовий файл LaTeX під назвою `required-input-fs.tex`, який є частиною нашого [прикладу рішення](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET):

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

Третій рядок файлу вказує на те, що для нього потрібен пакунок `fancybox`, який не включено до "рідної" підтримки. Припустімо, що у нас є вихідний файл для пакета `fancybox`. Оскільки це простий пакет, що складається з одного файлу, ми можемо розмістити цей файл у будь-якому місці нашої файлової системи та вказати шлях до каталогу наступним чином:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Після того, як ми запустимо завдання TeX із цією опцією (не забудьте налаштувати інші опції за потреби), ми отримаємо вихідний документ, який у цьому випадку є зображенням у форматі PNG.

![Вихідний документ](/tex/images/python-net/Conversion-RequiredInputFs.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Надання необхідних вхідних даних в заархівованій формі (пакет `pgfplots`)

Тепер припустімо, що у нас є такий файл LaTeX під назвою `required-input-zip.tex`, який також є простим файлом із нашого прикладу рішення:


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

У третьому рядку можна помітити, що для файлу потрібен пакет `pgfplots`, який не підтримується "нативно". Знову ж таки, припускаючи, що у нас є вихідні файли для пакета `pgfplots`, цих файлів досить багато і вони розташовані у двох різних каталогах у каталозі інсталяції будь-якої програми верстки LaTeX. Папку `pgfplots` можна знайти в обох каталогах `\tex\generic` і `\tex\latex`. Щоб бібліотека Aspose.TeX функціонувала правильно, необхідно надати вміст обох цих папок як вхідні дані. Щоб досягти цього, ми хочемо запакувати ці вихідні файли в ZIP-архів. Нижче наведено бажаний макет архіву:

![Оформлення архіву](/tex/images/python-net/pgfplots-zip-layout.png)

А ось метод, за допомогою якого ми визначаємо доступність цих вихідних файлів:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Після виконання завдання TeX із цією опцією ми отримуємо вихідний документ:

![Вихідний документ](/tex/images/python-net/Conversion-RequiredInputZip.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_ПРИМІТКА:_** Результат було перевірено за допомогою пакета `pgfplots` версії 1.18.1. У той час як версія пакета `pfg`, включеного в бібліотеку **Aspose.TeX**, є 3.1.9a.

<!--
### Використання зовнішніх пакетів шрифтів

Як правило, дистрибутиви LaTeX постачаються з попередньо визначеним набором шрифтів, які можна використовувати для верстки. Однак, окрім цих типових шрифтів, **Aspose.TeX** також містить кілька нестандартних пакетів шрифтів, таких як `amsfonts`, `eurosym` і `wasysym`. Як ми обговорювали раніше, Aspose.TeX також підтримує використання зовнішніх пакетів, хоча більша частина нашого попереднього обговорення була зосереджена на пакетах, які не містять шрифтів.

Розширення двигуна *Object TeX* **Aspose.TeX** вимагає карт шрифтів, які є текстовими файлами в певному форматі з розширенням `.map`, щоб визначити відповідні фізичні шрифти для кожної назви внутрішнього шрифту TeX. Ці карти шрифтів потрібно завантажити в пам’ять TeX під час фази ініціалізації та включити до пакета, який ви використовуєте. Оскільки механізм не знає назв усіх карт шрифтів, він шукає файли з розширенням `.map`. Таким чином, коли вказується значення параметра [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/), реалізація [IInputWorkingDirectory](https:/ /reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) інтерфейс має дозволяти доступ до колекцій імен файлів за розширенням. Крім того, ця реалізація також має реалізовувати інтерфейс [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Стандартні реалізації, такі як [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) і [InputZipDirectory](https://reference.aspose.com/ tex/python-net/aspose.tex.io/inputzipdirectory/), уже відповідає цим вимогам.

Нижче наведено приклад спеціального необхідного каталогу введення, який демонструє, як реалізувати інтерфейс [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). У цьому прикладі зосереджено на зборі імен файлів за розширенням і навмисно опущено деталі зберігання та отримання файлів.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.py" >}}
-->

### Обмеження

Якщо ви натрапите на пакет, розроблений під ядром *LaTeX3e* і потрібен для вашого файлу LaTeX, навряд чи він працюватиме з бібліотекою **Aspose.TeX**. Це тому, що бібліотека базується на ядрі *LaTeX2e*.

Крім того, можуть бути випадки, коли пакет, необхідний для вашого файлу LaTeX, безпосередньо використовує залежні від пристрою примітивні команди, які не підтримуються механізмом *Object TeX* бібліотеки **Aspose.TeX**. У таких випадках пакет не працюватиме з бібліотекою.