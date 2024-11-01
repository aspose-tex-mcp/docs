---
translation: true
template: /templates/_template-net.md
title: Convertidor de línea de comando TeX | Herramientas CLI de Aspose.TeX
linktitle: Convertir Aspose.TeX
weight: 80
url: /net/cli-tools/tex-convert/
description: Potente herramienta de conversión de línea de comandos de Aspose.TeX para convertir TeX/LaTeX de manera fácil y eficiente. Convertidor Aspose CLI TeX.
keywords: convertidor cli de tex a pdf, convertidor cli de látex a pdf, convertidor cli tex
lastmod: "2024-10-30"
---

{{<section overview>}}

## Descripción general

La herramienta [Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) es una potente aplicación CLI que facilita la conversión de documentos TeX y LaTeX a varios formatos. Esta herramienta permite a los desarrolladores y diseñadores crear documentos que funcionan perfectamente en diferentes plataformas y dispositivos.

## Características clave

- **Formatos de entrada admitidos**: TeX, LaTeX.
- **Formatos de salida admitidos**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Uso flexible**: se puede utilizar mediante comandos simples de línea de comandos y mediante programación en su código C#, compatible con .NET 6.0/7.0.

## Beneficios

El uso de la herramienta Aspose.TeX Convert proporciona varias ventajas:

- **Eficiencia**: convierta rápidamente documentos TeX/LaTeX a múltiples formatos sin la necesidad de software complejo.
- **Automatización**: integre la conversión de documentos en sus flujos de trabajo y scripts automatizados.
- **Flexibilidad**: Maneje varios formatos de documentos para garantizar la compatibilidad con diferentes sistemas y aplicaciones.

## Licencias

Si bien la aplicación Aspose.TeX Convert en sí es de uso gratuito, la conversión de documentos requiere una [licencia] Aspose.TeX válida (2). Puede comprar una licencia o utilizar Aspose.TeX en modo de prueba con fines de evaluación.

## ¿Cómo instalar TeX Command-Line Converter?

La herramienta Aspose.TeX Convert se puede instalar global o localmente, según las necesidades de su proyecto. Se recomienda utilizar la instalación local para uso específico del proyecto para evitar conflictos de versiones.

### Instalación global

Para instalar Aspose.TeX Convert globalmente en su máquina, use el siguiente comando:

```bash
dotnet tool install --global Aspose.TeX.Convert
```

Especifique la opción `--version` si necesita una versión específica de la herramienta.

### Instalación local

Para la instalación local dentro de un proyecto específico, primero navegue hasta el directorio raíz de su proyecto. Luego, ejecute los siguientes comandos:

1. Cree un manifiesto de herramienta si aún no está presente:

   ```bash
   manifiesto de nueva herramienta dotnet
   ```

2. Instale Aspose.TeX Convert localmente:

   ```bash
   Instalación de la herramienta dotnet Aspose.TeX.Convert --local
   ```

Nuevamente, puede especificar la opción `--version` para una versión específica.

### Actualización del convertidor TeX CLI

Para actualizar la herramienta Aspose.TeX Convert a la última versión, use el comando `dotnet tool update` con `--global` o `--local`, que coincida con su tipo de instalación.

### Desinstalación del convertidor TeX CLI

Si necesita desinstalar la herramienta, use el comando `dotnet tool uninstall` con `--global` o `--local`, dependiendo de cómo se instaló la herramienta.

## Uso

### Línea de comando

Convierta sus documentos usando argumentos de línea de comandos. Aquí están los parámetros disponibles:

- `-i, --input [Obligatorio]`: Ruta al documento TeX o LaTeX de entrada.
  - Ejemplo: `--input input.tex`
- `-o, --output [Obligatorio]`: Ruta del documento convertido.
  - Ejemplo: `--salida salida.pdf`
- `-f, --format [Opcional]`: formato del documento de salida.
  - Formatos admitidos: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Ejemplo: `--formato pdf`
- `-l, --license [Opcional]`: Ruta al archivo de licencia Aspose.TeX .NET.
  - Ejemplo: `--license ruta_a_licencia.lic`
- `-v, --verbose [Opcional]`: habilita la salida detallada.
  - Ejemplo: `--detallado`

Ejemplo de uso de la línea de comandos:


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### ¿Cómo integrar CLI LaTeX Converter en proyectos C#?

La aplicación Aspose.TeX Convert también se puede integrar directamente en sus proyectos .NET usando la línea de comando, lo que permite el acceso programático a las capacidades de conversión TeX dentro de su código C#.

**Agregar el convertidor de línea de comandos LaTeX a su proyecto:**

Para agregar la herramienta Aspose.TeX Convert a su proyecto de Visual Studio, vaya al directorio raíz de su proyecto y ejecute el siguiente comando:


```bash
dotnet Aspose.TeX.Convert add
```

Este comando agrega la funcionalidad Aspose.TeX Convert directamente a su proyecto, permitiéndole usar los métodos y propiedades de la biblioteca a través de su código. Esto es particularmente útil para los desarrolladores que buscan implementar procesos de conversión TeX personalizados directamente dentro de sus aplicaciones.

### Usar desde el código

A continuación se muestra un ejemplo del uso de las herramientas CLI de Aspose.TeX mediante programación en su código C#:


```csharp
using Aspose.TeX.MicroApps.Convert;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        // Initialize convert options
        var options = new ConvertOptions
        {
            // Required: Specify the input document path
            InputDocument = "input.tex",
            
            // Required: Specify the output document path
            OutputFilePath = "output.pdf",
            
            // Optional: Specify the output format
            ToFormat = "pdf"
        };

        // Conditional: Apply license if you have one
        if (isLicensed)
        {
            options.LicenseFile = "path_to_license.lic";
        }

        // Execute the conversion task
        await ConvertTasks.Create(options).Execute();
    }
}
```

Para obtener más información y ejemplos de uso, visite la [documentación de Aspose.TeX para .NET](/tex/{{lang.url-fragment}}net/).