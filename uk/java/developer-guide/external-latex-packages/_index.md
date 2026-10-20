---
translation: true
template: /templates/_template-java.md
title: Зовнішні пакети LaTeX | Aspose.TeX для Java
linktitle: Зовнішні пакети LaTeX
weight: 30
url: /java/external-latex-packages/
description: API Aspose.TeX для Java дозволяє використовувати зовнішні Пакети, тобто ті, які не входять до самої бібліотеки, як Пакети fancybox або pgfplots.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Зовнішні пакети LaTeX

До бібліотеки **Aspose.TeX** для Java включено кілька [поширених пакетів LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Тому вам не потрібно піклуватися про те, як надати ці Пакети механізму TeX бібліотеки. Але іноді (можливо, часто) для вашого файлу LaTeX може знадобитися пакет, окрім "нативно" підтримуваного "набору" пакетів. У цьому випадку ви можете спробувати надати необхідні вхідні дані, тобто вихідні файли необхідного пакета, використовуючи метод [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) екземпляра класу [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Ми побачимо, як це працює, на двох прикладах.

Укажіть у `inputFile` повний шлях до відповідного документа LaTeX, а в `outputDirectory` — наявну папку виведення. Обидва приклади перетворення створюють PNG із роздільною здатністю 150 DPI. Імпортуйте класи Aspose.TeX із вибраного прикладу, `com.aspose.tex.rendering.ImageDevice`, `com.aspose.tex.rendering.PngSaveOptions`, а для введення із ZIP — `java.io.InputStream` і `java.nio.file.Files`. Обробляйте або оголошуйте винятки в методі виклику. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/).

### Розпаковане необхідне введення (пакет `fancybox`)

Скажімо, у нас є такий простий файл LaTeX, який є `required-input-fs.tex` з нашого [прикладу рішення](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java):

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

Третій рядок потребує зовнішнього пакета `fancybox`. Укажіть у `packagesDirectory` локальну папку з `fancybox.sty` і його залежностями. Повний приклад нижче призначає цю папку параметру `RequiredInputDirectory` і створює зображення PNG. Пристрій і робочі папки залишаються відкритими до завершення завдання, потім звільняються або закриваються.

![Вихідний документ](/tex/images/java/Conversion-RequiredInputFs.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-FileSystem.java" >}}

### Архівований необхідний вхід (пакет `pgfplots`)

Давайте тепер припустимо, що у нас є наступний також досить простий файл LaTeX, який є `required-input-zip.tex` з нашого прикладу рішення:


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

У третьому рядку ми бачимо, що для файлу потрібен пакет `pgfplots`, який також не підтримується "нативно". Знову ж таки, ми припускаємо, що у нас є вихідні файли пакета `pgfplots`. Це досить великий набір файлів, які розділені між двома розташуваннями, якщо ви знайдете їх у каталозі встановлення будь-якої програми верстки LaTeX. Ви можете знайти папку `pgfplots` у папках `\tex\generic` і `\tex\latex`. І вміст обох цих папок має бути надано як необхідні вхідні дані для бібліотеки Aspose.TeX. Ми хочемо, щоб ці вихідні файли були запаковані в ZIP-архів, тому ось макет архіву:

![макет архіву](/tex/images/java/pgfplots-zip-layout.png)

Укажіть у `packagesZip` значення `java.nio.file.Path`, що вказує на архів із generic- та LaTeX-файлами пакета. Повний Java-приклад нижче відкриває його через `Files.newInputStream(...)` і призначає `InputZipDirectory` параметру `RequiredInputDirectory`. Порожній аргумент базового шляху вибирає весь архів. Тримайте ZIP-потік і папку відкритими до завершення завдання TeX, потім закрийте їх. Результат — зображення PNG із двома графіками.

![Вихідний документ](/tex/images/java/Conversion-RequiredInputZip.png)

Ось повний вихідний код прикладу:

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-Zip.java" >}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### Використання зовнішніх пакетів шрифтів

Як правило, дистрибутиви LaTeX постачаються з вибором типових шрифтів, які можна використовувати для набору. На додаток до цих шрифтів, **Aspose.TeX** пропонує кілька нестандартних пакетів шрифтів, таких як `amsfonts`, `eurosym` і `wasysym`. Як згадувалося раніше, **Aspose.TeX** також підтримує використання зовнішніх пакетів, хоча ми зосереджені переважно на пакетах, які не містять шрифтів.
Розширення двигуна *Object TeX* у **Aspose.TeX** вимагає карт шрифтів, які є текстовими файлами з розширенням `.map`, які визначають фізичні шрифти, що відповідають назві внутрішнього шрифту кожного TeX. Ці карти шрифтів потрібно завантажити в пам’ять TeX під час фази ініціалізації та включити до файлів пакету. Оскільки механізм не знає назв усіх карт шрифтів, він шукає будь-які файли з розширенням `.map`. Таким чином, реалізація інтерфейсу [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), який використовується як значення параметра [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--), має забезпечувати спосіб доступу до колекцій імен файлів на основі їх розширення. Зокрема, ця реалізація також має реалізовувати інтерфейс [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Стандартні реалізації [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) і [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/) уже відповідають цій вимозі.

Наступний користувацький `RequiredInputDirectory` реалізує обидва інтерфейси та читає явно зареєстровані локальні файли. Збережіть його як `RequiredInputDirectory.java` разом із включеними імпортами. Зареєструйте кожен файл через `storeFileName(...)`, призначте екземпляр через `options.setRequiredInputDirectory(...)` і закрийте його після завдання. Це плоский реєстр: імена файлів мають бути унікальними під час запиту без повного шляху. Розширення порівнюються без урахування регістру; необов’язковий шлях збирання вибирає папку файлової системи. Зареєструйте всі потрібні файли пакета, карти шрифтів, метрики та фізичні файли шрифтів. Збирання файлів робить карти доступними для виявлення, але не надає відсутніх даних шрифтів.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInputDirectory.java" >}}

### Обмеження

Пакет, необхідний для вашого файлу LaTeX, можна розробити в ядрі *LaTeX3e*. Такий пакет, швидше за все, не працюватиме з бібліотекою **Aspose.TeX**, оскільки остання базується на ядрі *LaTeX2e*.

Крім того, пакет, потрібний для вашого файлу LaTeX, може безпосередньо викликати залежні від пристрою примітивні команди, які не підтримуються механізмом *Object TeX* бібліотеки **Aspose.TeX**. Такий пакет, на жаль, працювати точно не буде.