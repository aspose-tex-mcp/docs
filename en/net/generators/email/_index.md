---
translation: true
title: HTML Email Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML email input, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/email/
platformtag: net
family: html
generator: HTML Email Input Generator
element: HTML email input
tag: email
---

{{<section banner>}}
---
h1: HTML Email Input Generator
h2: Generate HTML and C# code for an HTML Email Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Easily generate HTML Email Input!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type='email'` is used to allow the user to enter and edit an email address or a list of email addresses. The input value is automatically validated to ensure that it is a properly-formatted email address.

{{<section plugin>}}

{{<app/generator name="email" >}}

HTML Email Input Generator helps to generate HTML code for the input tag with `type='email'` by selecting attributes like `name`, `placeholder`, `size`, `multiple`, `required`, and `pattern`. 
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field.
- The `size` attribute is a numeric value indicating how many characters wide should be in the input field. The default value is 20.
- The `multiple` boolean attribute specifies that the user can enter multiple email addresses separated by commas.
- The `pattern` attribute is a regular expression that the input value must match in order for the value to pass the constraint validation. If the specified pattern is not specified or is invalid, the regular expression is not applied and this attribute is completely ignored.
<br>

<h2> Create HTML Email Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an HTML email input, see the C# code example below. You can create the desired element with a few lines of C# code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Email Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) and [Size](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/size/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `multiple`, `required`, and `pattern` attributes.
1. Copy C# code for the HTML email input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. Clear, safe and simple!"
---