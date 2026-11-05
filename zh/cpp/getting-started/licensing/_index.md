---
translation: true
template: /templates/_template-cpp.md
title: 许可| Aspose.TeX for Java 入门
linktitle: 许可
weight: 70
url: /cpp/licensing/
description: 当您停止使用Aspose.TeX API解决方案的许可版本时，此处可以找到如何应用许可证。
lastmod: "2026-04-20"
---

{{<section overview>}}

## 评估aspose.tex

您可以轻松下载用于评估目的的C ++产品的aspose.tex。请参阅[Aspose.TeX for C ++下载页](https://www.nuget.org/packages/Aspose.TeX.Cpp/)查找最新版本。评估下载与购买的下载相同。当您添加几行代码应用许可证时，评估版本就会获得许可。

### 评估版本限制

aspose.tex的评估版(未指定许可证)提供完整的产品功能，只是在输出文档中只能获得多达四个第一页。另外，这些页面将用评估模式水印盖章。

如果您想在没有评估限制的情况下尝试Aspose.TeX，请申请30天的临时许可。请参阅[如何获得临时许可证？](https://purchase.aspose.com/temporary-license/)有关更多信息。

## 申请许可证

一旦您对C ++的Aspose.TeX的评估感到满意，请在Aspose网站上购买许可证：[购买门户](https://purchase.aspose.com/pricing?)。让自己熟悉可用的不同许可类型。如果您有任何疑问，请[与Aspose销售团队联系](https://consulting.aspose.com/)，他们很乐意为您提供帮助。

每个ASPOSE许可证都可以免费升级为期一年的订阅，以便在此期间出现的任何新版本或修复程序。我们为许可和评估用户提供免费且无限的技术支持。

许可证是一个纯文本XML文件，其中包含详细信息，例如产品名称，许可开发人员的数量，订阅到期日期等。该文件是数字签名的，因此请勿修改文件：即使在文件中添加额外的线路中断也无效。

### 何时申请许可证

遵循以下简单规则：

- 每个应用程序域只需要设置一次许可证。
- 您需要在使用任何其他 Aspose::Tex类之前设置许可证。
- 多次调用setlicense不是有害的，而是废物处理器时间。
- 如果要开发一个应用程序，请在使用 Aspose::Tex类之前在启动代码中调用setlicense。
- 如果您正在开发类库，则可以从使用 Aspose::Tex的类的静态构造函数调用setlicense。静态构造函数在创建类实例之前执行，以确保正确设置 Aspose::Tex许可证。

### 使用文件或流对象应用许可证

使用[许可证:: setlicense](https://reference.aspose.com/tex/cpp/aspose.tex/license/)方法来许可组件。设置许可证的最简单方法是将许可证文件放在与Aspose.TeX.dll同一文件夹中，并指定文件名，没有路径，如下所示。

#### 从文件中加载许可证

此代码段将在文件或嵌入式资源中存储的许可初始化。

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromFile.cpp" >}}

#### 从流对象加载许可证

这些代码片段从流中初始化许可证。

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromStream.cpp" >}}