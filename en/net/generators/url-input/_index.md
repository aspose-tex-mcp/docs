---
translation: true
title: HTML URL Input Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: Сreate HTML URL Input for your website. Рreview the URL Input, copy and use generated HTML and C# code in your project!
url: /net/generators/url-input/
platformtag: net
family: html
generator: HTML URL Input Generator
element: HTML URL input
tag: url-input
---

{{<section banner>}}
---
h1: HTML URL Input Generator
h2: Generate HTML and C# code for an HTML URL Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML URL Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) with `type='url'` defines a field for entering a URL. It only accepts null or a valid URL. This input value is automatically validated before the form is submitted. HTML URL Input Generator helps you to generate code which can be pasted into HTML. Just select options and generate the URL input on the fly!

{{<section plugin>}}

{{<app/generator name="url-input" >}}

<br>
<h2> Attributes </h2>

With the input `type='url'` element you can use attributes such as *name*, *id*, *size*, *pattern*, *placeholder*, *list*, *maxlength*, *minlength*, etc.
- The `size` attribute is a numeric value indicating how many characters can be in the input field. 
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field.
- The `pattern` attribute, if specified, is a regular expression that the input value must match in order for the value to pass validation. 
<br><br>

<h2> Create URL Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your C# product or programmatically add an HTML URL input, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create URL Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/)
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) and [Size](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/size/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `placeholder`, `pattern`, or other supported attributes with their values.
1. Copy code for the HTML URL input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With HTML Code Generators, all the hard work has already been done for you. All you have to do is copy and paste!"
---