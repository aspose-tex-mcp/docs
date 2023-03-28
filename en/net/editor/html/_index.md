---
translation: true
title: Edit HTML in C# - Aspose.HTML for .NET
template: /templates/_template-editor-child.md
description: Code to edit HTML files in C#. Use Aspose.HTML for .NET API features to create, remove, or edit content of an HTML document.
url: /net/editor/html/
platformtag: net
family: html
informat: HTML
---

{{<section banner>}}
---
h1: Edit HTML in C#
h2: Use HTML Editor to create, remove, or edit content of an HTML document programmatically
---

{{<section overview>}}
---
h2: How to Edit HTML in C#
---

There are many ways you can edit HTML by using [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library. You can modify the document by inserting new nodes, removing, or editing the content of existing nodes. If you need to edit HTML documents programmatically in C#, the [Aspose.Html.Dom](https://reference.aspose.com/html/net/aspose.html.dom/) (Document Object Model) namespace provides API that represents and interacts with any HTML documents. This namespace contains classes and methods to manipulate HTML documents on the fly. You can insert, remove, replace HTML nodes, extract CSS style information, get the content of elements, and navigate through HTML document by various data selectors.<br>
Any document editing you want to perform involves loading an HTML document, editing and saving it in the supported format. It can be different scenarios, but it can be made with a few required steps:
 - Load an HTML document into a Document object using one of HTMLDocument() constructors. You can load HTML from a file, HTML code, stream,  URL, or create from scratch.
 - Edit HTML DOM using classes and methods of Aspose.Html.Dom namespace.
 - Save HTML or convert HTML to the required file format.



{{<section "code-add-element" i18n-exclude>}}

```cs
    // Load HTML from a file
    var document = new HTMLDocument("document.html");
    
    var body = document.Body;

    // Create a new paragraph element
    var p = (HTMLParagraphElement)document.CreateElement("p");        
    
    // Create a text node
    var text = document.CreateTextNode("We add a new paragraph to an HTML document.");
    
    // Add the text to the paragraph
    p.AppendChild(text);
    
    // Add paragraph to the document body 
    body.AppendChild(p);
    
    // Save HTML file 
    document.Save("edit-document-tree.html");    
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Prepare a path to a source HTML file
    string documentPath = Path.Combine(DataDir, "file.html");

    // Initialize an HTML document from the file
    using var document = new HTMLDocument(documentPath);

    // Find the first document paragraph element 
    var p = document.GetElementsByTagName("p").First();

    // Remove paragraph element
    p.Remove();                

    // Save the HTML document to a file
    document.Save(Path.Combine(OutputDir, "file-edited.html"));
```

{{<section code-text>}}
---
h2: How to Create Element and Add it to HTML File in C#
h3: How to Remove Element from HTML File in C#
title: C# code to edit HTML files
p: "The following C# code example shows how to remove the first paragraph in an HTML document:"
---

Using the C# library, you can programmatically edit HTML documents - change the document structure, style, and content. Let's look at how to add a new HTML element such as `<p>` to an HTML file.

{{<section steps>}}
---
h2: Steps to Create and Add Element to HTML Document in C#
---

Consider simple steps to edit existing HTML document. In the document will add a new text paragraph:

1. Load an HTML document using one of [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/) constructors. You can load HTML from a file, HTML code, stream, or URL.
2. Create a new paragraph element. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of the Document class to create a paragraph element. In an HTML document, the Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is `p`.
3. Create text content for a new paragraph using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method.
4. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add text content into the `<p>` element. 
5. Add the new paragraph to the document body using AppendChild() method.
6. Save the edited HTML file with [Save()](https://reference.aspose.com/html/net/aspose.html/htmldocument/save/#save_10) method.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. You can download the examples from the [GitHub](https://github.com/aspose-html/Aspose.HTML-Documentation) repository. They are open source and can be freely used in your own applications.<br>
 
The [Editing an HTML Document](https://docs.aspose.com/html/net/working-with-documents/editing-a-document/) documentation article gives you basic information on how to read or edit the Document Object Model using Aspose.HTML for .NET API. You will explore how to create HTML elements and how to work with them - modify the document by inserting new nodes, removing, or editing the content of existing nodes.<br>

Aspose.HTML for .NET is an advanced document processing API that allows you to create or open existing HTML documents from various sources in order to perform manipulation operations such as remove, replace and edit HTML nodes, save HTML documents, extract CSS from HTML, configure a document sandbox and more. For more information about classes and methods for editing and manipulating HTML documents, see the [API Reference.](https://reference.aspose.com/html/net/)<br>


{{<section other-editors>}}
---
title: Other Supported Editors
subTitle: "Edit files in other file formats:"
---