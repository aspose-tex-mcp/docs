---
translation: true
template: /templates/_template-net.md
linktitle: 许可
title: 许可 | .NET的Aspose.TeX
weight: 70
url: /net/licensing/
description: 当您停止使用Aspose.TeX API解决方案的.NET的许可版本时，您会发现如何应用许可证。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 评估aspose.tex

您可以轻松下载.net产品的aspose.tex，以进行评估。请参阅[Aspose.TeX的.NET下载页](https://www.nuget.org/packages/Aspose.TeX/)以查找最新版本。评估下载与购买的下载相同。当您添加几行代码应用许可证时，评估版本就会获得许可。

### 评估版本限制

aspose.tex的评估版(未指定许可证)提供完整的产品功能，只是在输出文档中只能获得多达四个第一页。另外，这些页面将用评估模式水印盖章。

如果您想在没有评估限制的情况下尝试Aspose.TeX，请申请30天的临时许可。请参阅[如何获得临时许可证？](https://purchase.aspose.com/temporary-license/)有关更多信息。

## 申请许可证

一旦您对.net的aspose.tex评估感到满意，请在Aspose网站上购买许可证：[购买门户](http://www.aspose.com/purchase/default.aspx)。让自己熟悉可用的不同许可类型。如果您有任何疑问，请[与Aspose销售团队联系](http://www.aspose.com/corporate/contact/default.aspx)，他们很乐意为您提供帮助。

每个ASPOSE许可证都可以免费升级为期一年的订阅，以便在此期间出现的任何新版本或修复程序。我们为许可和评估用户提供免费且无限的技术支持。

许可证是一个纯文本XML文件，其中包含详细信息，例如产品名称，许可开发人员的数量，订阅到期日期等。该文件是数字签名的，因此请勿修改文件：即使在文件中添加额外的线路中断也无效。

### 何时申请许可证

遵循以下简单规则：

- 每个应用程序域只需要设置一次许可证。
- 您需要在使用任何其他aspose.tex类之前设置许可证。
- 多次调用setlicense不是有害的，而是废物处理器时间。
- 如果要开发Windows表单或控制台应用程序，请在使用aspose.tex类之前在启动代码中调用setlicense。
- 在开发ASP.NET应用程序时，请在aplication_start受保护的方法中从global.asax.cs文件调用setlicense。应用程序启动时，它被调用一次。
- 请勿在page_load方法中调用setlicense，因为它意味着每次加载网页时都会加载许可证。
- 如果您正在开发类库，则可以从使用Aspose.TeX的类的静态构造函数调用setlicense。静态构造函数在创建类实例之前执行，以确保正确设置Aspose.TeX许可证。

### 使用文件或流对象应用许可证

使用[许可证。设置](https://reference.aspose.com/tex/net/aspose.tex/license/)方法来许可组件。设置许可证的最简单方法是将许可证文件与 *aspose.tex.dll* 相同的文件夹中，并指定文件名，没有路径，如下所示。

#### 从文件中加载许可证

此代码段将在文件或嵌入式资源中存储的许可初始化。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-LoadLicenseFromFile.cs" >}}

#### 从流对象加载许可证

这些代码片段从流中初始化许可证。

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-LoadLicenseFromStream.cs" >}}

### 计量许可证

aspose.tex具有替代许可机制。那些希望根据API功能使用的客户可以使用 *Metered许可 *来收费的那些客户。应用 *计量许可证 *实际上与应用一对密码键一样简单。有关更多详细信息，请参阅[计量许可常见问题解答部分](https://purchase.aspose.com/faqs/licensing/metered/)。

使用[*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/)类的实例设置了计量许可证的公共和私钥，如下所示： 

{{< gist "aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.Examples-SetMeteredLicense.cs" >}}