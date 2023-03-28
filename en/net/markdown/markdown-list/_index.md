---
translation: true
title: Markdown Lists - C# Code
template: /templates/_template-md-child.md
description: Creating Markdown Lists in C#. Use the C# library to create ordered and unordered Markdown lists.
url: /net/markdown-list/
platformtag: net
family: html
element: List
tag: markdown-list
---

{{<section banner>}}
---
h1: Markdown Lists in C#
h2: Use the C# library to create ordered and unordered Markdown lists.
---

{{<section overview>}}
---
h2: How to Create Markdown Lists in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. Markdown supports ordered (numbered) and unordered (bulleted) lists. In this article, you learn about adding lists in Markdown using C# library.
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = md.SyntaxFactory;

    // Create a new empty odered list node
    var orderedList = mdf.OrderedList();

    // Create and add to the odered list a li1 item with the marker “1”
    var li1 = mdf.OrderedListItem(1);
    orderedList.AppendChild(li1);

    // Create a paragraph with text content and add it to the li1 item
    var paragraph = mdf.Paragraph();

    var heading = mdf.AtxHeading("The first element in the Markdown ordered list is the level 3 heading.", 3);
    paragraph.AppendChild(heading);
    li1.AppendChild(paragraph);

    //Create and add to the odered list a li2 item with the marker “2”
    var li2 = mdf.OrderedListItem(2);
    orderedList.AppendChild(li2);

    // Create a strong emphasis with text content and add it to the li2 item
    var bold = mdf.Emphasis(Emphasis.Strong);

    bold.AppendChild(mdf.Text("The second item in the Markdown ordered list is in bold."));
    li2.AppendChild(bold);

    // Add orderedList to MD syntax tree
    md.AppendChild(orderedList);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output-odered-list.md");

    // Save MD file
    md.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
// Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factoty
    var mdf = md.SyntaxFactory;

    // Create a new empty unodered list node
    var unorderedList = mdf.UnorderedList();

    // Create and add to the unodered list a li1 element with the marker “-”
    var li1 = mdf.UnorderedListItem("-");
    unorderedList.AppendChild(li1);

    // Create a paragraph with text content and add it to the li1 item:
    var paragraph = mdf.Paragraph();
    paragraph.AppendChild(mdf.Text("The first item of the unordered Markdown list."));            
    li1.AppendChild(paragraph);

    // Create and add to the unodered list a li2 element with the marker “-”
    var li2 = mdf.UnorderedListItem("-");
    unorderedList.AppendChild(li2);

    // Create a paragraph with text content and add it to the li2 item:
    var paragraph2 = mdf.Paragraph();
    paragraph2.AppendChild(mdf.Text("The second item of the unordered Markdown list."));
    li2.AppendChild(paragraph2);

    // Add unorderedList to MD syntax tree
    md.AppendChild(unorderedList);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-unodered-list.md");

    // Save MD file
    md.Save(savePath);       
```

{{<section code-text>}}
---
h2: Create Markdown Ordered List in C#
h3: Create Unordered Markdown List in C#
title: C# code to create Markdown ordered list
title1: C# code to add unordered list to MD file
p: "The following C# code example shows how to add unordered list to MD file:"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding Markdown ordered list to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Ordered List in C#
---

Here are a few simple steps to create Markdown ordered list:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create a new orderedList node using the [OderedList()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/orderedlist/) constructor in SyntaxFactory.
4. Use the [OrderedListItem()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/orderedlistitem/)constructor to create new instances of the ListItemSyntaxNode class with an ordered list item marker.
5. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add odered list items into the orderedList node.
6. After all items with their content are gathered into a single orderedList element, add it to the document syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---