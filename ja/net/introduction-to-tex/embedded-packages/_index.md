---
translation: true
template: /templates/_template-net.md
title: Aspose.TeX埋め込みLaTeXパッケージ
linktitle: 埋め込まれたLaTeXパッケージ
weight: 20
url: /net/embedded-packages/
description: 以下は、使用されている説明とバージョンとともに、Aspose.TeXライブラリに埋め込まれたパッケージのリストです。
lastmod: 2026-10-21
---

{{<section overview>}}

## 組み込み済みのLaTeXパッケージ一覧

開発者の皆様から、どのマクロパッケージがAspose.TeXエンジン環境に標準で組み込まれており、どれが手動での追加を必要とするのかというご質問をよくいただきます。Aspose.TeXライブラリには、あらかじめ組み込まれているLaTeXパッケージがいくつか存在します。以下にその一覧を示します。


| **パッケージ** | **バージョン** |
| :- | :- |
| `amsmath` | v2.17j 2021/04/20. |
| `colortbl` | v1.0f 2022/06/20. |
| `eurosym` | v1.1 1998/08/06. |
| `geometry` | v5.9 2020/01/02 相当の調整版 |
| `graphics` | v1.4d 2021/03/04 相当の調整版 (graphicx v1.2c 2020/12/05, color v1.0j 2005/11/14 を含む) |
| `hyperref` | v6.83m 2012/11/06 相当の調整版 |
| `lipsum` | v2.7 2021/09/20. |
| `multirow` | v2.8 2021/03/15. |
| `pgf` | v3.1.9a 2021/05/15. |
| `pict2e` | v0.4b 2020/09/30 相当の調整版 |
| `setspace` | v6.7b 2022/12/04. |
| `url` | v3.4 2013/09/16. |
| `wasysym` | v2.0 2003/10/30. |
| `xcolor` | v2.12 2016/05/11. |

### `latex-tools` バンドル:

`afterpage`, `array`, `bm`, `calc`, `dcolumn`, `delarray`, `enumerate`, `fileerr`, `fontsmpl`, `ftnright`, `hhline`, `indentfirst`, `layout`, `longtable`, `multicol`, `rawfonts`, `showkeys`, `somedefs`, `tabularx`, `theorem`, `trace`, `varioref`, `verbatim`, `xr`, `xspace`

**詳細情報:**

- [TeX 入出力 (tex-io)](/tex/{{lang.url-fragment}}net/tex-io/): `IInputWorkingDirectory` および `IOutputWorkingDirectory` が、どのようにストリームやディスクリソースを扱うかについて解説しています。
- [LaTeX とは](/tex/{{lang.url-fragment}}net/what-is-latex/)
- [Aspose.TeX と Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/): 基盤となるマネージド・オブジェクト・モデルについて解説しています。

企業向けの文書では、エンジンに標準で組み込まれていない、特殊なファイルやサードパーティ製の `.sty` / `.cls` ファイルが必要になることが避けられません。Aspose.TeX では、こうした[外部の LaTeX パッケージを利用する](/tex/{{lang.url-fragment}}net/external-latex-packages/)ことも可能です。