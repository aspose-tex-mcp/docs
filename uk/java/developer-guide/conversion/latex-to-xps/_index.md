---
translation: true
template: /templates/_template-java.md
title: LaTeX до XPS | Java
linktitle: LaTeX до XPS
weight: 12
url: /java/latex-to-xps/
description: Функція перетворення рішення Aspose.TeX API для Java дозволяє конвертувати файли LaTeX у формат XPS. Вивчіть приклади коду.
lastmod: "2026-04-21"
---

{{<section overview>}}


Іншим цільовим форматом є [**XPS**](https://en.wikipedia.org/wiki/Open_XML_Paper_Specification). Файл **XPS** фізично є ZIP-пакетом, який містить розбитий на сторінки вміст документа, а також метадані, необхідні для належного відображення певними засобами перегляду (наприклад, Windows XPS Viewer) і друку. Усі дані в пакеті організовано як файли в каталогах. Деякі з них містять такі ресурси, як зображення, шрифти та профілі ICC. Інші — це XML-файли в різних конкретних схемах. До останніх відносяться файли, що містять самі дані документа. Дані документа — це набір файлів — кожен файл містить дані для окремої сторінки документа. Такі файли складаються з одного елемента сторінки та дерева дочірніх елементів - *Canvas*, *Path* і *Glyphs*. *Canvas* — це груповий елемент, який може містити інші *Canvases*, *Paths* і *Glyphs*. Його призначення — контролювати вигляд усіх дочірніх елементів як групи. Елементи *Path* використовуються для визначення шляхів векторної графіки. А елементи *Glyphs* використовуються для визначення текстового вмісту. Усі три елементи мають властивості для визначення різних аспектів зовнішнього вигляду.

Існує бібліотека [**Aspose.Page**](https://products.aspose.com/page/), яка надає API для роботи з документами XPS, а також для їх перетворення у формати PDF і растрових зображень.

## Як конвертувати LaTeX у XPS

Перетворення в XPS таке ж просте, як і [перетворення у формати растрових зображень](/tex/{{lang.url-fragment}}java/latex-to-image/), за винятком того, що на додаток до [SaveOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getSaveOptions--) ми маємо використовувати екземпляр класу [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/) .

Задайте в `inputFile` повний шлях до файлу LaTeX, наприклад `hello-world.ltx`, а в `outputDirectory` — наявну папку виводу. Імпортуйте використані в прикладі класи з `com.aspose.tex` і `com.aspose.tex.rendering`. Метод, що викликає цей код, має обробляти або оголошувати винятки. Застосуйте ліцензію згідно з [посібником із ліцензування](/tex/{{lang.url-fragment}}java/licensing/), щоб уникнути обмежень ознайомлювальної версії. Приклад використовує неінтерактивний режим і закриває ресурси виводу. Для самодостатнього вхідного файлу `hello-world.ltx` вихідний файл за замовчуванням — `hello-world.xps`.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Simplest.java" >}}

### Альтернативний спосіб запису основного вихідного файлу XPS

Є ще один конструктор класу [XpsDevice](https://reference.aspose.com/tex/java/com.aspose.tex.rendering/xpsdevice/#XpsDevice-java.io.OutputStream-), який дозволяє нам отримати результуючий файл XPS альтернативним способом.

Використовуйте ті самі значення `inputFile` і `outputDirectory`, що й вище. Задайте `xpsFile` як `java.nio.file.Path`, наприклад `Paths.get(outputDirectory, "any-name.xps")`. Окрім класів Aspose.TeX, імпортуйте `java.io.OutputStream`, `java.nio.file.Files`, `java.nio.file.Path` і `java.nio.file.Paths`. Потік визначає шлях вихідного XPS-файлу; допоміжні файли й надалі записуються в `outputDirectory`.

{{< gist "aspose-com-gists" "a30f406f6b8ace1b7d15c68a1df75c6d" "Example-ConvertLaTeXToXPS-Alternative.java" >}}

Ефект такий самий, як ми отримуємо [тут](/tex/{{lang.url-fragment}}java/latex-to-pdf/#альтернативний-спосіб-запису-основного-вихідного-файлу-pdf).

**Ви також можете ознайомитися з безкоштовною [веб-програмою](https://products.aspose.app/tex/conversion/latex-to-xps) для перетворення LaTeX на XPS, створеною на основі API [Aspose.TeX для .NET](https://products.aspose.com/tex/net/). [Тут](https://products.aspose.com/tex/java/) – сторінка версії Java.**