---
translation: true
title: HTML Checkbox Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Checkbox Generator lets you create HTML checkboxes for your website. You can preview the checkbox and copy generated HTML and C# code.
url: /net/generators/checkbox/
platformtag: net
family: html
generator: HTML Checkbox Generator
element: checkbox
tag: checkbox
---

{{<section banner>}}
---
h1: HTML Checkbox Generator
h2: Generate HTML and C# code for an HTML checkbox element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Checkbox on the fly!
---

The [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type="checkbox"` defines a checkbox. The checkbox is an input field representing a binary choice. The exact appearance of the checkbox depends on the operating system configuration on which the browser is running. It is usually square but may have rounded corners. This is a form element that allows users to select one or more options from the given options.<br> HTML Checkbox Generator lets you create checkbox elements for your website. You can preview the checkbox and copy or download the generated HTML code.

{{<section plugin>}}

{{<app/generator name="checkbox" >}}

<br>
<h2> Attributes </h2>

The checkbox usually contains a `name` and `value` attributes. This name/value pair will be sent to the server when the form is submitted. If the `value` attribute is not specified, then the reported default value is "on".<br>
You can generate an HTML checkbox input tag and checkbox C# code by selecting attributes such as `name`, `checked`, `id`, etc. Each checkbox is associated with a `<label>` element wrapped around the checkbox. Please always include a `<label>` tag for better accessibility!<br><br>

<h2> Create HTML Checkbox in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a checkbox, see the C# code example below. You can create a checkbox with a few lines of C# code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Checkbox in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/), [Id](https://reference.aspose.com/html/net/aspose.html/htmlelement/id/) and [Checked](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/checked/) attributes.
1. Create the [HTMLLabelElement](https://reference.aspose.com/html/net/aspose.html/htmllabelelement/) and set required attributes.
1. Copy C# code for the HTML checkbox and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---