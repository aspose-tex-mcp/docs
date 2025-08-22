---
translation: true
template: /templates/_template-net.md
title: Instalación y configuración básica | Aspose.TeX .NET
linktitle: Instalación y configuración
weight: 18
url: /net/tikz-installation-and-basic-configuration/
keywords: instalar TikZ, configurar TikZ, configurar TikZ
description: Guía paso a paso para instalar y configurar TikZ en tus documentos TeX y LaTeX.
lastmod: "2025-06-29"
---

{{<section overview>}}

Este capítulo cubre la instalación y configuración básica de la extensión TikZ para TeX y LaTeX. Le proporcionaremos instrucciones claras, paso a paso, para ayudarle a comenzar rápidamente a crear gráficos con TikZ.

## Instalación de TikZ

TikZ viene preinstalado con distribuciones populares de TeX, como **TeX Live** y **MiKTeX**. Si usa estas distribuciones, probablemente ya tenga TikZ instalado. De lo contrario, siga estas instrucciones:

### Usuarios de TeX Live

1. Abra el Gestor de TeX Live (`tlmgr`).
2. Actualice la lista de paquetes:

   ```bash
   tlmgr update --self --all
   ```

3. Instalar TikZ (parte del paquete `pgf`):

   ```bash
   tlmgr install pgf
   ```

### Usuarios de MiKTeX

1. Abra la consola de MiKTeX.
2. Vaya a la pestaña **Paquetes**.
3. Escriba `pgf` en la barra de búsqueda.
4. Seleccione e instale el paquete `pgf` si aún no está instalado.

## Verificación de la instalación

Puede verificar la instalación correcta de TikZ con este sencillo documento de prueba:

```tex
\documentclass{article}
\usepackage{tikz}

\begin{document}

Probando TikZ:

\begin{tikzpicture}
  \draw (0,0) rectangle (2,1);
\end{tikzpicture}

\end{document}
```

Compila este documento con `pdflatex` o cualquier editor compatible con LaTeX (como TeXworks u Overleaf). Deberías ver un pequeño rectángulo en el PDF resultante.

## Configuración básica de TikZ

TikZ requiere una configuración mínima. Sin embargo, puedes configurar opciones globales para controlar el comportamiento de los gráficos:

- **Escala de gráficos globalmente**:

  ```tex
  \tikzset{every picture/.style={scale=1.5}}
  ```

- **Establecer colores y estilos de línea predeterminados**:

  ```tex
  \tikzset{
    every path/.style={thick, blue},
    every node/.style={font=\small}
  }
  ```

Incluye estos comandos en el preámbulo de tu documento para aplicar un estilo consistente.

## Editores recomendados para TikZ

Para una edición cómoda y una compilación en tiempo real, recomendamos los siguientes editores de LaTeX:

- **TeXstudio**: editor gratuito y completo con vista previa integrada de TikZ.
- **Overleaf**: editor colaborativo en la nube con excelente compatibilidad con TikZ.
- **Visual Studio Code** con la extensión **LaTeX Workshop**: editor moderno y ligero compatible con TikZ.

Elige un editor según tus preferencias y requisitos de flujo de trabajo.

---

Siguiendo estas instrucciones, habrás configurado TikZ correctamente y estarás listo para crear gráficos impresionantes para tus documentos TeX y LaTeX.

**Además, explora nuestra [aplicación web](https://products.aspose.app/tex/conversion/latex/) gratuita basada en [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/) para realizar conversiones de TeX rápidas y sencillas.**