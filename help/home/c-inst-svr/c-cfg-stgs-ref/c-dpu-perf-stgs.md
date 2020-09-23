---
description: 调整DPU性能的说明。
solution: Analytics
title: DPU 性能设置
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---


# DPU 性能设置{#dpu-performance-settings}

调整DPU性能的说明。

在*安装目录*\Components\DPU.cfg文件 [!DNL Insight Server] 中完成以下参数。

| 参数 | 描述 |
|---|---|
| 执行批次计数 | 这是一个调整参数。 默认值为 65536。您可以指定任意小的执行批次计数。 请与Adobe联系，然后再对此值进行任何更改。 |
| 执行批 | 这是一个调整参数。 默认值为 128。请与Adobe联系，然后再对此值进行任何更改。 |
| 执行时间 | 这是一个调整参数。 默认值为0.100。请在对此值进行任何更改之前与Adobe联系。 |
| 出错时字段转储 | 此参数可设置为true或false。 如果设置为true, [!DNL Insight Server] 则每当执行引 [!DNL Field Dump number.txt] 擎出错时都在其Trace目录中创建一个名为的文件。 &lt;> [!DNL Field Dump] 对 [!DNL number]于疑难 [!DNL .txt] 排解非常有用。 |
| 用户档案路径 | 存储所有用户档案文件的位置。 默认位置为用户档案\。 |
| 查询内存限制 | 保留存储查询结果的内 [!DNL Insight Server] 存量（以字节为单位）。 默认值为100000000(100MB)。 如果需要更多空间来查询结果（例如，允许更多同时使用的用户），则可以增加设置，但您必须继续检查内存 [!DNL Insight Server’s] 负载。 |
| 状态路径 | 系统状态文件的位置。 默认位置为State\。 |
| 线程 | 具有多个处理器的 [!DNL Insight Server] 计算机的性能调整参数。 通常，对于任何n核系统，此值应设置为n。默认值为1。 |
| 用户路径 | 授权用户文件的位置。 默认位置为“用户”。 |

