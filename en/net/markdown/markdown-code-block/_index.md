---
translation: true
title: Markdown Code Block - C# Code
template: /templates/_template-md-child.md
description: Create Markdown Inline Code and Code Block in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-code-block/
platformtag: net
family: html
element: Code Block
tag: markdown-code-block
---

{{<section banner>}}
---
h1: Markdown Code Block in C#
h2: Use the C# library to create Markdown Inline Code ot Markdown Code Block.
---

{{<section overview>}}
---
h2: How to Create Markdown Inline Code or Code Block in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Use the SyntaxFactory property to get the factory for creating the Markdown syntax tree
    var mdf = markdown.SyntaxFactory;

    // Create an empty codeSpan node
    var codeSpan = mdf.CodeSpan();

    // Create text content for the codeSpan
    codeSpan.AppendChild(mdf.Text("Source code text"));

    // Add codeSpan to MD document
    markdown.AppendChild(codeSpan); 

    // Add a space after the code node through a special WhiteSpace node
    markdown.AppendChild(mdf.Whitespace());           

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-code.md");

    // Save MD file
    markdown.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = markdown.SyntaxFactory;

    // Create a start token and an end token that will frame a code block
    var startToken = mdf.Token(SourceText.From("```\r\n"));
    var endToken = mdf.Token(SourceText.From("\r\n```"));

    // Create a fenced code element
    var fencedCodeSpan = mdf.FencedCodeBlock(startToken, null, endToken);

    // Create text content for the fenced code element
    fencedCodeSpan.AppendChild(mdf.Text("Source code text"));

    //Add the fenced code element to MD file
    markdown.AppendChild(fencedCodeSpan);
            
    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-code-block.md");

    // Save MD file
    markdown.Save(savePath);
```

{{<section code-text>}}
---
h2: How to Add Markdown Inline Code in C#
h3: Add Markdown Code Block in C#
title: C# code to add inline code to MD file
title1: C# code to add Markdown code block
p: "The following C# code example shows how to add Markdown code block to MD document:"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Creating a Markdown inline code or Markdown code block in C# has a feature, that the CodeSpan or FencedCodeBlock element needs to be assembled from several nodes, such as text nodes, spaces between text nodes, or an empty line after the node.<br>
Let's look at creating a Markdown document from scratch and adding inline code to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Code in C#
---

We remind you that the inline code needs to be assembled from the component nodes. Consider simple steps to create Markdown inline code:

1. Create a new empty CodeSpan node using [CodeSpan()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/codespan/#codespan) constructor in SyntaxFactory.
2. Use the [Text()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/text/#text_2) constructor to create text nodes for the CodeSpan.
3. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add text nodes into the CodeSpan element.
4. Add created code block to the document syntax tree using AppendChild() method.
5. Use the [Whitespace()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/whitespace/#whitespace_2) constructor to create space after inline code.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---