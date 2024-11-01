---
translation: true
template: /templates/_template-cpp.md
title: Другие параметры управления TeX | С++
linktitle: Другие варианты
weight: 17
url: /cpp/other-options/
description: Функциональность преобразования решения Aspose.TeX API для C++ позволяет установить начальный режим взаимодействия, в котором запускается движок.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Как установить режим взаимодействия

Как мы упоминали [здесь](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX для C++** позволяет нам установить начальный режим взаимодействия, в котором запускается движок. Вот как мы это делаем:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Как задать имя задания

Когда мы передаем основной входной файл в качестве имени файла, мы получаем выходные файлы с тем же именем, но с другими расширениями. Движок TeX называет имя входного файла *имя задания* и использует его для выходных файлов, за исключением случаев, когда записываются вспомогательные файлы с явно указанными другими именами. Когда мы передаем основной входной файл как [поток](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), движок TeX использует имя задания по умолчанию — *texput*.
В обоих случаях мы можем переопределить имя задания, назначив соответствующий параметр преобразования.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## Как повторить работу

Как мы уже упоминали [выше](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) относительно меток и ссылок, бывают случаи, когда нам нужно запустить одно и то же задание дважды. Вот как это можно сделать:

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```