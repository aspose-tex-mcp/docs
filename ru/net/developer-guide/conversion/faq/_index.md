---
translation: true
template: /templates/_template-net.md
title: Конвертеры Aspose.TeX для .NET – Часто задаваемые вопросы
linktitle: Часто задаваемые вопросы
type: docs
weight: 90
url: /net/conversion/faq/
description: Часто задаваемые вопросы о преобразовании файлов TeX и LaTeX с помощью Aspose.TeX для .NET, включая поддерживаемые форматы, код преобразования, вывод в поток, параметры изображений, пакеты, ознакомительный режим и требования к среде выполнения.
keywords: Aspose.TeX, .NET, FAQ, преобразование LaTeX, LaTeX в PDF, LaTeX в XPS, LaTeX в SVG, LaTeX в PNG, TeXJob, лицензирование, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**В: Какие входные и выходные форматы поддерживает Aspose.TeX для .NET?**

**О:** Aspose.TeX выполняет вёрстку документов TeX и LaTeX. Основной входной файл можно передать как файл, поток или через терминал; подключаемые им файлы можно брать из папки или ZIP-архива. Отдельные API отрисовывают одну математическую формулу LaTeX или фрагмент LaTeX. Выходные форматы — PDF, XPS, SVG, PNG, JPEG, BMP и TIFF. См. [Поддерживаемые форматы файлов](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**В: Может ли Aspose.TeX преобразовать LaTeX в Word (DOCX) или HTML?**

**О:** Нет. Aspose.TeX создаёт только PDF, XPS, SVG и растровые изображения. Если нужен другой формат, преобразуйте полученный PDF с помощью библиотеки, которая его поддерживает.
<br><br>

**В: Как преобразовать файл LaTeX в PDF на C#?**

**О:** Создайте `TeXOptions` для формата ObjectLaTeX, укажите выходной каталог и `PdfSaveOptions` и запустите `TeXJob` с `PdfDevice`:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Результат записывается в выходной рабочий каталог под именем задания. См. [LaTeX в PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**В: Как выбрать выходной формат?**

**О:** Задайте `TeXOptions.SaveOptions` и передайте в `TeXJob` соответствующее устройство:

| Формат | Параметры сохранения | Устройство |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

См. [LaTeX в XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) и [LaTeX в изображение](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**В: Можно ли получить результат в памяти, а не в файле?**

**О:** Да. У `PdfDevice` и `XpsDevice` есть конструкторы, принимающие `Stream`, в который записывается документ. `ImageDevice` хранит отрисованные страницы в свойстве `Result` в виде массива массивов байтов, по одному на страницу. Чтобы прочитать основной входной файл из потока, передайте поток в конструктор `TeXJob`. См. [LaTeX в PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) и [Другие способы предоставления основного входного файла TeX](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**В: Как управлять разрешением и качеством изображений?**

**О:** Используйте свойства параметров сохранения изображений:

- `Resolution` — разрешение изображения в DPI.
- `SmoothingMode` и `InterpolationMode` — качество отрисовки.
- `TiffSaveOptions.Compression` и `TiffSaveOptions.Multipage` — сжатие TIFF и сохранение всех страниц в один файл (многостраничный TIFF пока не поддерживается пакетом `Aspose.TeX.Drawing`).

Например, `new PngSaveOptions { Resolution = 300 }` создаёт изображения PNG с разрешением 300 DPI. См. [LaTeX в изображение](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**В: Как узнать, успешно ли прошло преобразование?**

**О:** `TeXJob.Run()` возвращает значение `TeXJobResult`: `Spotless`, `WarningIssued`, `ErrorMessageIssued` или `FatalErrorStop`. Подробности записываются в файл протокола (`.log`) в выходном каталоге и в выходной терминал. См. [Выходной интерфейс Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**В: Нужна ли на сервере установка LaTeX (например, MiKTeX)?**

**О:** Нет. Aspose.TeX — самостоятельная библиотека .NET с собственным движком TeX, форматом LaTeX и шрифтами. Внешний дистрибутив TeX ей не нужен.
<br><br>

**В: Какие пакеты LaTeX можно использовать?**

**О:** Aspose.TeX содержит набор встроенных пакетов LaTeX, см. [Встроенные пакеты LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Чтобы использовать другие пакеты, поместите их файлы в папку или ZIP-архив и укажите его в `TeXOptions.RequiredInputDirectory`, см. [Внешние пакеты LaTeX](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**В: Можно ли отрисовать отдельную формулу или фрагмент LaTeX вместо целого документа?**

**О:** Да. Для математических формул используйте `PngMathRenderer` или `SvgMathRenderer`, для произвольных фрагментов LaTeX — `PngFigureRenderer` или `SvgFigureRenderer`. Они возвращают размер полученного изображения. См. [Отрисовка математических формул LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) и [Отрисовка рисунков LaTeX](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**В: Каковы требования к среде выполнения?**

**О:**

- Пакет `Aspose.TeX`: Windows (x64/x86); .NET Framework 4.0 или новее, .NET Standard 2.0, .NET 6 или новее.
- Пакет `Aspose.TeX.Drawing`: Windows, Linux и macOS (x64/Arm64); .NET Framework 4.7.2 или новее, .NET 7 или новее.
- Дополнительные нативные библиотеки не нужны. В Linux для вывода в XPS и SVG нужна ICU. См. [Системные требования](/tex/{{lang.url-fragment}}net/system-requirements/) и [Linux, macOS и Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**В: Каковы ограничения ознакомительной версии?**

**О:** Без лицензии Aspose.TeX работает в ознакомительном режиме: выводит не более четырёх страниц документа, и на страницах стоит водяной знак ознакомительной версии. Ознакомительная версия — это тот же пакет; чтобы оценить продукт без ограничений, запросите [30-дневную временную лицензию](https://purchase.aspose.com/temporary-license/). См. [Лицензирование](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**В: Как применить лицензию в коде?**

**О:** Примените лицензию один раз, до первого преобразования:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

Лицензию можно также загрузить из потока или использовать лимитную (metered) лицензию. См. [Лицензирование](/tex/{{lang.url-fragment}}net/licensing/). Цены указаны на [странице цен Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**В: Где найти документацию по API, примеры и поддержку?**

**О:**

- [Руководство разработчика](https://docs.aspose.com/tex/net/)
- [Справочник по API](https://reference.aspose.com/tex/net/)
- [Форум сообщества](https://forum.aspose.com/c/tex/)
<br><br>
