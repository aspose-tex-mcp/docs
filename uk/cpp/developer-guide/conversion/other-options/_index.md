---
translation: true
template: /templates/_template-cpp.md
title: Інші параметри керування TeX | C++
linktitle: Інші варіанти
weight: 17
url: /cpp/other-options/
description: Функція перетворення рішення Aspose.TeX API для C++ дозволяє встановити початковий режим взаємодії, у якому запускається двигун. Ось кілька прикладів коду.
lastmod: 2024-09-20
---

{{<section overview>}}

## Як встановити режим взаємодії

Як ми згадували [тут](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX для C++** дозволяє встановити початковий режим взаємодії, у якому запускається механізм. Ось як ми це робимо:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Як встановити назву роботи

Коли ми передаємо основний вхідний файл як ім’я файлу, ми отримуємо вихідні файли з такою ж назвою, але з іншими розширеннями. Механізм TeX називає ім'я вхідного файлу *ім'ям завдання* і використовує його для вихідних файлів, за винятком випадків, коли записуються допоміжні файли з явно вказаними іншими іменами. Коли ми передаємо основний вхідний файл як [stream](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), механізм TeX використовує назву завдання за замовчуванням, яка є *texput*.
В обох випадках ми можемо змінити назву завдання, призначивши відповідний параметр перетворення.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## Як повторити роботу

Як ми вже згадували [вище](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) щодо міток і посилань, бувають випадки, коли ми хотіли б виконати ту саму роботу двічі. Ось як це можна зробити:
```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```