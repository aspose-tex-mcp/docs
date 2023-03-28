---
translation: true
title: HTML Audio Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML Audio Generator creates HTML and C# code for an audio element. You can generate code and use it in your own website or C# project.
url: /net/generators/audio/
platformtag: net
family: html
generator: HTML Audio Generator
element: HTML audio
tag: audio
---

{{<section banner>}}
---
h1: HTML Audio Generator
h2: Generate HTML and C# code for an HTML audio element and use it in your website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Audio Tag Easily!
---

The [audio](https://html.spec.whatwg.org/multipage/media.html#the-audio-element) HTML element is used to embed music or any sound content in an HTML document. The `<audio>` element can contain one or more `<source>` tags with different audio sources. The browser will choose the first source it supports. Support for the `<audio>` element varies by browser. Add sounds to your web page using this HTML Audio Generator!

{{<section plugin>}}

{{<app/generator name="audio" >}}

<br>
<h2> Attributes </h2>

There are many options available in HTML Audio Generator that you can use to generate HTML audio tag code and then copy & paste it into your own website. Main attributes supported by the audio element are `controls`, `autoplay`, `loop`, `preload` and `src`. 

 - The audio `preload` attribute specifies the audio file should be loaded when the page loads.
 - The `src` attribute specifies the URL of the audio to embed. But this is optional. Instead, you can use the `<source>` element in the audio block to specify the audio to embed.
 - The `autoplay` boolean attribute, if specified, will automatically start playing.
 - The audio `controls` attribute specifies whether controls should be displayed or not in your browser. For example, if you disabled audio controls and your autoplay setting is enabled, audio will play but will not be visible in the browser. 
 - The `loop` boolean attribute, if specified, will automatically seek back to the start upon reaching the end of the audio.
 - The `muted` boolean attribute, if specified, indicates whether the audio will be initially silenced. Its default value is false. 
<br><br>

<h2> Create HTML Audio Element in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an `<audio>` element, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Audio Element in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create an audio element. In an HTML document, the Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "audio".
2. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `controls` and other required attributes.
3. Create one or more `<source>` elements and set required attributes for them. Use the CreateElement() method with "source" tagName.
4. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add `<source>` elements into the `<audio>` element. 
5. Copy C# code for the HTML audio element and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---