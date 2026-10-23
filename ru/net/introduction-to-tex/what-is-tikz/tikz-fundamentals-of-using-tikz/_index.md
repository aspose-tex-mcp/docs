---
translation: true
template: /templates/_template-net.md
title: Основы работы с TikZ | Aspose.TeX .NET
linktitle: Основы TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: основы tikz, основы tikz, руководство по tikz
description: Изучите основные принципы и основные команды TikZ для создания графики для документов TeX и LaTeX.
lastmod: 2026-10-22
---

{{<section overview>}}

В этой главе мы рассмотрим основные принципы и команды TikZ. Понимание этих основ позволит вам создавать чёткую и выразительную графику для ваших документов.

## Система координат в TikZ

Графика TikZ строится с использованием координат. Координаты определяют положение объектов на ваших чертежах и могут быть заданы различными способами:

- **Декартовы координаты (x, y)**:

```tex
\documentclass{article}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    \draw (0,0) -- (2,2);
\end{tikzpicture}
\end{document}
```

- **Полярные координаты (угол:радиус)**:


```tex
    \draw (0,0) -- (45:2);
```

*Краткое примечание об относительных смещениях:

- (0,0) -- ++(1,1) — переход в точку (0,0), проведение линии в точку (1,1) и установка новой текущей точки в (1,1).
- (0,0) -- +(1,1) — проведение линии в точку (1,1) относительно (0,0), при этом текущая точка остается неизменной — (0,0).*

Координаты можно свободно комбинировать в чертеже для достижения желаемого графического результата.

## Рисование базовых фигур

TikZ позволяет легко создавать базовые геометрические фигуры:

- **Линии и полилинии**:


```tex
    \draw (0,0) -- (1,1) -- (2,0);
```

- **Прямоугольники**:

```tex
    \draw (0,0) rectangle (2,1);
```

- **Круги и эллипсы**:

```tex
   \draw (1,1) circle (0.5);
    \draw (3,1) ellipse (1 and 0.5);
```

## Цвета и заливки

Цвета и заливки значительно повышают визуальную чёткость. Вы можете указать цвета напрямую или использовать предопределённые названия:

```tex
   \draw[red, thick] (0,0) rectangle (1,1);
   \draw[fill=blue!20] (2,0) circle (0.5);
```

Синтаксис `blue!20` означает синий цвет с интенсивностью 20%.

## Стили и толщина линий

TikZ позволяет изменять стили и толщину линий для улучшения графического представления:

- **Толщина линии**:

```tex
   \draw[ultra thick] (0,0) -- (1,1);
   \draw[thin] (1,0) -- (2,1);
```

- **Пунктирные и пунктирные линии**:

```tex
   \draw[dashed] (0,0) -- (2,2);
   \draw[dotted] (2,0) -- (4,2);
```

## Узлы и метки

Узлы позволяют легко добавлять любые текстовые аннотации:

```tex
   \draw (0,0) -- (1,1) 
```

Вы можете точно позиционировать надписи относительно графических элементов, что повышает читаемость.

## Контуры и кривые

Контуры TikZ могут быть прямыми или кривыми. Кривые создаются с помощью простого синтаксиса:

```tex
   \draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Контрольные точки интуитивно задают кривизну.

## Группировка элементов

Группировка графических элементов упрощает преобразования (например, масштабирование и поворот):

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Элементы в области действия поворачиваются и масштабируются вместе, сохраняя выравнивание.

---

Освоение этих фундаментальных концепций и команд TikZ заложит прочную основу для создания сложной графики для ваших документов.

## Программная обработка рисунков TikZ с помощью Aspose.TeX

Ниже представлено подробное руководство и пример кода, демонстрирующие, как разработчики могут скомпилировать `.tex`-документ, содержащий рисунки TikZ, непосредственно в высококачественный векторный формат (PDF) в рамках управляемого .NET-приложения.

```csharp
using System;
using System.IO;
using Aspose.TeX;
using Aspose.TeX.Configuration;
using Aspose.TeX.Presentation.Pdf;
using Aspose.TeX.IO;

namespace AsposeTexTikzDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Определение входных и выходных каталогов с использованием абстракций ввода-вывода Aspose.TeX
            string dataDir = @"C:\DocumentSamples\TikzInput";
            string outputDir = @"C:\DocumentSamples\TikzOutput";

            // Проверка наличия выходного каталога
            Directory.CreateDirectory(outputDir);
            Directory.CreateDirectory(outputDir);

            // Инициализация параметров TeX для стандартной обработки LaTeX-документа
            // TeXConfig.LaTeX настраивает движок с использованием стандартных встроенных пакетов (включая tikz/pgf)
            TeXOptions options = TeXOptions.ConsoleAppRunSettings(TeXConfig.LaTeX, dataDir, outputDir);

            // Указание имени основного входного файла, содержащего среду TikZ
            options.JobName = "tikz-fundamentals";

            // Настройка параметров сохранения для вывода документа непосредственно в формате PDF
            options.SaveOptions = new PdfSaveOptions();

            // Создание и выполнение задачи TeXJob, связывающей исходный файл, устройство вывода и параметры
            try
            {
                Console.WriteLine("Starting TikZ compilation job...");
                
                new TeXJob(
                    Path.Combine(dataDir, "tikz-fundamentals.tex"), 
                    new PdfDevice(), 
                    options
                ).Run();

                Console.WriteLine($"TikZ graphic successfully compiled to PDF at: {outputDir}");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Compilation failed: {ex.Message}");
            }
        }
    }
}
```

**Кроме того, ознакомьтесь с нашим бесплатным [веб-приложением](https://products.aspose.app/tex/conversion/latex/) на основе [API Aspose.TeX для .NET](https://products.aspose.com/tex/net/) для быстрого и простого преобразования TeX.**
