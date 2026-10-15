---
translation: true
template: /templates/_template-java.md
title: Другие пути предоставления входного файла TeX | Java
linktitle: Другие способы предоставления основного входного файла TeX
weight: 14
url: /java/other-ways-of-main-input/
description: Функциональность преобразования решения Aspose.TeX API для Java имеет конструктор, который принимает поток в качестве первого аргумента.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Предоставление основного входного файла движку TeX в виде потока.

До этого момента мы знали только, как передать [основной входной файл](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) в движок TeX как имя файла, полностью заданное или в краткой форме, с расширением или без него. Но есть еще один [конструктор](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) класса TeXJob, который принимает поток в качестве первого аргумента. Это удобно, если по каким-то причинам основной входной файл у нас имеет форму, отличную от файла файловой системы диска. Вот как мы можем с этим справиться:

Укажите в `outputDirectory` существующую папку вывода. Импортируйте классы Aspose.TeX из примеров, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions`, а для ввода из потока — `java.io.ByteArrayInputStream` и `java.nio.charset.StandardCharsets`. Вызывающий метод должен обрабатывать или объявлять исключения. Примените лицензию согласно [руководству по лицензированию](/tex/{{lang.url-fragment}}java/licensing/), чтобы избежать ограничений ознакомительной версии. Пример потока содержит полный документ LaTeX, поэтому рабочая папка ввода не нужна. Потоки и устройства остаются открытыми до завершения задания, затем закрываются или освобождаются.

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-StreamInput-LaTeX.java" >}}

Если при вводе из потока имя задания не задано явно, движок использует имя по умолчанию *texput*. Этот пример создаёт `texput.xps` и `texput.log`. Для выбора другого имени задания используйте `options.setJobName(...)`. Подробности об именах заданий см. [здесь](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) и [здесь](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name).

## Ввод основного входного файла TeX из терминала

Есть еще один [конструктор](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  класса TeXJob, который вообще не позволяет нам указывать входные данные. Вы можете задаться вопросом, что же будет обрабатывать такое задание TeX? На этот раз нам понадобится входной терминал. Движок TeX попросит нас ввести имя файла из терминала.

Укажите в `inputDirectory` папку с полным документом LaTeX под именем `hello-world.ltx`, а в `outputDirectory` — существующую папку вывода. Запустите пример в консоли, введите `hello-world.ltx` в ответ на приглашение `**` и нажмите Enter. Он создаёт `hello-world.xps` и записывает вывод терминала в консоль. Оба примера используют `NonstopMode` для обработки, но терминальному конструктору всё равно нужно начальное имя файла. Для запуска без участия пользователя предоставьте реализацию `IInputTerminal` либо используйте ввод из файла или потока.

Вот код:

{{< gist "aspose-com-gists" "889663554934c807ebc90e12d08bc8d0" "Example-MainInputTerminal.java" >}}

Как только он запускается, движок зависает, ожидая, пока мы введем имя файла (с путем или без него, с расширением или без него):


![Окно терминала](/tex/images/java/Conversion-MainInputTerminal.png)

А вот как это будет выглядеть на выходном терминале, который является консолью:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```