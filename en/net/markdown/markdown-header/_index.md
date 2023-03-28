---
translation: true
title: Markdown Header - C# Code
template: /templates/_template-md-child.md
description: Code for creating Markdown Header in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-header/
platformtag: net
family: html
element: Header
tag: markdown-header
---

{{<section banner>}}
---
h1: Markdown Header in C#
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Header in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
     // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Get a SyntaxFactory to create new elements
    var mdf = markdown.SyntaxFactory;

    // Create headings of the required level
    var heading1 = mdf.AtxHeading("Heading 1 level text", 1);
    var heading2 = mdf.AtxHeading("Heading 2 level text", 2);
    var heading3 = mdf.AtxHeading("Heading 3 level text", 3);                       

    // Create and add newLineTrivia element for an empty line after headings 
    var newLineTrivia = mdf.NewLineTrivia();
    heading1.GetTrailingTrivia().Add(newLineTrivia);
    heading2.GetTrailingTrivia().Add(newLineTrivia);
    heading3.GetTrailingTrivia().Add(newLineTrivia);            

    // Add the headers to the Markdown syntax tree
    markdown.AppendChild(heading1);
    markdown.AppendChild(heading2);
    markdown.AppendChild(heading3);            

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output-headers.md");

    // Save MD file
    markdown.Save(savePath);   
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = "C:/temp/document.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the document and get a Markdown syntax tree
    var syntaxTree = parser.ParseFile(input);

    // The first element of this document is AtxHeading
    var heading = (AtxHeadingSyntaxNode)syntaxTree.FirstChild;

    // Accumulate the text content from its elements
    var sb = new StringBuilder();

    while (heading.FirstChild != null)
    {
        sb.Append(heading.FirstChild);

        //  Remove accumulated first element from the tree
        heading.RemoveChild(heading.FirstChild);
    }

    // Get a SyntaxFactory to create new elements 
    var syntaxFactory = syntaxTree.SyntaxFactory;

    // Сreate a text node consisting of new and old text and add it as a child element of AtxHeading 
    var textSyntaxNode = syntaxFactory.Text("Added some new text! " + sb);
            
    // Add the new element to the document tree
    heading.AppendChild(textSyntaxNode);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "edit-header.md");

    // Save MD file
    syntaxTree.Save(savePath);    
```

{{<section code-text>}}
---
h2: How to Add Markdown Header in C#
h3: Edit Markdown Header in C#
title: C# code to edit MD files
title1: C# code to add Markdown Header
p: "The following C# code example shows how to edit Markdown header in an existing MD document:"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Creating a Markdown header element in C# has a feature. The feature is that the header needs to be assembled from several nodes, such as text nodes, spaces between text nodes, and an empty line after the header. Let's look at creating a new Markdown document from scratch and adding headers to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Header in C#
---

Let's consider the simple steps to create a Markdown header:

1. Create a new header using [AtxHeading(string, int)](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/atxheading/#atxheading_2) constructor of the [MarkdownSyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/) class. It creates AtxHeadingSyntaxNode with text content and heading level.
2. Create a newLineTrivia element for an empty line after header. Use the [NewLineTrivia()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/newlinetrivia/) constructor.
3. Call the Add() method of the SyntaxNodeCollection class to add the newLineTrivia node into header element.
4. After all header nodes have been collected into one element, add it to the document syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---