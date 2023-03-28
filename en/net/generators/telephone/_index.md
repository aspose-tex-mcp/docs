---
translation: true
title: HTML Telephone Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Сreate HTML Telephone Input for your website. Рreview the Telephone Input, copy and use generated HTML and C# code in your project!
url: /net/generators/telephone/
platformtag: net
family: html
generator: HTML Telephone Input Generator
element: HTML telephone input
tag: telephone
---

{{<section banner>}}
---
h1: HTML Telephone Input Generator
h2: Generate HTML and C# code for an HTML Telephone Input element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Telephone Input on the fly!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type='tel'` is used to let the user enter and edit a telephone number. This input value is not automatically validated because telephone number formats vary widely around the world. Functionally, this is handy with mobile browsers because smartphones usually recognize the type of input and change the keyboard to display a numeric keypad. Note that browsers that don't support `type='tel'` fall back to standard text input.

{{<section plugin>}}

{{<app/generator name="telephone" >}}

<br>
<h2> Attributes </h2>

With the input `type='tel'` element you can use attributes such as *name*, *size*, *placeholder*, *list*, *maxlength*, *minlength*, etc.
- The `size` attribute is a numeric value indicating how many characters can be in the input field. 
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field.
<br><br>

<h2> Create HTML Telephone Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your product or programmatically add a telephone input, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Telephone Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/)
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/), and [Size](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/size/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `placeholder` or other supported attributes with their values.
1. Copy C# code for the HTML telephone input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Code Generators, all the hard work has already been done for you. All you have to do is copy and paste!"
---