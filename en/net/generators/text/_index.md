---
translation: true
title: HTML Text Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Сreate HTML Text Input for your website. Рreview the text box, copy and use generated HTML and C# code in your project!
url: /net/generators/text/
platformtag: net
family: html
generator: HTML Text Input Generator
element: HTML text input
tag: text
---

{{<section banner>}}
---
h1: HTML Text Input Generator
h2: Generate HTML and C# code for an HTML Text Input element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Text Input Easily!
---

HTML [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) elements with `type='text'` create basic single-line text inputs. Use them if you want users to enter a single line value. An on-screen keyboard will appear if you are using a smartphone or tablet. You can use this HTML Text Input Generator to create code which can be pasted into HTML. Just select options and get the text input on the fly!

<b>Note:</b> Text boxes are classified into two types: text fields and [text areas.](/html/{{lang.url-fragment}}net/generators/textarea/) These two text boxes serve different purposes and help users understand what they should be entering into the text field. An HTML `<textarea>` tag defines an area where you can enter multiple lines of text. 

{{<section plugin>}}

{{<app/generator name="text" >}}

<br>
<h2> Attributes </h2>

With the input `type='text'` element you can use attributes such as *name*, *size*, *placeholder*, *list*, *required*, *spellcheck*, *maxlength*, *minlength*, etc.

- The `size` attribute is a numeric value indicating how many characters should be in the input field. The default width of the text field is 20 characters.
- The `placeholder` attribute is a string that gives the user a brief hint about what information is expected in the field.
- The `spellcheck` is an attribute that is used to indicate whether to enable spell-checking for an element.
- Add a `required` attribute to ensure users fill this field.
<br><br>

<h2> Create HTML Text Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your product or programmatically add a text input, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create Text Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/), and [Size](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/size/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `placeholder`, `spellcheck` or other supported attributes with their values.
1. Copy C# code for the HTML text input and use it in your project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Code Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---