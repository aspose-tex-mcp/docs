---
translation: true
deploy: false
---

{{<section faq-createcustomtex>}}
---
h2: FAQ
Q1: "What is a LaTeX template?"
A1: "Template is a saved set of properties, settings or structure that can be applied to a newly created document to save time. For LaTeX it can be a file that contains information of page format, fonts, document class, included packages, etc."
Q2: "How do I use LaTeX templates?"
A2: "If you do not use any additional software and the template is just a  .tex file, just open it and start working. Just keep in mind that you do not save the changes right in  this document but use Save as option instead."
Q3: "How to set the type of LaTeX document?"
A3: 'To specify the type of document in LaTeX such as an article, book, or presentation, use the command `\documentclass{article}`.'
Q4: "How to create a custom TeX format?"
A4: "To create a custom TeX format using Aspose.TeX API Solution you need to create TeX engine options. Then specify a file system working directory for the input and output and create the format using *TeXJob.CreateFormat()* Method."
---

{{<section faq-custominput>}}
---
h2: FAQ
Q1: "How do I enter in TeX?"
A1: 'To enter any input to a TeX file use `\input` and `\include` commands. For example, the `\input<file name>` command adds the file with the specified name to the TeX file.'
Q2: "How do I make a TeX file?"
A2: "For this create TeX engine options for no format upon *ObjectTeX* engine extension using *ConsoleAppOptions()* Method of *TeXOptions Class*."
Q3: "How to work with the input of a TeX file?"
A3: "To manipulate the input of TeX using Aspose.TeX API Solution, use the Input Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
Q4: "How to customize the input of a TeX file?"
A4: "To customize the input of a TeX file using this API Solution you need to create TeX engine options. Then specify a file system working directory for the input using the *InputFileSystemDirectory* Class."
---

{{<section faq-customoutput>}}
---
h2: FAQ
Q1: "How do I make a LaTeX file?"
A1: "Aspose.TeX Solution allows you to create a LaTeX file online. Just use one of the [cross-platform applications](https://products.aspose.app/tex/applications): LaTeX Equation Editor, LaTeX Editor or LaTeX Table Generator. They let you generate files in just a few moments."
Q2: "How to work with the output of a TeX file?"
A2: "To manipulate the output of TeX using Aspose.TeX API Solution, use the Output Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
Q3: "How do I view LaTeX output?"
A3: "To View TeX/LaTeX files online there are free [Viewer](https://products.aspose.app/tex/viewer) applications. With them, you will need only to upload files and get the result on the screen in just a moment."
Q4: "How to customize the output of a TeX file?"
A4: "To customize the output of a TeX file using this API Solution you need to create TeX engine options. Then specify a file system working directory for the input using the *OutputFileSystemDirectory* Class."
---


{{<section faq-loadfromdisc>}}
---
h2: FAQ
Q1: "How can I read TeX files online?"
A1: "To read TeX files online there is a free [Viewer](https://products.aspose.app/tex/viewer) application. With it, you will need only to upload files and get the result on the screen in just a moment. You may also use [LaTeX Include Graphics](https://products.aspose.app/tex/includegraphics) which lets you also see and add the LaTeX code of a file."
Q2: "How do I open a LaTeX file in Word?"
A2: "The easiest way to do this, is to convert LaTeX to Word with our web [Converter](https://products.aspose.app/tex/conversion/latex). Then you will be able to use the content of your file in MS Word."
Q3: "How do I load a TeX file from disk?"
A3: "First, create conversion options using *ConsoleAppOptions()*. Then specify a file system working directory for the input and output. Specify the console as the output terminal and run the job."
---


{{<section faq-loadfromzip>}}
---
h2: FAQ
Q1: "What classes are used to load a TeX file from ZIP?"
A1: "To manipulate the output/input of TeX files loaded from ZIP, use the ZipDirectory Classes of the [*Aspose.TeX.IO*](https://reference.aspose.com/tex/net/aspose.tex.io/) namespace."
Q2: "How do I install TeX Package?"
A2: "For this, open the NuGet package manager, and search for Aspose.TeX and install or use the following command from the Package Manager Console."
Q3: "How do I load a TeX file from ZIP?"
A3: "Open the stream on the ZIP archive for the input and output. Then create conversion options using *ConsoleAppOptions()*. Next, specify a ZIP archive working directory for the input and output. Specify the console as the output terminal, define the saving options, and run the job."
---


{{<section faq-loadlicense>}}
---
h2: FAQ
Q1: "What is the difference between TeX and LaTeX?"
A1: "TeX is markup or typeset language, when LaTeX is the most famous package of TeX, that includes many useful tools for publication."
Q2: "How to load a TeX license?"
A2: "To load a TeX license using this API Solution you need to Initialize license object by means of the *License* Class. Then set the license using the *SetLicense()* Method."
Q3: "How to manage licenses with this API Solution?"
A3: "To license the component use the entities of the [*License*](https://reference.aspose.com/tex/net/aspose.tex/license/) Class."
---


{{<section faq-outputtodisk>}}
---
h2: FAQ
Q1: "Can I transform TeX files to PDF?"
A1: "Yes, this API Solution supports such functionality. You will need the *Aspose.TeX.Presentation.Pdf* namespace that provides classes for typesetting TeX files to PDF."
Q2: "Can I write TeX output to a disk?"
A2: "This API Solution includes such functionality. For this use the *OutputFileSystemDirectory* Class that implements the regular file system’s method for getting a file stream to write to."
Q3: "How to write TeX output to a disk?"
A3: "First, create conversion options using *ConsoleAppOptions()*. Next, specify a file system working directory for the input and output. Note that the terminal output must be written to a file in the output working directory, and run the job."
---


{{<section faq-outputtozip>}}
---
h2: FAQ
Q1: "How do I view TeX output?"
A1: "To open to see the content of the TeX file online, use the cross-platform [TeX Viewer](https://products.aspose.app/tex/viewer/tex). It will also let you save the file as an image."
Q2: "Can I write TeX output to a ZIP archive?"
A2: "Yes, this API Solution supports such functionality. You will need *OutputZipDirectoryClass* that implements the method for getting a file stream to write to when the working directory is a ZIP archive."
Q3: "How to write TeX output to a ZIP archive?"
A3: "Create the instance of the *TeXOptions Class*. Then specify a ZIP archive working directory for the output and the console as the output terminal. Specify the saving options and run the conversion. Finally, write the output to ZIP using *OutputZipDirectory* Class."
---


{{<section faq-typesettex>}}
---
h2: FAQ
Q1: "What is typeset in LaTeX?"
A1: "LaTeX supports various typesetting features useful for a document author called packages. In these packages you can find advanced tools for math formulas, drawing graphics, creating tables and templates, etc."
Q2: "Is LaTeX a typesetting software?"
A2: "Yes, LaTeX is a typesetting software and is widely used for creating different types of elaborated documents like, science works, articles, term papers, books, and many more."
Q3: "How to typeset TeX files?"
A3: "To typeset TeX files using Aspose.TeX API Solution you need to create the format provider first. Create conversion options for a custom format upon ObjectTeX engine extension. Then specify a file system working directory for the input and output and create the format using *TeXJob.CreateFormat()* Method."
---