---
translation: true
template: /templates/_template-java.md
linktitle: 许可
title: 许可 | Aspose.TeX for Java 入门
weight: 70
url: /java/licensing/
description: 当您停止使用Aspose.TeX API解决方案的许可版本时，此处可以找到如何应用许可证。
lastmod: "2026-04-21"
---

{{<section overview>}}


### 评估版本限制

aspose.tex的评估版(未指定许可证)提供完整的产品功能，只是在输出文档中只能获得多达四个第一页。另外，这些页面将用评估模式水印盖章。

如果您想在没有评估限制的情况下尝试Aspose.TeX，请申请30天的临时许可。请参阅[如何获得临时许可证？](https://purchase.aspose.com/temporary-license/)有关更多信息。

### 使用文件或流对象应用许可证

使用 [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-) 方法为组件应用许可证。在以下示例中，将 `licenseFilePath` 设置为许可证文件的完整路径。调用方法必须处理或声明 `Exception`。

#### 从文件中加载许可证

此代码片段应用存储在文件中的许可证。

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromFile.java" >}}

#### 从流对象加载许可证

这些代码片段从流中初始化许可证。

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromStream.java" >}}

### 计量许可证

aspose.tex具有一种替代许可机制，称为 *metered许可 *。如果客户希望根据API功能的使用来计费，则可以应用 *Metered许可证 *，这实际上与应用加密密钥对一样简单。有关更多详细信息，请参阅[计量许可常见问题解答部分](https://purchase.aspose.com/faqs/licensing/metered/)。

可以使用[*Metered*](https://reference.aspose.com/tex/java/com.aspose.tex/metered/)类的实例设置计量许可证的公共和私钥，如下所示：

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetMeteredLicense.java" >}}