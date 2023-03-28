---
translation: true
title: HTML Submit Input Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: Сreate HTML Submit Input for your website. Рreview the submit button, copy and use generated HTML and C# code in your project!
url: /net/generators/submit/
platformtag: net
family: html
generator: HTML Submit Input Generator
element: HTML submit input
tag: submit
---

{{<section banner>}}
---
h1: HTML Submit Input Generator
h2: Generate HTML and C# code for an HTML submit input element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Submit Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type='submit'` is rendered as a submit button which submits the form to the server. When the user clicked the button, the user agent attempts to submit the form to the server. HTML Submit Input Generator helps you to generate code which can be pasted into HTML. Just select options and generate the submit button on the fly!

{{<section plugin>}}

{{<app/generator name="submit" >}}

<br>
<h2> Attributes </h2>

A `value` attribute contains a string that is displayed as the label of the button. Otherwise, if you don't specify a value, the button will have a default label chosen by the user agent. If you want to disable the submit button, set the `disabled` attribute to it.<br><br>

<h2> Create HTML Submit Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your product or programmatically add a submit button, see the C# code example below. You can create a submit input tag with a few lines:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Submit Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1.  Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `value`, `disabled`, or other supported attributes with their values.
1. Copy C# code for the submit button and use it in your project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Code Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---