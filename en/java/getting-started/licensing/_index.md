---
translation: true
template: /templates/_template-java.md
linktitle: Licensing
title: Licensing | Aspose.TeX for Java
weight: 70
url: /java/licensing/
description: When you stopped on the licensed version of the Aspose.TeX API solution for Java here you find out how to apply the license.
lastmod: "2024-09-20"
---

{{<section overview>}}


### Evaluation Version Limitations

The evaluation version of Aspose.TeX (without a license specified) provides full product functionality except that only up to four first pages can be obtained in the output document. Also, those pages will be stamped with an evaluation mode watermark.

If you want to try Aspose.TeX out without evaluation limitations, request a 30-day temporary license. Please refer to [How to get a Temporary License?](https://purchase.aspose.com/temporary-license/) for more information.

### Apply the License using File or Stream Object

Use the [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-) method to license the component. In the examples below, set `licenseFilePath` to the full path to your license file. The calling method must handle or declare `Exception`.

#### Loading a License from File

This code snippet applies a license stored in a file.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromFile.java" >}}

#### Loading a License from a Stream Object

These code snippets initialize the license from the stream.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromStream.java" >}}

### Metered License

Aspose.TeX has an alternative licensing mechanism called *Metered Licensing*. If a customer wishes to be billed based on the usage of the API features, they can apply a *Metered License*, which is actually as simple as applying a cryptographic key pair. For more details, please refer to the [Metered Licensing FAQ section](https://purchase.aspose.com/faqs/licensing/metered/).

The public and private keys of a metered license can be set using an instance of the [*Metered*](https://reference.aspose.com/tex/java/com.aspose.tex/metered/) class, as shown below:

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetMeteredLicense.java" >}}