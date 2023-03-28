---
translation: true
title: Edit Markdown in C# - Aspose.HTML for .NET
template: /templates/_template-editor-child.md
description: Code to edit MD files in C#. Use Aspose.HTML for .NET API features to create, remove, or edit content of an MD file.
url: /net/editor/md/
platformtag: net
family: html
informat: MD
---

{{<section banner>}}
---
h1: Edit Markdown in C#
h2: Use Markdown Editor to create, remove, or edit content of an MD file programmatically
---

{{<section overview>}}
---
h2: How to Edit Markdown in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to edit Markdown files without using other software. You can modify a Markdown document by inserting new elements, removing, or editing the content of existing nodes. <br>
The [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) namespace contains classes and methods to manipulate a Markdown syntax tree based on GitHub Flavored Markdown (GFM) Specification.<br>
The [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespace contains classes and methods to provide full Markdown parsing and rendering.<br>
The [Aspose.Html.Toolkit.Markdown.Extensions](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.extensions/) namespace contains classes and methods for manipulating the Markdown syntax tree based on specifications that are not part of the GFM specification. <br>
Any document editing you want to perform involves loading an MD document, editing and saving it in the supported format. It can be different scenarios, but it can be made with a few required steps:
 - Open or [create Markdown.](/html/{{lang.url-fragment}}net/create-markdown/)
 - [Parse Markdown](/html/{{lang.url-fragment}}net/parse-markdown/) to get a syntax tree. Edit the Markdown syntax tree using the classes and methods in the above namespaces.
 - [Save MD](/html/{{lang.url-fragment}}net/save-md/) or [convert MD](/html/{{lang.url-fragment}}net/conversion/md-to-pdf/) to the required file format.

 
{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = @"C:\temp\document.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
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
    var textSyntaxNode = syntaxFactory.Text("Some new text! " + sb);
            
    // Add the new element to the document tree
    heading.AppendChild(textSyntaxNode);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output-edit-header.md");

    // Save MD file
    syntaxTree.Save(savePath);  
```

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = @"C:\temp\document.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
    var syntaxTree = parser.ParseFile(input);

    // Get a SyntaxFactory to create new elements 
    var syntaxFactory = syntaxTree.SyntaxFactory;

    // Create a new paragraph 
    var paragraphSyntaxNode = syntaxFactory.Paragraph();

    // Create and add newLineTrivia element for an empty line after paragraph 
    var newLineTrivia = syntaxFactory.NewLineTrivia();            
    paragraphSyntaxNode.GetTrailingTrivia().Add(newLineTrivia);
            
    // Create text content for the paragraph 
    var textSyntaxNode = syntaxFactory.Text("New paragraph text.");    
    paragraphSyntaxNode.AppendChild(textSyntaxNode);

    // Add the paragraph before the first element of the syntax tree
    syntaxTree.InsertBefore(paragraphSyntaxNode, syntaxTree.FirstChild);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output-add-paragraph.md");

    // Save MD file
    syntaxTree.Save(savePath);
```

{{<section code-text>}}
---
h2: How to Add Element to MD File in C# 
h3: How to Edit Markdown Header in C#
title: C# code to edit MD files
p: "Let's look at how to edit the first element in the MD file ([document.md](/html/images/markdown/document.md)). The first element in the file is a header, level 3. The edited file you find following the link - [output-edit-header.md](/html/images/markdown/output-edit-header.md)"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. The following C# code example shows how to add a new paragraph to an MD document: 

{{<section steps>}}
---
h2: Steps to Create and Add Element to MD Document in C#
---

Consider simple steps to edit existing MD document. In the document will add a new text paragraph:

1. Specify the path to the source MD file and use the [MarkdownParser()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/markdownparser/#constructor) constructor to initialize a new instance of the MarkdownParser class. 
2. Call the [ParseFile()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/parsefile/) method to parse Markdown and get a syntax tree.
3. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get a syntax factory to create new elements.
4. Create a new paragraph using the Paragraph() constructor. Create and add text content for a new paragraph.
5. Use [InsertBefore()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/insertbefore/) method to add the paragraph before the first element of the syntax tree.
6. Save the edited MD file with [Save()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/save/#save_2) method.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. You can download the examples from the [GitHub](https://github.com/aspose-html/Aspose.HTML-Documentation) repository. They are open source and can be freely used in your own applications.<br>
 
The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

Markdown is a simple markup language that allows you to format plain text. MD files use Markdown language that was proposed and developed by John Gruber. John Gruber designed Markdown’s formatting syntax with the goal of making it as readable as possible. Markdown is often used as a format for documentation and readme files since it allows writing in an easy-to-read and easy-to-write style. In addition, MD files can be converted to HTML, PDF, XPS or images to take advantage of other formats for specific tasks.

{{<section other-editors>}}
---
title: Other Supported Editors
subTitle: "Edit files in other file formats:"
---