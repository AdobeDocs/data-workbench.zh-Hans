---
description: 调整DPU性能的说明。
title: DPU 性能设置
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# DPU 性能设置{#dpu-performance-settings}

调整DPU性能的说明。

在* [!DNL Insight Server]安装目录*\Components\DPU.cfg文件中填写以下参数。

| 参数 | 描述 |
|---|---|
| 执行批次计数 | 这是一个调整参数。 默认值为 65536。您可以指定任意小的执行批次计数。 请在更改此值之前与Adobe联系。 |
| 执行批 | 这是一个调整参数。 默认值为 128。请在更改此值之前与Adobe联系。 |
| 执行时间 | 这是一个调整参数。 默认值为0.100。请在对此值进行任何更改之前与Adobe联系。 |
| 出错时转储字段 | 此参数可以设置为true或false。 如果设置为true，则每当执行引擎出错时，[!DNL Insight Server]会在其“跟踪”目录中创建名为[!DNL Field Dump number.txt]的文件。 [!DNL Field Dump] &lt;[!DNL number]> [!DNL .txt]对于故障排除很有用。 |
| 用户档案路径 | 存储所有用户档案文件的位置。 默认位置为用户档案\。 |
| 查询内存限制 | [!DNL Insight Server]保留用于存储查询结果的内存量（以字节为单位）。 默认值为100000000(100MB)。 如果需要更多空间用于查询结果（例如，允许更多同时使用户），可以增加设置，但必须继续检查[!DNL Insight Server’s]内存负载。 |
| 状态路径 | 系统状态文件的位置。 默认位置为State\。 |
| 线程 | 具有多个处理器的[!DNL Insight Server]计算机的性能调整参数。 通常，对于任何n核系统，此值应设置为n。默认值为1。 |
| 用户路径 | 授权用户文件的位置。 默认位置为“用户”。 |
