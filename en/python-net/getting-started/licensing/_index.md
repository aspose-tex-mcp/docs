---
translation: true
template: /templates/_template-python-net.md
linktitle: Licensing
title: Licensing | Aspose.TeX for Python
weight: 70
url: /python-net/licensing/
description: If you are using the licensed version of the Aspose.TeX API solution for Python, you can learn here how to apply the license.
lastmod: "2024-09-20"
---

{{<section overview>}}

## Evaluate Aspose.TeX

To evaluate Aspose.TeX for Python, you can easily download the product from the [Aspose.TeX for Python download page](https://pypi.org/project/aspose-tex-net/). The evaluation version is the same as the purchased version. By adding a few lines of code to apply the license, the evaluation version becomes licensed. Please refer to the download page for the latest version.

### Evaluation Version Limitations

The The evaluation version of Aspose.TeX provides full product functionality, with the exception that only the first four pages can be obtained in the output document. Additionally, these pages will be stamped with an evaluation mode watermark.

If you would like to try Aspose.TeX without these evaluation limitations, you can [request a 30-day temporary license](https://purchase.aspose.com/temporary-license/) which will you test every aspect of a product before buying it.

## Applying a License

After you have completed your evaluation of Aspose.TeX for Python and are satisfied with its performance, you can purchase a license through the Aspose website at the [Purchase Portal](https://purchase.aspose.com/pricing?). It is recommended to familiarize yourself with the different license types available before making a purchase. If you have any questions or need assistance, please feel free to [contact the Aspose sales team](https://consulting.aspose.com/), as they will be more than happy to help you.

Each Aspose license includes a one-year subscription that entitles you to free upgrades to any new versions or fixes released during that period. We also offer free and unlimited technical support to both licensed and evaluation users.

The license for Aspose is a plain text XML file that includes information such as the product name, number of licensed developers, and subscription expiry date. It is important not to modify the file as it is digitally signed, and even adding an extra line break will invalidate it.

### When to Apply a License

Please follow these guidelines:

- The license only needs to be set once per application domain.
- Set the license before using any other Aspose.TeX classes.
- Calling `set_license` multiple times is not harmful but wastes processor time.

#### Loading a License from File

The following example applies a license from a file. Set `ASPOSE_TEX_PYTHON_NET_LICENSE_PATH` to the license path, or place `Aspose.TeX.Python-net.lic` in the working directory.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### Loading a License from a Stream Object

The next example opens the license file as a binary stream and closes it after applying the license. It uses the same license path setting as the file example.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### Metered License

Aspose.TeX offers an alternative licensing mechanism called *Metered Licensing*, which allows customers to be billed based on their usage of the API features. Applying a *Metered License* is as simple as applying a pair of cryptographic keys. For more information, please refer to the [Metered Licensing FAQ section](https://purchase.aspose.com/faqs/licensing/metered/).

To set the public and private keys of a metered license, you can use an instance of the [*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/) class, as shown below. Supply your keys through `ASPOSE_TEX_METERED_PUBLIC_KEY` and `ASPOSE_TEX_METERED_PRIVATE_KEY`:

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}