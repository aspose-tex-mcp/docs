---
translation: false
deploy: false
---

{{<section converter-latex-images>}}
---
title: C++ code example TEX to PNG BMP JPEG TIFF
input: TEX
output: PNG BMP JPEG TIFF
---
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectLaTeX());

options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

options->set_SaveOptions(System::MakeObject<{{output camel}}SaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"{{inputFile}}", System::MakeObject<ImageDevice>(), options)->Run();

{{<section converter-latex-pdf>}}
---
title: C++ code example PDF
input: TEX
output: PDF
---
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectLaTeX());

options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));

options->set_SaveOptions(System::MakeObject<{{output camel}}SaveOptions>());

System::MakeObject<Aspose::TeX::TeXJob>(u"{{inputFile}}", System::MakeObject<PdfDevice>(), options)->Run();