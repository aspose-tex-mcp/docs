---
translation: true
title: HTML Button Generator - online plugin and C# code
template: /templates/_template-generators-child.md
description: HTML Button Generator creates HTML button and C# code for this element. You can generate code and use it in your own website or C# project.
url: /net/generators/button/
platformtag: net
family: html
generator: HTML Button Generator
element: HTML button
tag: button
---

{{<section banner>}}
---
h1: HTML Button Generator
h2: Generate HTML and C# code for an HTML button element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Button on the fly!
---

The `<button>` [HTML](https://html.spec.whatwg.org/multipage/form-elements.html#the-button-element) element is an interactive element that defines a clickable button. You can activate the HTML button using the mouse,  keyboard, voice command, or other assistive technology. The `<button>` is a type of form element that is used to submit, reset a [form](https://html.spec.whatwg.org/multipage/forms.html#the-form-element) or open a dialog box. Once activated, it performs a programmable action. 

{{<section plugin>}}

{{<app/generator name="button" >}}

<br>
<h2> Attributes </h2>

The `<button>` element's attributes include: *name*, *type*, *value*, *autofocus*, *form*, *disabled*, *formaction*, etc. But all of these attributes are optional. However, you should always specify the *type* attribute for a `<button>` element, to tell browsers what type of button it is, as different browsers use different default *type* for the button element.
Inside a `<button>` tag you can put text and add icons to your button to make it unique.
<br><br>

<h2> Create HTML Button in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a `<button>` element, see the C# code example below. You can create a button with a few lines of C# code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Button in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLButtonElement.](https://reference.aspose.com/html/net/aspose.html/htmlbuttonelement/) It creates the HTML element specified by tagName, or an HTMLUnknownElement if tagName isn’t recognized.
2. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlbuttonelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlbuttonelement/name/), [TextContent](https://reference.aspose.com/html/net/aspose.html.dom/element/textcontent/) and [Disabled](https://reference.aspose.com/html/net/aspose.html/htmlbuttonelement/disabled/) attributes.
3. Copy C# code for the HTML button and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---