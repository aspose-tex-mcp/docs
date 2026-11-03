---
translation: true
template: /templates/_template-net.md
title: Перетворювачі Aspose.TeX для .NET – поширені запитання
linktitle: FAQ
type: docs
weight: 90
url: /net/conversion/faq/
description: Поширені запитання про перетворення файлів TeX і LaTeX за допомогою Aspose.TeX для .NET, зокрема про підтримувані формати, код перетворення, виведення в потік, параметри зображень, пакети, ознайомлювальний режим і вимоги до середовища виконання.
keywords: Aspose.TeX, .NET, FAQ, перетворення LaTeX, LaTeX у PDF, LaTeX у XPS, LaTeX у SVG, LaTeX у PNG, TeXJob, ліцензування, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**З: Які вхідні та вихідні формати підтримує Aspose.TeX для .NET?**

**В:** Aspose.TeX верстає документи TeX і LaTeX. Основний вхідний файл можна передати як файл, потік або через термінал; файли, які він підключає, можна брати з папки або ZIP-архіву. Окремі API відмальовують одну математичну формулу LaTeX або фрагмент LaTeX. Вихідні формати — PDF, XPS, SVG, PNG, JPEG, BMP і TIFF. Див. [Підтримувані формати файлів](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**З: Чи може Aspose.TeX перетворити LaTeX у Word (DOCX) або HTML?**

**В:** Ні. Aspose.TeX створює лише PDF, XPS, SVG і растрові зображення. Якщо потрібен інший формат, перетворіть отриманий PDF за допомогою бібліотеки, яка його підтримує.
<br><br>

**З: Як перетворити файл LaTeX у PDF на C#?**

**В:** Створіть `TeXOptions` для формату ObjectLaTeX, вкажіть вихідний каталог і `PdfSaveOptions` та запустіть `TeXJob` з `PdfDevice`:

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Результат записується у вихідний робочий каталог під назвою завдання. Див. [LaTeX у PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**З: Як вибрати вихідний формат?**

**В:** Задайте `TeXOptions.SaveOptions` і передайте в `TeXJob` відповідний пристрій:

| Формат | Параметри збереження | Пристрій |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

Див. [LaTeX до XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) і [LaTeX до зображення](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**З: Чи можна отримати результат у пам'яті, а не у файлі?**

**В:** Так. `PdfDevice` і `XpsDevice` мають конструктори, що приймають `Stream`, у який записується документ. `ImageDevice` зберігає відмальовані сторінки у властивості `Result` у вигляді масиву масивів байтів, по одному на сторінку. Щоб прочитати основний вхідний файл із потоку, передайте потік у конструктор `TeXJob`. Див. [LaTeX у PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) і [Інші способи надання основного вхідного файлу TeX](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**З: Як керувати роздільною здатністю та якістю зображень?**

**В:** Використовуйте властивості параметрів збереження зображень:

- `Resolution` — роздільна здатність зображення в DPI.
- `SmoothingMode` і `InterpolationMode` — якість відмальовування.
- `TiffSaveOptions.Compression` і `TiffSaveOptions.Multipage` — стиснення TIFF і збереження всіх сторінок в один файл (багатосторінковий TIFF поки що не підтримується пакетом `Aspose.TeX.Drawing`).

Наприклад, `new PngSaveOptions { Resolution = 300 }` створює зображення PNG з роздільною здатністю 300 DPI. Див. [LaTeX до зображення](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**З: Як дізнатися, чи успішно пройшло перетворення?**

**В:** `TeXJob.Run()` повертає значення `TeXJobResult`: `Spotless`, `WarningIssued`, `ErrorMessageIssued` або `FatalErrorStop`. Подробиці записуються у файл протоколу (`.log`) у вихідному каталозі та у вихідний термінал. Див. [Інтерфейс виведення Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**З: Чи потрібне на сервері встановлення LaTeX (наприклад, MiKTeX)?**

**В:** Ні. Aspose.TeX — самостійна бібліотека .NET з власним рушієм TeX, форматом LaTeX і шрифтами. Зовнішній дистрибутив TeX їй не потрібен.
<br><br>

**З: Які пакети LaTeX можна використовувати?**

**В:** Aspose.TeX містить набір вбудованих пакетів LaTeX, див. [Вбудовані пакети LaTeX](/tex/{{lang.url-fragment}}net/embedded-packages/). Щоб використовувати інші пакети, помістіть їхні файли в папку або ZIP-архів і вкажіть його в `TeXOptions.RequiredInputDirectory`, див. [Зовнішні пакети LaTeX](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**З: Чи можна відмалювати окрему формулу або фрагмент LaTeX замість цілого документа?**

**В:** Так. Для математичних формул використовуйте `PngMathRenderer` або `SvgMathRenderer`, для довільних фрагментів LaTeX — `PngFigureRenderer` або `SvgFigureRenderer`. Вони повертають розмір отриманого зображення. Див. [Відтворення математичних формул LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) і [Відтворення рисунків LaTeX](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**З: Які вимоги до середовища виконання?**

**В:**

- Пакет `Aspose.TeX`: Windows (x64/x86); .NET Framework 4.0 або новіший, .NET Standard 2.0, .NET 6 або новіший.
- Пакет `Aspose.TeX.Drawing`: Windows, Linux і macOS (x64/Arm64); .NET Framework 4.7.2 або новіший, .NET 7 або новіший.
- Додаткові нативні бібліотеки не потрібні. У Linux для виведення в XPS і SVG потрібна ICU. Див. [Системні вимоги](/tex/{{lang.url-fragment}}net/system-requirements/) і [Linux, macOS і Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**З: Які обмеження ознайомлювальної версії?**

**В:** Без ліцензії Aspose.TeX працює в ознайомлювальному режимі: виводить не більше чотирьох сторінок документа, і на сторінках є водяний знак ознайомлювальної версії. Ознайомлювальна версія — це той самий пакет; щоб оцінити продукт без обмежень, запросіть [30-денну тимчасову ліцензію](https://purchase.aspose.com/temporary-license/). Див. [Ліцензування](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**З: Як застосувати ліцензію в коді?**

**В:** Застосуйте ліцензію один раз, до першого перетворення:

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

Ліцензію також можна завантажити з потоку або використати лімітну (metered) ліцензію. Див. [Ліцензування](/tex/{{lang.url-fragment}}net/licensing/). Ціни наведено на [сторінці цін Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**З: Де знайти документацію з API, приклади та підтримку?**

**В:**

- [Посібник розробника](https://docs.aspose.com/tex/net/)
- [Довідник з API](https://reference.aspose.com/tex/net/)
- [Форум спільноти](https://forum.aspose.com/c/tex/)
<br><br>
