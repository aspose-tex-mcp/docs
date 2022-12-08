---
meta: true
translation: true
deploy: false
---

{{<section faqcreatecustomtex>}}
---
qs[1].name: "What is a LaTeX template?"
qs[1].text: "Template is a saved set of properties, settings or structure that can be applied to a newly created document to save time. For LaTeX it can be a file that contains information of page format, fonts, document class, included packages, etc."
qs[2].name: "How do I use LaTeX templates?"
qs[2].text: "If you do not use any additional software and the template is just a  .tex file, just open it and start working. Just keep in mind that you do not save the changes right in  this document but use Save as option instead."
qs[3].name: "How to set the type of LaTeX document?"
qs[3].text: "To specify the type of document in LaTeX such as an article, book, or presentation, use the command `documentclass{article}`."
qs[4].name: "How to create a custom TeX format?"
qs[4].text: "To create a custom TeX format using Aspose.TeX API Solution you need to create TeX engine options. Then specify a file system working directory for the input and output and create the format using *TeXJob.CreateFormat()* Method."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqcustominput>}}
---
qs[1].name: "How do I enter in TeX?"
qs[1].text: "To enter any input to a TeX file use `input` and `include` commands. For example, the `input<file name>` command adds the file with the specified name to the TeX file."
qs[2].name: "How do I make a TeX file?"
qs[2].text: "For this create TeX engine options for no format upon *ObjectTeX* engine extension using *ConsoleAppOptions()* Method of *TeXOptions Class*."
qs[3].name: "How to work with the input of a TeX file?"
qs[3].text: "To manipulate the input of TeX using Aspose.TeX API Solution, use the Input Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
qs[4].name: "How to customize the input of a TeX file?"
qs[4].text: "To customize the input of a TeX file using this API Solution you need to create TeX engine options. Then specify a file system working directory for the input using the *InputFileSystemDirectory* Class."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqcustomoutput>}}
---
qs[1].name: "How do I make a LaTeX file?"
qs[1].text: "Aspose.TeX Solution allows you to create a LaTeX file online. Just use one of the [cross-platform applications](https://products.aspose.app/tex/applications): LaTeX Equation Editor, LaTeX Editor or LaTeX Table Generator. They let you generate files in just a few moments."
qs[2].name: "How to work with the output of a TeX file?"
qs[2].text: "To manipulate the output of TeX using Aspose.TeX API Solution, use the Output Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
qs[3].name: "How do I view LaTeX output?"
qs[3].text: "To View TeX/LaTeX files online there are free [Viewer](https://products.aspose.app/tex/viewer) applications. With them, you will need only to upload files and get the result on the screen in just a moment."
qs[4].name: "How to customize the output of a TeX file?"
qs[4].text: "To customize the output of a TeX file using this API Solution you need to create TeX engine options. Then specify a file system working directory for the input using the *OutputFileSystemDirectory* Class."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadfromdisc>}}
---
qs[1].name: "How can I read TeX files online?"
qs[1].text: "To read TeX files online there is a free [Viewer](https://products.aspose.app/tex/viewer) application. With it, you will need only to upload files and get the result on the screen in just a moment. You may also use [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics) which lets you also see and add the LaTeX code of a file."
qs[2].name: "How do I open a LaTeX file in Word?"
qs[2].text: "The easiest way to do this, is to convert LaTeX to Word with our web [Converter](https://products.aspose.app/tex/conversion/latex). Then you will be able to use the content of your file in MS Word."
qs[3].name: "How do I load a TeX file from disk?"
qs[3].text: "First, create conversion options using *ConsoleAppOptions()*. Then specify a file system working directory for the input and output. Specify the console as the output terminal and run the job."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadfromzip>}}
---
qs[1].name: "What classes are used to load a TeX file from ZIP?"
qs[1].text: "To manipulate the output/input of TeX files loaded from ZIP, use the ZipDirectory Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
qs[2].name: "How do I install TeX Package?"
qs[2].text: "For this, open the NuGet package manager, and search for Aspose.TeX and install or use the following command from the Package Manager Console."
qs[3].name: "How do I load a TeX file from ZIP?"
qs[3].text: "Open the stream on the ZIP archive for the input and output. Then create conversion options using *ConsoleAppOptions()*. Next, specify a ZIP archive working directory for the input and output. Specify the console as the output terminal, define the saving options, and run the job."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqloadlicense>}}
---
qs[1].name: "What is the difference between TeX and LaTeX?"
qs[1].text: "TeX is markup or typeset language, when LaTeX is the most famous package of TeX, that includes many useful tools for publication."
qs[2].name: "How to load a TeX license?"
qs[2].text: "To load a TeX license using this API Solution you need to Initialize license object by means of the *License* Class. Then set the license using the *SetLicense()* Method."
qs[3].name: "How to manage licenses with this API Solution?"
qs[3].text: "To license the component use the entities of the [*License*](https://reference.aspose.com/tex/net/aspose.tex/license/) Class."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqoutputtodisk>}}
---
qs[1].name: "Can I transform TeX files to PDF?"
qs[1].text: "Yes, this API Solution supports such functionality. You will need the *Aspose.TeX.Presentation.Pdf* namespace that provides classes for typesetting TeX files to PDF."
qs[2].name: "Can I write TeX output to a disk?"
qs[2].text: "This API Solution includes such functionality. For this use the *OutputFileSystemDirectory* Class that implements the regular file system’s method for getting a file stream to write to."
qs[3].name: "How to write TeX output to a disk?"
qs[3].text: "First, create conversion options using *ConsoleAppOptions()*. Next, specify a file system working directory for the input and output. Note that the terminal output must be written to a file in the output working directory, and run the job."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqoutputtozip>}}
---
qs[1].name: "How do I view TeX output?"
qs[1].text: "To open to see the content of the TeX file online, use the cross-platform [TeX Viewer](https://products.aspose.app/tex/viewer/tex). It will also let you save the file as an image."
qs[2].name: "Can I write TeX output to a ZIP archive?"
qs[2].text: "Yes, this API Solution supports such functionality. You will need *OutputZipDirectoryClass* that implements the method for getting a file stream to write to when the working directory is a ZIP archive."
qs[3].name: "How to write TeX output to a ZIP archive?"
qs[3].text: "Create the instance of the *TeXOptions Class*. Then specify a ZIP archive working directory for the output and the console as the output terminal. Specify the saving options and run the conversion. Finally, write the output to ZIP using *OutputZipDirectory* Class."
---

{{<import path="/meta/schemas.md" section="faq">}} 


{{<section faqtypesettex>}}
---
qs[1].name: "What is typeset in LaTeX?"
qs[1].text: "LaTeX supports various typesetting features useful for a document author called packages. In these packages you can find advanced tools for math formulas, drawing graphics, creating tables and templates, etc."
qs[2].name: "Is LaTeX a typesetting software?"
qs[2].text: "Yes, LaTeX is a typesetting software and is widely used for creating different types of elaborated documents like, science works, articles, term papers, books, and many more."
qs[3].name: "How to typeset TeX files?"
qs[3].text: "To typeset TeX files using Aspose.TeX API Solution you need to create the format provider first. Create conversion options for a custom format upon ObjectTeX engine extension. Then specify a file system working directory for the input and output and create the format using *TeXJob.CreateFormat()* Method."
---

{{<import path="/meta/schemas.md" section="faq">}} 

