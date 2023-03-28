---
translation: true
title: HTML Number Input Generator - Online tool and C# code
template: /templates/_template-generators-child.md
description: Сreate HTML Number Input for your website. Рreview the Number Input, copy and use generated HTML and C# code in your project!
url: /net/generators/number/
platformtag: net
family: html
generator: HTML Number Input Generator
element: HTML number input
tag: number
---

{{<section banner>}}
---
h1: HTML Number Input Generator
h2: Generate HTML and C# code for an HTML Number Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Number Input on the fly!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type="number"` defines a field for entering a number. It includes a built-in check for rejecting non-numeric entries. You can also set limits on accepted numbers. HTML Number Input Generator helps you to generate HTML number input code which can be pasted into HTML. Just select options and generate the number input box on the fly!

{{<section plugin>}}

{{<app/generator name="number" >}}

<br>
<h2> Attributes </h2>

The HTML number input usually contains a `name`, `value`, `min`, `max`, and `step` attributes. <br>
- With the `min` and `max` attributes you can set the minimum and maximum values.
- The `step` attribute is a number indicating the granularity. The default step value is 1.
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field. For example, "multiple of 2".<br><br>

<h2> Create Number Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your product or programmatically add a number input, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Number Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/)
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `value`, `min`, `max`, `placeholder` and `step` attributes with their values.
1. Copy C# code for the HTML number input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Code Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---