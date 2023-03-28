---
translation: true
title: HTML Search Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML search input, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/search/
platformtag: net
family: html
generator: HTML Search Input Generator
element: HTML search input
tag: search
---

{{<section banner>}}
---
h1: HTML Search Input Generator
h2: Generate HTML and C# code for an HTML Search Input element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Search Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type='search'` defines a text field designed for the user to enter search queries into. Search boxes are ubiquitous on every website. This is useful for finding specific data. HTML Search Input Generator helps you to generate code which can be pasted into HTML. Just select options and generate the search box on the fly!

{{<section plugin>}}

{{<app/generator name="search" >}}

<br>
<h2> Attributes </h2>

- The `name` attribute is required. If no name is given for the search field, nothing will be submitted.
- The `size` attribute is a numeric value indicating how many characters can be in the input field.
- The `spellcheck` is an attribute that is used to indicate whether to enable spell-checking for an element.
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field.<br><br>

<h2> Create HTML Search Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a search input tag, see the example below. You can create a search input element with a few lines of C# code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Search Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `size`, `spellcheck` and `placeholder` attributes with their values.
1. Copy code for the HTML Search Input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---