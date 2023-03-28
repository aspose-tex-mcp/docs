---
translation: true
title: HTML Radio Button Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML Radio Buttons for your website. You can preview the radio buttons and copy generated HTML and C# code.
url: /net/generators/radio/
platformtag: net
family: html
generator: HTML Radio Button Generator
element: HTML radio button
tag: radio
---

{{<section banner>}}
---
h1: HTML Radio Button Generator
h2: Generate HTML and C# code for an HTML Radio Button and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Radio Button on the fly!
---

The [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) type `radio` is used to create radio buttons. They are called radio buttons because they look and work the same as the buttons on old radios. Radio buttons are typically used to indicate a group item. Only one radio button in a group can be selected at the time. Radio buttons usually appear as small circles that fill or highlight when selected.
Checkboxes are similar to radio buttons, but radio buttons are designed to select a single value from a set, while checkboxes allow you to turn individual values on and off.

{{<section plugin>}}

{{<app/generator name="radio" >}}

<br>
<h2> Attributes </h2>

You can generate an HTML radio button input tag and C# code by selecting attributes such as `name`, `id`, `checked`, etc. 
- The `name` attribute defines a radio button group by giving each radio button in the group the same name.
- The `id` attribute specifies a unique value that uniquely identifies an individual radio button in the group.
- The `checked` boolean attribute, if present, indicates that this radio button is the default selected one in the group.
<br><br>

<h2> Create Radio Button in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a radio button, see the C# example below. You can create the desired element with a few lines of code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Radio Button in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/), [Id](https://reference.aspose.com/html/net/aspose.html/htmlelement/id/) and [Checked](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/checked/) attributes.
1. Create the [HTMLLabelElement](https://reference.aspose.com/html/net/aspose.html/htmllabelelement/) and set required attributes.
1. Copy C# code for the HTML radio button and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---