---
translation: true
template: /templates/_template-cpp.md
title: Otras opciones de gestión de TeX | C++
linktitle: Otras opciones
weight: 17
url: /cpp/other-options/
description: La funcionalidad de conversión de la solución API Aspose.TeX para C++ permite establecer el modo de interacción inicial en el que se inicia el motor.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Cómo configurar el modo de interacción

Como mencionamos [aquí](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX para C++** nos permite configurar el modo de interacción inicial en el que arranca el motor. Así es como lo hacemos:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Cómo configurar el nombre del trabajo

Cuando pasamos el archivo de entrada principal como nombre de archivo, obtenemos archivos de salida con el mismo nombre, aunque con otras extensiones. El motor TeX llama al nombre del archivo de entrada *nombre del trabajo* y lo utiliza para los archivos de salida, excepto en los casos en que se escriben archivos auxiliares con otros nombres especificados explícitamente. Cuando pasamos el archivo de entrada principal como [flujo](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), el motor TeX usa el nombre de trabajo predeterminado, que es *texput*.
En ambos casos, podemos anular el nombre del trabajo asignando la opción de conversión adecuada.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```

## Cómo repetir el trabajo

Como mencionamos [arriba](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) con respecto a las etiquetas y referencias, hay casos en los que nos gustaría ejecutar el mismo trabajo dos veces. Así es como se puede hacer:

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```