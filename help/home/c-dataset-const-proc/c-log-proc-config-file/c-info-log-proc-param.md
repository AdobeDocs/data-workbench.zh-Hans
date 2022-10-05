---
description: 指向有关 Log Processing.cfg 文件中特定参数的其他信息的链接。
title: 日志处理参数
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 64%

---

# 日志处理参数{#log-processing-parameters}

{{eol}}

指向有关 Log Processing.cfg 文件中特定参数的其他信息的链接。

<!--
c_data_filters.xml
-->

## 数据过滤器 {#data-filters}

[!DNL Log Processing.cfg] 文件中定义的过滤器包括以下各项：

* End Time（结束时间）
* Hash Threshold（哈希阈值）
* Start Time（开始时间）

由这些参数定义的过滤发生在日志条目离开解码器之后、转换之后，但在由 [!DNL Log Entry Condition]. 通常情况下，更改这些参数中的任何一个都会导致数据集的组成发生变化。

使用的推荐技术 [!DNL Sensor] 数据源构建涵盖特定时间段的数据集，即为数据集使用“开始时间”和“结束时间”参数。

使用 Start Time（开始时间）和 End Time（结束时间）参数要优于使用其他方法（例如移动日志文件以按目录将它们分隔开）。通过设置数据集的开始时间和结束时间，Data Workbench Server 可自动仅使用那些在给定时间间隔内发生的日志条目。假定结束时间为过去的时间，Data Workbench Server 通常会使用相同的日志条目集来更新数据集，即使对于通过添加新转换更新的数据集也是如此。

<!--
c_log_entry_con.xml
-->

## 日志条目

从本质上讲，这是一个对可用日志条目进行过滤的过程。如果 [!DNL Log Entry Condition] 返回值false时，日志条目会从可用的日志条目集中过滤掉。

的 [!DNL Log Entry Condition] 通过使用条件运算进行描述(请参阅 [条件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md))，并可以使用收集的任何输入字段 [!DNL Sensor] (请参阅 *Data Workbench [!DNL Sensor] 指南* )或由包含在 [!DNL Log Processing.cfg] 文件来定义测试条件。 [!DNL Log Entry] 条件在日志处理期间应用，也可以在转换期间应用。

此示例演示了如何使用 [!DNL log entry condition] 网站数据。 您可以使用 [!DNL Log Entry Condition] 创建数据集，以重点关注网站的特定部分或对网站执行某些特定操作的访客。

的 [!DNL Log Entry Condition] 在此示例中，创建一个数据集，该数据集仅包含那些属于网站存储的日志条目。 通过使用 [!DNL RECondition test] 匹配模式 [!DNL "/store/.*"] 和 [!DNL cs-uri-stem] 字段作为正则表达式的输入，仅以字符串开头的网页 [!DNL "/store/"] 包含在数据集中。

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## 键拆分 {#key-split}

数据集中跟踪 ID 的数量进行了人为增加，但 Data Workbench Server 处理的日志条目总数并未人为增加，从而保持数据集中的可计算事件的总数不变。在拆分单个元素的数据之后，该数据会永远与两个不同的跟踪 ID 关联，但它们彼此却无法相关。

例如，如果您要处理 Web 数据，则每个跟踪 ID 都表示一个唯一的访客。如果启用键拆分功能，则数据集中具有大量事件数据的访客会被拆分为多个访客。数据集中的访客数量进行了人为增加，而可计算事件（例如页面查看或预订）的总数并未人为增加。进行拆分之后，子访客的数据便无法相关。

键拆分使用概率算法。因此，在内存使用率、失败概率、键拆分阈值（[!DNL Split Key Bytes]（拆分键字节数））和数据集大小之间会进行适度平衡。如果使用建议的设置（如下所列），则失败率会很低。在事件数据超出键拆分阈值的元素中，每 22,000 个元素中大约有 1 个（通常每个数据集不超过 1 个）会截断部分数据，而不是进行拆分。

下表中显示了每个参数的建议值（不使用键拆分和使用键拆分）。

| 参数 | 不使用键拆分 | 键拆分 |
|---|---|---|
| Group Maximum Key Bytes（组最大键字节数） | 1e6 | 2e6 |
| Split Key Bucket Space（拆分键存储段空间） | 6e6 | 6e6 |
| Split Key Bytes（拆分键字节数） | 0 | 1e6 |
| Split Key Space Ratio（拆分键空间比率） | 10 | 10 |

[!DNL Group Maximum Key Bytes] 指定可针对单个跟踪ID处理的事件数据的最大数量。 超过此限制的数据会被数据集构建过程过滤出去。[!DNL Split Key Bytes]（拆分键字节数）表示单个跟踪 ID 拆分为多个元素时依据的字节数。系统会根据概率分布大约按此字节数对元素进行拆分。[!DNL Split Key Space Ratio] 和 [!DNL Split Key Bucket Space] 控制密钥拆分的内存使用率和失败率。

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]和 [!DNL Split Key Bucket Space] 必须声明全部，密钥拆分才能正常工作。 在未咨询 Adobe 的情况下，请不要随便更改这些参数的值。
