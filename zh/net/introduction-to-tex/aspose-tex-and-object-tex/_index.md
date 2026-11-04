---
translation: true
template: /templates/_template-net.md
linktitle: Object TeX
title: Aspose.TeX和Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX是此API解决方案的输入和输出格式，因此我们可以在这里解释Object TeX以及如何将其转换为目标格式。
lastmod: "2026-11-04"
---

{{<section overview>}}

## Object TeX

现在，让我们考虑输出格式。

原始TeX仅能以 *DVI*(独立)格式输出文件。碰巧的是，DVI格式并未定义要打印文件的媒体的指标 - 页面大小和整个页面内容的左上角的位置。一旦我们决定使TeX引擎能够输出文件，例如，我们需要定义此类指标。因此，我们需要将新的原语包括在原始TeX引擎的套装中。这将是引擎本身的延伸。

那就是 *Object* TeX。同样，**一方面，这是一种编程语言，其中包括VirTeX的一组原语，并随着新的输出需求施加的新原语而扩展。另一方面，这是一种扩展的TeX引擎，也了解新的原语。而且，第三方，Object TeX是一个整体的新排版系统。**

有第四只手。Object TeX格式也是基于Plain TeX的格式，其中包含涉及新原语的定义，例如将默认值分配给媒体指标。

## Aspose.TeX

Aspose.TeX只是Object TeX系统的API。

## 为什么新的TeX是Object？ {#why-the-new-tex-is-object}

那么，为什么我们在系统的名称中使用“对象”呢？原因是Object TeX引擎的实际输出不是输出格式的文件，而是某些中间 *对象 *模型，然后将其转换为目标格式。

## 原生引擎的局限性与托管环境的灵活性

当从传统的命令行 TeX 发行版（如 TeX Live 或 MiKTeX）迁移到像 Aspose.TeX 这样的托管式 .NET 库时，开发人员会经历一次根本性的转变：从“绑定于文件系统、由进程驱动”的执行模式，转向“灵活的、面向对象”的架构。

以下是原生引擎的局限性与 Aspose.TeX 所提供的托管灵活性之间的对比，旨在为技术文档和开发人员指南提供参考。

1. 文件系统与 I/O 架构

**原生 TeX 的局限性：**

- 传统的 TeX 引擎（如 pdfTeX 或 XeTeX）与本地文件系统紧密耦合。它们要求文件路径指向磁盘上的物理目录。
- 在服务器上执行原生进程时，往往需要授予对多个系统路径的读写权限。如果不可信的 `.tex` 输入试图进行目录遍历或访问受限的系统文件，这会带来安全漏洞。
- 若要将动态内容或存储在数据库中的 LaTeX 内容输入到原生 TeX 引擎中，必须先将其写入磁盘上的临时文件，这不仅产生了不必要的 I/O 开销，还增加了后续清理工作的复杂性。

**Aspose.TeX 的托管灵活性：**

- Aspose.TeX 通过 `IInputWorkingDirectory` 和 `IOutputWorkingDirectory` 接口，将引擎与物理磁盘路径隔离开来。
- 开发人员可以无缝地从内存流（Memory Streams）、ZIP 压缩包或自定义数据源中读取数据，并将结果写入其中，而无需触及本地磁盘。

2. 错误处理与服务器端执行

**原生 TeX 的局限性：**

- 当传统的 TeX 编译器遇到字体缺失、宏未定义或语法错误时，它不仅会崩溃，往往还会暂停执行并进入交互式提示符（interactive prompt）状态。这会导致后台 Web 应用程序或工作服务（worker services）陷入无限期挂起状态。

**Aspose.TeX 的托管灵活性：**

- Aspose.TeX 完全在 .NET 运行时中运行，它通过 `TeXJob.Run()` 返回的 `TeXJobResult` 值报告编译问题和缺失的依赖项，详细信息写入记录文件（`.log`）和输出终端。
- 将 `Interaction` 选项设置为 `NonstopMode` 或 `BatchMode` 后，作业不会等待用户输入，因此云函数、微服务和后台工作队列可以妥善处理格式错误的文档、记录错误并返回相应的 HTTP 状态码或错误消息，而不会锁定服务器线程。

3. 并发与线程安全

**原生 TeX 的局限性：**

- 标准的命令行（CLI）工具通常设计为单实例、顺序执行模式。若要实现并发运行，必须启动多个独立的操作系统级进程；这种方式计算开销巨大，且在高负载下难以扩展。

**Aspose.TeX 提供的灵活解决方案：**

- 由于 Aspose.TeX 将排版任务封装在独立的 `TeXJob` 和 `TeXOptions` 对象实例中，开发人员能够在多线程 .NET 环境下并发处理多个文档（需遵循常规的对象实例线程隔离规则）。