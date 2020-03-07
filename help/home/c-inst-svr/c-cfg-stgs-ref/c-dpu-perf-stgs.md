---
description: 调整DPU性能的说明。
solution: Insight
title: DPU性能设置
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DPU性能设置{#dpu-performance-settings}

调整DPU性能的说明。

在*安装目录*\Components\DPU.cfg文件中 [!DNL Insight Server] 完成以下参数。

| 参数 | 描述 |
|---|---|
| 执行批次计数 | 这是一个调整参数。 默认值为 65536。您可以指定任意小的执行批次计数。 请在对此值进行任何更改之前与Adobe联系。 |
| 执行批 | 这是一个调整参数。 默认值为 128。请在对此值进行任何更改之前与Adobe联系。 |
| 执行时间 | 这是一个调整参数。 默认值为0.100。请在对此值进行任何更改之前与Adobe联系。 |
| 出错时字段转储 | 此参数可以设置为true或false。 如果设置为true，则每当 [!DNL Insight Server] 执行引擎出错时，都 [!DNL Field Dump number.txt] 会在其Trace目录中创建一个名为的文件。 &lt; [!DNL Field Dump] > [!DNL number]对于疑难 [!DNL .txt] 排解很有用。 |
| 配置文件路径 | 存储所有配置文件的位置。 默认位置为Profiles\。 |
| 查询内存限制 | 保留用于存储查询结果的内 [!DNL Insight Server] 存量（以字节为单位）。 默认值为100000000(100MB)。如果查询结果需要更多空间（例如，允许更多同时使用户），则可以增加设置，但您必须继续检查内存 [!DNL Insight Server’s] 负载。 |
| 状态路径 | 系统状态文件的位置。 默认位置为“状态”。 |
| 线程 | 具有多个处理器的 [!DNL Insight Server] 计算机的性能调整参数。 通常，对于任何n核系统，此值应设置为n。默认值为1。 |
| 用户路径 | 授权用户文件的位置。 默认位置为“用户”。 |

