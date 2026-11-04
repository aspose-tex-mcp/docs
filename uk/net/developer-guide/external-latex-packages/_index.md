---
translation: true
template: /templates/_template-net.md
title: Зовнішні пакети LaTeX | Aspose.TeX для .NET
linktitle: Зовнішні пакети LaTeX
weight: 20
url: /net/external-latex-packages/
description: API Aspose.TeX для .NET дозволяє використовувати зовнішні Пакети, тобто ті, що не входять до самої бібліотеки, як Пакети fancybox і pgfplots.
keywords: зовнішні пакети latex, aspose tex, .net tex, пакети latex, fancybox, pgfplots, обов'язковий вхідний каталог, вхідний zip, користувацький вхідний каталог, конвертація tex
lastmod: "2026-11-04"
---

{{<section overview>}}

## Зовнішні пакети LaTeX

Бібліотека **Aspose.TeX** включає кілька [загальних пакетів LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Тож вам не доведеться турбуватися про те, як надати ці Пакети механізму TeX бібліотеки. Але іноді (або досить часто) для вашого файлу LaTeX може знадобитися пакет, окрім "нативно" підтримуваного "набору" пакетів. Якщо це так, ви можете спробувати надати необхідні вхідні дані, тобто вихідні файли необхідного пакета, за допомогою параметра [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) екземпляра класу [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Ми побачимо, як це працює, на двох прикладах.

### Розпаковане необхідне введення (пакет `fancybox`)

Скажімо, у нас є такий простий файл LaTeX, який є `required-input-fs.tex` з нашого [прикладу рішення](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET):


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

У 3-му рядку ми бачимо, що для файлу потрібен пакет `fancybox`, який не підтримується "нативно". Давайте також припустимо, що у нас є вихідний файл пакета `fancybox`. Це простий пакет, тому він насправді складається з одного файлу. Ми можемо розмістити цей файл у будь-якому місці нашої файлової системи та вказати шлях до каталогу так просто, як показано нижче:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Після виконання завдання TeX із цією опцією (не забудьте налаштувати інші опції за потреби), ми отримуємо вихідний документ (тобто зображення PNG).

![Вихідний документ](/tex/images/net/Conversion-RequiredInputFs.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Архівований необхідний вхід (пакет `pgfplots`)

Давайте тепер скажемо, що у нас є наступний також досить простий файл LaTeX, який є `required-input-zip.tex` з нашого прикладу рішення:


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


У 3-му рядку ми бачимо, що для файлу потрібен пакет `pgfplots`, який також не підтримується "нативно". Знову ж таки, ми припускаємо, що у нас є вихідні файли пакета `pgfplots`. Це досить велика кількість файлів, які розділені між двома розташуваннями, якщо ви знайдете їх у каталозі інсталяції будь-якої програми верстки LaTeX. Ви можете знайти папку `pgfplots` у папках `\tex\generic` і `\tex\latex`. І вміст обох цих папок має бути надано як необхідні вхідні дані для бібліотеки Aspose.TeX. Ми хочемо, щоб ці вихідні файли були запаковані в ZIP-архів, тому ось макет архіву:

![Оформлення архіву](/tex/images/net/pgfplots-zip-layout.png)

І ось як ми визначаємо доступ до цих вихідних файлів:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Після виконання завдання TeX із цією опцією ми отримуємо вихідний документ:

![Вихідний документ](/tex/images/net/Conversion-RequiredInputZip.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_ПРИМІТКА:_** Результат було перевірено за допомогою пакета `pgfplots` версії 1.18.1. У той час як версія пакета `pfg`, включеного в бібліотеку **Aspose.TeX**, є 3.1.9a.

### Використання зовнішніх пакетів шрифтів

Як правило, дистрибутиви LaTeX надають набір типових шрифтів, доступних для верстки. Крім цих шрифтів, **Aspose.TeX** містить ряд нестандартних пакетів шрифтів. Наприклад, `amsfonts`, `eurosym` і `wasysym`. Як ми бачили вище, Aspose.TeX також дозволяє використовувати зовнішні пакети. Але здебільшого ми говорили про пакети, які не містять шрифтів.
Розширенню двигуна *Object TeX* **Aspose.TeX** потрібні карти шрифтів (які є текстовими файлами в певному форматі з розширенням `.map` за домовленістю), щоб визначити, які фізичні шрифти відповідають назві внутрішнього шрифту кожного TeX . Ці карти шрифтів повинні бути завантажені в пам'ять TeX під час фази ініціалізації. І, звичайно, вони повинні бути присутніми серед файлів пакета, який ви підключаєте. Оскільки двигун не знає назв усіх карт шрифтів, він шукає всі файли з розширенням `.map`. Таким чином, реалізація інтерфейсу [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), який використовується як значення параметра [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/), має забезпечувати спосіб доступу до колекцій імен файлів за розширенням. Точніше, ця реалізація також має реалізовувати інтерфейс [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Стандартні реалізації - [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) і [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - вже це роблять.

Нижче ми надаємо ілюстративний приклад спеціального необхідного каталогу введення, який також реалізує інтерфейс [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Зосереджуючись на зборі імен файлів за розширенням, ми навмисно опускаємо деталі зберігання та пошуку файлів.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}

### Обмеження {#restrictions}

Може статися, що пакет, необхідний для вашого файлу LaTeX, розроблено під ядром *LaTeX3e*. Такий пакет, швидше за все, не працюватиме з бібліотекою **Aspose.TeX**, оскільки остання базується на ядрі *LaTeX2e*.

Також може статися так, що пакет, необхідний для вашого файлу LaTeX, безпосередньо викликає залежні від пристрою примітивні команди, які не підтримуються механізмом *Object TeX* бібліотеки **Aspose.TeX**. Такий пакет, на жаль, працювати точно не буде.

## Створення ШІ-агента для оптимізації вбудованих пакетів LaTeX

Якщо вам потрібно створити ШІ-агента, який оптимізує контент для вбудованого інвентарю пакетів без повільних динамічних мережевих пошуків або пошуку у файловій системі під час генерації, ви можете скористатися робочим процесом, описаним нижче.
Замість того щоб змушувати LLM вгадувати, які пакети безпечні або швидкі у використанні, агент орієнтується на цей конкретний, попередньо скомпільований перелік пакетів, щоб уникнути помилок через відсутні пакети.

![Архітектура вбудованого складання документів ШІ-агента](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png)

1. Вилучення наміру макета (шар аналізу LLM)
Користувач надає неструктуровані багатоформатні дані або директиви діалогу. LLM безпосередньо зіставляє запити зі списком вбудованих пакетів Aspose (`colortbl` для затінення рядків, `geometry` для полів і `multirow` для комірок, що займають кілька рядків).

2. Ізоляція AST та додавання преамбули
Замість того щоб писати громіздкі імпорти пакетів, агент перевіряє вимоги до коду за списком вбудованих пакетів.
Він записує в преамбулу лише потрібні команди `\usepackage`.

3. Поток та виконання (вузол механізму Aspose.TeX)
Вихідний код LaTeX передається в `TeXJob` як потік, а `TeXOptions` створюється для `TeXConfig.ObjectLaTeX`. `TeXJob.Run()` виконується синхронно, тому агент запускає його у фоновому робочому процесі.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,multirow,colortbl}
```

4. Серіалізація ресурсів (шар рендерингу виводу)
Завдання записує результат за допомогою пристрою виводу, наприклад `PdfDevice` або `SvgDevice`, і агент повертає його клієнту.