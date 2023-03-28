---
translation: true
title: Bold in Markdown - C# Code
template: /templates/_template-md-child.md
description: Create Markdown bold text in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-bold/
platformtag: net
family: html
element: Bold
tag: markdown-bold
---

{{<section banner>}}
---
h1: Bold in Markdown - C# Code
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Bold in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
The [MarkdownSyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/) class contains methods to create various Markdown elements. For bold text making, we will use the Emphasis() method that takes as a parameter the Emphasis enumeration value `Emphasis.Strong`. You can use bold for single words, multiple words, sentences, paragraphs, and so on, depending on the formatting style of the document.

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = markdown.SyntaxFactory;

    // Create bold object add text for it
    var bold = mdf.Emphasis(Emphasis.Strong);
    bold.AppendChild(mdf.Text("Bold in Markdown"));

    // Add bold text to the Markdown syntax tree
    markdown.AppendChild(bold);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-bold.md");

    // Save MD file
    markdown.Save(savePath);    
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = md.SyntaxFactory;

    // Create an empty paragraph
    var paragraph = mdf.Paragraph();            

    // Add texts and whitespace to the paragraph
    paragraph.AppendChild(mdf.Text("The Markdown bold is used to"));
    paragraph.AppendChild(mdf.Whitespace());

    // Create bold object add text for it
    var bold = mdf.Emphasis(Emphasis.Strong);
    bold.AppendChild(mdf.Text("bold"));

    // Add bold text and whitespace after it to the paragraph
    paragraph.AppendChild(bold);
    paragraph.AppendChild(mdf.Whitespace());

    // Complete the text of sentence and add to the paragraph
    paragraph.AppendChild(mdf.Text("the text, and it is similar to the bold in Microsoft Word and other text formatting documents."));

    // Add paragraph into MD document
    md.AppendChild(paragraph);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-bold-word.md");

    // Save MD file
    md.Save(savePath);    
```
The rendered result must be: The bold command is used to <b>bold</b> the text, and it is similar to the bold in Microsoft word and other text formatting documents.

{{<section code-text>}}
---
h2: Markdown Bold Text in C#
h3: Markdown Bold for just One Word in a Sentence
title: C# code to create bold in Markdown
title1: C# code to add Markdown bold
p: "We can use bold for single words, multiple words, sentences, paragraphs, and so on, depending on the formatting style of the document. The following C# code example shows how to add bold Markdown for just one word in a sentence."
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding bold text to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Bold in C#
---

Let' discuss C# example based on bold in Markdown. We consider a few simple steps to create Markdown bold text:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create bold object add text for it using [Emphasis()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/emphasis/#emphasis) constructor and the [Text()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/text/#text_2) constructor.
4. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add bold node into the the document syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---