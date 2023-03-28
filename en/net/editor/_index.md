---
translation: true
template: /templates/_template-editor.md
title: Edit HTML, MHTML, and Markdown Using C#
url: /net/editor/
aliases:
  - /net/editor/xhtml/
  - /net/editor/epub/
  - /net/editor/svg/
description: Code to edit HTML, Markdown, and MHTML files in C#. Use Aspose.HTML for .NET API features to create, remove, or edit content of a document. 
feature: editor
---

{{<section banner>}}
---
h1: Edit HTML, MHTML and MD Files Via C# 
h2: Use C# library features to create elements, remove, or edit the content of existing nodes of a document.
---

{{<section overview>}}
---
h2: Edit HTML, MHTML and Markdown Files Using C#
---

In order to edit HTML, MHTML and MD files, we will use [Aspose.HTML for.NET API](https://products.aspose.com/html/{{lang.url-fragment}}net/) which is a feature-rich, powerful and easy-to-use document manipulation API for the C# platform. You can choose a kind of Editor for different source files such as HTML, MHTML or Markdown.<br>

You can edit files in other file formats and consider how to create, load and save HTML documents by following the links. Here you will find various approaches that can be used to edit documents:


{{<section functions>}}
---
h2: Editing Functions
---

Some file editing functions that the Aspose.HTML for .NET API can perform are the following:
 - Edit a document tree - add, replace or remove elements (paragraphs, images, tables, iframes, etc.).
 - Edit the content of existing nodes.
 - Specify and edit CSS style properties for HTML elements.
 - Navigate through a document and search elements to edit.
 - Modify attributes of HTML elements. 
 - Configure a document sandbox amd more.

If you want to generate HTML or C# code quickly, our [HTML Generators](/html/{{lang.url-fragment}}net/generators/) are here to help. These free online tools automatically generate HTML code and C# code on the fly! You can easily generate code to add elements such as images, forms, tables, etc. to HTML documents, copy and use it in your project.

{{<section "code" i18n-exclude>}}

```cs
    // Create an instance of an HTML document
    using (var document = new HTMLDocument())
    {
        var body = document.Body;

        // Create a paragraph element
        var p = (HTMLParagraphElement)document.CreateElement("p");
    
        // Set a custom attribute
        p.SetAttribute("id", "my-paragraph");
    
        // Create a text node
        var text = document.CreateTextNode("my first paragraph");
    
        // Add the text to the paragraph
        p.AppendChild(text);
    
        // Attach paragraph to the document body 
        body.AppendChild(p);
    
        // Save the HTML document to a file 
        document.Save(Path.Combine(OutputDir, "edit-document-tree.html"));
    }
```

{{<section how-to>}}
---
h2: How to Edit HTML Files
title: Edit HTML in C#
---

The DOM tree (Document Object Model) is the in-memory representation of a document. The [Aspose.Html.Dom](https://reference.aspose.com/html/net/aspose.html.dom/) namespace provides an API that represents and interacts with any HTML, XML, or SVG document. The task of editing HTML programmatically in C# is modifying elements in the HTML document tree.  Aspose.HTML API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. Consider simple steps to create and edit HTML. Let's create HTML document that will contain a text paragraph with an id attribute:

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. You can download the examples and showcase projects from the [GitHub](https://github.com/aspose-html/Aspose.HTML-Documentation) repository. They are open source and can be freely used in your own applications.

 - The articles in the documentation section [Working with HTML Documents](https://docs.aspose.com/html/net/working-with-documents/) provide the information you need to get started with the Aspose.HTML class library. You learn how the DOM represents an HTML document in memory and how to use the API to create, edit, and save an HTML file.
 - The [Editing an HTML Document](https://docs.aspose.com/html/net/working-with-documents/editing-a-document/) article gives you basic information on how to read or edit the Document Object Model (DOM). You will explore how to create HTML elements and how to work with them - modify the document by inserting new nodes, removing, or editing the content of existing nodes.<br>

{{<section installing>}}
---
h2: Installing Aspose.HTML for .NET library
---

Aspose.HTML is an advanced web scraping and HTML parsing library. This library supports parsing of HTML5, CSS3, SVG and HTML Canvas to construct a Document Object Model (DOM) based on the WHATWG DOM Standard. You can use several ways to install the Aspose.HTML library for .NET on your system:</br>

 - Using the NuGet Package Manager GUI.
 - Using the Package Manager Console.
 - Installing Aspose.HTML for .NET through MSI.</br>  

Use the Aspose.HTML C# library to convert, merge, edit HTML documents, extract data from the web, and more! For more details about C# library installation, please refer to [Aspose.HTML Documentation.](https://docs.aspose.com/html/net/getting-started/installation/)

{{<section other-aspose>}}
---
h2: Other Supported .NET API Features
---

Using Aspose.HTML, an advanced web scraping and HTML parsing library, you can create, edit, navigate through nodes, extract data, merge and convert HTML, XHTML, MD, EPUB, and MHTML files to PDF, XPS, DOCX, Images and other formats.