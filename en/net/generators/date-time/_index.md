---
translation: true
title: HTML Date & Time Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML date & time input, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/date-time/
platformtag: net
family: html
generator: HTML Date & Time Input Generator
element: HTML Date & Time Input
tag: date-time
---

{{<section banner>}}
---
h1: HTML Date & Time Input Generator
h2: Generate HTML and C# code for an HTML Date & Time Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate Date & Time Input on the fly!
---

The [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) elements with `type='date'`, or `type='time'` create input fields that let the user enter date or time, either with a textbox that validates the input or a special date & time picker interface. Date & time pickers are widely used to help users select the required date or time quickly and easily.

{{<section plugin>}}

{{<app/generator name="dateTime" >}}

<br>
<h2> Attributes </h2>

If you choose input type `type='date'`, you create an input field that allows users to enter a date. The resulting value includes the year, month, and day.
The `type='month'` input type creates an input field that allows users to enter the month and year. The input `type='week'` creates an input field that allows users to quickly select a year plus the week number for that year, which can be from week 1 to 52 or 53. The input `type='time'` is used to create an input field that allows users to quickly enter time - hours and minutes, sometimes seconds.

HTML Date & Time Input Generator helps to generate HTML date & time input code that can be inserted into HTML. Select options and create a date & time picker!<br><br>

<h2> Create HTML Date & Time Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an HTML date & time input, see the C# code example below. You can create the desired element with a few lines of C# code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Date & Time Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `value` attribute and its value to specify a date, time, week, or month.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---