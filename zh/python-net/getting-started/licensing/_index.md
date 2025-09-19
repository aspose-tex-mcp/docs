---
translation: true
template: /templates/_template-python-net.md
linktitle: 许可
title: 许可| 通过 .NET 为 Python 提供 Aspose.TeX
weight: 70
url: /python-net/licensing/
description: 如果您使用的是python的Aspose.TeX API解决方案的许可版本，则可以在此处学习如何应用许可证。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 评估aspose.tex

要评估python的Aspose.TeX，您可以从[Aspose.TeX for Python下载页面]轻松下载产品(1)。评估版本与购买的版本相同。通过添加几行代码应用许可，评估版将获得许可。请参阅下载页以获取最新版本。

### 评估版本限制

aspose.tex的评估版提供了完整的产品功能，但只能在输出文档中获得前四页。此外，这些页面将用评估模式水印盖章。

如果您想在没有这些评估限制的情况下尝试Aspose.TeX，则可以[请求30天的临时许可](https://purchase.aspose.com/temporary-license/)，您将在购买产品之前对其进行测试。

## 申请许可证

完成 Aspose.TeX for Python 的评估并对其性能感到满意后，您可以通过 Aspose 网站的 [购买门户](http://www.aspose.com/purchase/default.aspx) 购买许可证。建议您在购买前熟悉不同的许可证类型。如有任何疑问或需要帮助，请随时[联系 Aspose 销售团队](http://www.aspose.com/corporate/contact/default.aspx)，他们将非常乐意为您提供帮助。

每个ASPOSE许可都包括一年的订阅，该订阅有权释放此期间发布的任何新版本或修复程序。我们还为许可和评估用户提供免费且无限的技术支持。

Aspose的许可证是一个纯文本XML文件，其中包含诸如产品名称，许可开发人员数量和订阅到期日期之类的信息。重要的是不要在数字签名时修改文件，即使添加额外的线路断路也会使其无效。

### 何时申请许可证

请遵循以下准则：

- 每个应用程序域只需要设置一次许可证。
- 在使用任何其他aspose.tex类之前，请先设置许可证。
- 多次调用“ setlicense”是有害的，而是废物处理器时间。

#### 从文件中加载许可证

以下代码片段演示了如何初始化存储在文件中的许可证。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### 从流对象加载许可证

下一个代码从流来初始化许可证。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### 计量许可证

aspose.tex提供了一种称为 *metered许可 *的替代许可机制，该机制允许客户根据其对API功能的使用来计费客户。应用 *计量许可证 *与应用一对密码键一样简单。有关更多信息，请参阅[计量许可常见问题解答部分](https://purchase.aspose.com/faqs/licensing/metered/)。

要设置计量许可证的公共和私钥，您可以使用[*metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/)类的实例，如下所示：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}