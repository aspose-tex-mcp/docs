---
translation: true
title: Markdown Paragraph - C# Code
template: /templates/_template-md-child.md
description: Code for creating Markdown paragraph in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-paragraph/
platformtag: net
family: html
element: Paragraph
tag: markdown-paragraph
---

{{<section banner>}}
---
h1: Markdown Paragraph in C#
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Paragraph in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Use the SyntaxFactory property to get the factory for creating the Markdown syntax tree
    var mdf = md.SyntaxFactory;

    // Create an empty paragraph1
    var paragraph1 = mdf.Paragraph();

    // Add texts to the paragraph1
    paragraph1.AppendChild(mdf.Text("The first sentence of the first paragraph."));
    // Add a space after the first sentence in the paragraph through a special WhiteSpace node
    paragraph1.AppendChild(mdf.Whitespace());

    paragraph1.AppendChild(mdf.Text("The second sentence of the first paragraph."));

    // Create and add newLineTrivia element for an empty line after paragraph1 
    var newLineTrivia = mdf.NewLineTrivia();
    paragraph1.GetTrailingTrivia().Add(newLineTrivia);

    // Add the filled paragraph1 into MD document
    md.AppendChild(paragraph1);

    // Create an empty paragraph2
    var paragraph2 = mdf.Paragraph();

    // Add texts to the paragraph2
    paragraph2.AppendChild(mdf.Text("The first sentence of the second paragraph."));
    // Add a space after the first sentence in the paragraph through a special WhiteSpace node
    paragraph2.AppendChild(mdf.Whitespace());

    paragraph2.AppendChild(mdf.Text("The second sentence of the second paragraph."));

    // Add newLineTrivia element for an empty line after paragraph2             
    paragraph2.GetTrailingTrivia().Add(newLineTrivia);

    // Add the filled paragraph2 into MD document as a last child
    md.AppendChild(paragraph2);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-paragraph.md");

    // Save MD file
    md.Save(savePath);   
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = "C:/temp/input.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
    var syntaxTree = parser.ParseFile(input);

    // Get a SyntaxFactory to create new elements 
    var syntaxFactory = syntaxTree.SyntaxFactory;

    // Create a new empty paragraph 
    var paragraphSyntaxNode = syntaxFactory.Paragraph();

    // Create and add newLineTrivia element for an empty line after paragraph 
    var newLineTrivia = syntaxFactory.NewLineTrivia();            
    paragraphSyntaxNode.GetTrailingTrivia().Add(newLineTrivia);
            
    // Create text content for the paragraph 
    var textSyntaxNode = syntaxFactory.Text("Markdown language is simple to learn. It has minimal extra characters, so you can quickly write and make fewer errors.");

    // Add text into paragraph
    paragraphSyntaxNode.AppendChild(textSyntaxNode);

    // Add paragraph to MD document before the first element of the syntax tree
    syntaxTree.InsertBefore(paragraphSyntaxNode, syntaxTree.FirstChild);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output.md");

    // Save Markdown file
    syntaxTree.Save(savePath);
```

{{<section code-text>}}
---
h2: How to Add Markdown Paragraph in C#
h3: Add Markdown Paragraph in C#
title: C# code to edit MD files
title1: C# code to add paragraph
p: "The following C# code example shows how to add paragraph in an existing MD document:"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Creating an MD paragraph element in C# has a feature. The feature is that the paragraph needs to be assembled from several nodes, such as text nodes, spaces between text nodes, and an empty line after the paragraph. Let's look at creating a new Markdown document from scratch and adding two paragraphs to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Paragraph in C#
---

We remind you that the paragraph needs to be assembled from the component nodes. Consider simple steps to create Markdown paragraph:

1. Create a new empty paragraph node using [Paragraph()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/paragraph/) constructor in SyntaxFactory.
2. Use the [Text()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/text/#text_2) constructor to create text nodes for paragraph.
3. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add text nodes and whitespaces into paragraph.
4. Use the [Whitespace()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/whitespace/#whitespace_2) constructor to create space between text nodes in paragraph.
5. Create and add newLineTrivia element for an empty line after paragraph. Use the [NewLineTrivia()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/newlinetrivia/) constructor and the Add() method.
6. After all paragraph nodes have been collected into one element, add it to the document syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---