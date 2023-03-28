---
translation: true
title: HTML Color Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML color input, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/color/
platformtag: net
family: html
generator: HTML Color Input Generator
tag: color
element: HTML color input
---

{{<section banner>}}
---
h1: HTML Color Input Generator
h2:  Generate HTML and C# code for an HTML Color Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Color Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type="color"` defines a color picker. It provides a user interface element that allows a user to specify a color, either through a visual color picker interface or by typing the color into a text field in hexadecimal format #RRGGBB. HTML Color Input Code Generator helps to generate HTML input color code that can be inserted into HTML.<br>
The control consists of a small button inside which the current color is displayed. Clic the color button to open the color picker with an initial value. A preview of the selected color is displayed inside the control.

{{<section plugin>}}

{{<app/generator name="color" >}}
<br>
<h2> Attributes </h2>

An initial color can be specified with the `value` attribute which accepts hex color values. Only simple colors without alpha channel are allowed to use. The `value` must be in seven-character hexadecimal notation. The `value` is never empty. If you don't specify a value, the default is #000000, which means black.

You can generate an HTML color input tag and color picker C# code by selecting attributes such as `name` and `value`. <br><br>

<h2> Create HTML Color Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a color picker, see the C# code example below:
{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create Color Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `value` attribute and its value in hexadecimal format.
1. Copy C# code for the HTML color input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---