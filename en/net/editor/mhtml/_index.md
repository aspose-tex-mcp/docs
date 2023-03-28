---
translation: true
title: Edit MHTML in C# - Aspose.HTML for .NET
template: /templates/_template-editor-child.md
description: Code to edit MHTML files in C#. Use Aspose.HTML for .NET API features to create, remove, or edit content of an MHTML document.
url: /net/editor/mhtml/
platformtag: net
family: html
informat: MHTML
howto: howtoMHTML
---

{{<section banner>}}
---
h1: Edit MHTML in C#
h2: Use MHTML Editor to create, remove, or edit content of an MHTML document programmatically
---

{{<section overview>}}
---
h2: How to Edit MHTML in C#
---

MHTML files represent a web page archive format that can be created by a number of different applications. The format is known as archive format because it saves the web HTML code and associated resources in a single file.<br>
We will edit MHTML files using [Aspose.HTML for .NET API](/html/{{lang.url-fragment}}net/) which is a feature-rich, powerful and easy to use API for C# platform. The [Aspose.Html.Dom](https://reference.aspose.com/html/net/aspose.html.dom/) (Document Object Model) namespace contains classes and methods to manipulate HTML documents on the fly. You can insert, remove, replace HTML nodes, extract CSS style information, get the content of elements, and navigate through HTML document by various data selectors.<br>

**Note:** MHTML document editing goes through the stage of HTML document editing. You can load an HTML document, edit it and save it in MHTML format.

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Prepare path to source HTML file
    string documentPath = Path.Combine(DataDir, "file.html");

    // Prepare path for edited MHTML file saving 
    string savePath = Path.Combine(OutputDir, "file-edited-style.mhtml");

    // Initialize an HTML document from the file
    using var document = new HTMLDocument(documentPath);

    // Create a CSS Selector that extracts the first paragraph element in the document
    var element = document.QuerySelector("p");

    // Print content of the first paragraph  
    Output.WriteLine(element.InnerHTML);
    // output: Aspose.HTML for .NET is a cross-platform class library that enables your applications to perform a wide range of HTML manipulation tasks.

    // Set style attribute with properties for the selected element               
    element.SetAttribute("style", "color:rgb(50,150,200); background-color:#e1f0fe;");            

    // Create MHTML save options object
    var options = new MHTMLSaveOptions();

    // Save the HTML document as an MHTML file
    document.Save(savePath, options);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Prepare path to source HTML file
    string documentPath = Path.Combine(DataDir, "file.html");

    // Prepare path for edited MHTML file saving 
    string savePath = Path.Combine(OutputDir, "file-remove-p.mhtml");

    // Initialize an HTML document from the file
    using var document = new HTMLDocument(documentPath);

    // Find the last document paragraph element 
    var p = document.GetElementsByTagName("p").Last();

    // Remove paragraph element
    p.Remove();
            
    // Create MHTML save options object
    var options = new MHTMLSaveOptions();

    // Save the HTML document as an MHTML file
    document.Save(savePath, options);
```

{{<section code-text>}}
---
h2: Code to Edit MHTML File using C#
h3: How to Remove Element from MHTML File in C#
title: C# code to edit MHTML files
p: "The following C# code example shows how to remove the last paragraph in an MHTML document:"
---

Using the C# library, you can programmatically edit MHTML documents - change the document structure, style, and content. Let's look at how to style `<p>` paragraph element in an MHTML file. We add the `style` attribute to the first paragraph element in the document.

{{<section steps>}}
---
h2: Steps to style paragraph element in MHTML Document using C#
---

Consider simple steps to edit an existing document. In the document we will style the first paragraph:

1. Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
2. Create a CSS Selector that extracts the first element in the document which match selector. Use the [QuerySelector("p")](https://reference.aspose.com/html/net/aspose.html.dom/document/queryselector/) method of the Document class that returns the first `<p>` element in document.
3. Set style attribute with properties for the selected element. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add the style attribute with its property & value pairs.
4. Create an MHTML save options object using the [MHTMLSaveOptions()](https://reference.aspose.com/html/net/aspose.html.saving/mhtmlsaveoptions/mhtmlsaveoptions/) constructor. 
5. Save the edited HTML file as an MHTML document using the [Save()](https://reference.aspose.com/html/net/aspose.html/htmldocument/save/#save_14) method.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide and [API Reference.](https://reference.aspose.com/html/net/) You can download the examples and showcase projects from the [GitHub](https://github.com/aspose-html/Aspose.HTML-Documentation) repository. They are open source and can be freely used in your own applications.<br>
 
The [Editing an HTML Document](https://docs.aspose.com/html/net/working-with-documents/editing-a-document/) documentation article gives you basic information on how to read or edit the Document Object Model using Aspose.HTML for .NET API. You will explore how to create HTML elements and how to work with them - modify the document by inserting new nodes, removing, or editing the content of existing nodes.<br>

The articles in the [How-To Articles](https://docs.aspose.com/html/net/how-to-articles/) chapter answer popular questions about how to work with HTML files. In addition, the articles contain C# examples that provide the necessary information about using the Aspose.HTML class library to solve specific tasks, such as how to change the text style in a paragraph,  how to effectively apply selectors to select the elements you want to edit, etc.

{{<section other-editors>}}
---
title: Other Supported Editors
subTitle: "Edit files in other file formats:"
---