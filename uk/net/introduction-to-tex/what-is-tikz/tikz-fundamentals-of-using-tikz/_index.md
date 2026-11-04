---
translation: true
template: /templates/_template-net.md
title: Основи використання TikZ | Aspose.TeX .NET
linktitle: Основи TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: основи tikz, основи tikz, навчальний посібник з tikz
description: Дослідіть фундаментальні принципи та основні команди TikZ для створення графіки для ваших документів TeX та LaTeX.
lastmod: "2026-11-04"
---

{{<section overview>}}

У цьому розділі ми розглянемо основні принципи та команди TikZ. Розуміння цих основ дозволить вам створювати чітку та виразну графіку для ваших документів.

## Система координат у TikZ

Графіка TikZ створюється за допомогою координат. Координати визначають положення на ваших малюнках і можуть бути вказані різними способами:

- **Декартові координати (x,y)**:

```tex
\documentclass{article}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    \draw (0,0) -- (2,2);
\end{tikzpicture}
\end{document}
```

- **Полярні координати (кут:радіус)**:

```tex
    \draw (0,0) -- (45:2);
```

Координати можна вільно змішувати в кресленні для досягнення бажаного графічного результату.

*Коротке зауваження щодо відносних зміщень:

- (0,0) -- ++(1,1) переміщується в точку (0,0), проводить лінію до (1,1) і встановлює нову поточну точку в (1,1).
- (0,0) -- +(1,1) проводить лінію до (1,1) відносно точки (0,0), але залишає поточну точку незмінною — у (0,0).*

## Малювання основних фігур

TikZ дозволяє легко створювати основні геометричні фігури:

- **Лінії та полілінії**:


```tex
    \draw (0,0) -- (1,1) -- (2,0);
```

- **Прямокутники**:

```tex
    \draw (0,0) rectangle (2,1);
```

- **Кола та еліпси**:

```tex
   \draw (1,1) circle (0.5);
    \draw (3,1) ellipse (1 and 0.5);
```

## Кольори та візерунки заливки

Кольори та заливки значно покращують візуальну чіткість. Ви можете вказати кольори безпосередньо або використовувати попередньо визначені назви:

```tex
   \draw[red, thick] (0,0) rectangle (1,1);
   \draw[fill=blue!20] (2,0) circle (0.5);
```

Синтаксис `blue!20` означає синій колір з інтенсивністю 20%.

## Стилі та товщина ліній

TikZ дозволяє змінювати стилі та товщину ліній для покращення графічного представлення:

- **Товщина лінії**:

```tex
   \draw[ultra thick] (0,0) -- (1,1);
   \draw[thin] (1,0) -- (2,1);
```

- **Пунктирні та пунктирні лінії**:

```tex
   \draw[dashed] (0,0) -- (2,2);
   \draw[dotted] (2,0) -- (4,2);
```

## Вузли та мітки

Вузли дозволяють легко додавати будь-які текстові анотації:

```tex
   \draw (0,0) -- (1,1) 
```

Ви можете точно розташовувати підписи відносно ваших графічних елементів, покращуючи читабельність.

## Контури та криві

Контури TikZ можуть бути прямими лініями або кривими. Криві створюються за допомогою простого синтаксису:

```tex
   \draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Контрольні точки інтуїтивно формують кривизну.

## Групування елементів

Групування графічних елементів спрощує трансформації (такі як масштабування та обертання):

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Елементи в межах `scope` обертаються та масштабуються разом, зберігаючи вирівнювання.

---

Опанування цих фундаментальних концепцій та команд TikZ закладе міцну основу для створення складної графіки для ваших документів.

## Приклад програмної обробки малюнків TikZ за допомогою Aspose.TeX

Нижче наведено детальний опис процесу та приклад коду, що демонструє, як розробники можуть компілювати документ `.tex`, який містить малюнки TikZ, безпосередньо у високоякісний векторний формат (PDF) у межах керованого .NET-застосунку.

```csharp
using System;
using System.IO;
using Aspose.TeX;
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;

namespace AsposeTexTikzDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Визначення вхідного та вихідного каталогів
            string dataDir = @"C:\DocumentSamples\TikzInput";
            string outputDir = @"C:\DocumentSamples\TikzOutput";

            // Перевірка наявності вихідного каталогу
            Directory.CreateDirectory(outputDir);

            // Ініціалізація параметрів TeX для стандартного завдання обробки документа LaTeX
            // TeXConfig.ObjectLaTeX налаштовує рушій із вбудованими пакетами (зокрема tikz/pgf)
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            options.InputWorkingDirectory = new InputFileSystemDirectory(dataDir);
            options.OutputWorkingDirectory = new OutputFileSystemDirectory(outputDir);

            // Встановлення імені завдання, яке використовується для вихідних файлів
            options.JobName = "tikz-fundamentals";

            // Налаштування параметрів збереження для відтворення безпосередньо у формат PDF
            options.SaveOptions = new PdfSaveOptions();

            // Створення та виконання TeXJob із вихідним файлом, пристроєм виводу та параметрами
            Console.WriteLine("Starting TikZ compilation job...");

            TeXJobResult result = new TeXJob(
                Path.Combine(dataDir, "tikz-fundamentals.tex"),
                new PdfDevice(),
                options
            ).Run();

            if (result < TeXJobResult.ErrorMessageIssued)
                Console.WriteLine($"TikZ graphic successfully compiled to PDF at: {outputDir}");
            else
                Console.WriteLine($"Compilation failed with {result}. See the .log file in {outputDir}.");
        }
    }
}
```

**Крім того, ознайомтеся з нашим безкоштовним [веб-додатком](https://products.aspose.app/tex/conversion/latex/) на основі [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) для швидкого та легкого перетворення TeX.**
