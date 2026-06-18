---
translation: true
template: /templates/_template-python-net.md
linktitle: 许可
title: 许可| 通过 .NET 为 Python 提供 Aspose.TeX
weight: 70
url: /python-net/licensing/
description: 如果您使用的是python的Aspose.TeX API解决方案的许可版本，则可以在此处学习如何应用许可证。
lastmod: "2026-06-18"
---

{{<section overview>}}

## 评估aspose.tex

要评估 Aspose.TeX for Python，您可以轻松地从 [Aspose.TeX for Python 下载页面](https://pypi.org/project/aspose-tex-net/) 下载该产品。评估版与购买版功能相同。只需添加几行代码应用许可证，评估版即可获得许可。请访问下载页面获取最新版本。

### 评估版本限制

Aspose.TeX 的评估版提供完整的产品功能，但输出文档仅包含前四页。此外，这四页会带有评估模式水印。

如果您想在不受评估版限制的情况下试用 Aspose.TeX，可以[申请 30 天临时许可证](https://purchase.aspose.com/temporary-license/)，这样您就可以在购买前测试产品的各个方面。

## 申请许可证

完成 Aspose.TeX for Python 的评估并对其性能满意后，您可以通过 Aspose 网站的[购买门户](http://www.aspose.com/purchase/default.aspx)购买许可证。建议您在购买前先了解不同的许可证类型。如有任何疑问或需要帮助，请随时[联系 Aspose 销售团队](http://www.aspose.com/corporate/contact/default.aspx)，他们将竭诚为您服务。

每个 Aspose 许可证都包含一年的订阅期，在此期间您可以免费升级到任何新版本或修复程序。我们还为所有用户（包括已授权用户和评估用户）提供免费且无限制的技术支持。

Aspose 许可证是一个纯文本 XML 文件，其中包含产品名称、授权开发者数量和订阅到期日期等信息。请勿修改此文件，因为它经过数字签名，即使添加一个额外的换行符也会使其失效。

### 何时申请许可证

请遵循以下准则：

- 每个应用程序域只需设置一次许可证。
- 在使用任何其他 Aspose.TeX 类之前，请先设置许可证。
- 多次调用 `SetLicense` 函数不会造成损害，但会浪费处理器时间。

#### 从文件中加载许可证

以下代码片段演示了如何初始化存储在文件中的许可证。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### 从流对象加载许可证

下一个代码从流来初始化许可证。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### 计量许可证

Aspose.TeX 提供了一种名为“计量许可”的替代许可机制，允许客户根据其 API 功能的使用情况付费。应用“计量许可”非常简单，只需应用一对加密密钥即可。更多信息，请参阅[计量许可常见问题解答](https://purchase.aspose.com/faqs/licensing/metered/)。

要设置计量许可的公钥和私钥，您可以使用[*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/)类的实例，如下例所示：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}