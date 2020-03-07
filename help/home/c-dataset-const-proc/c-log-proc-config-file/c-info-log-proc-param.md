---
description: 指向有关 Log Processing.cfg 文件中特定参数的其他信息的链接。
solution: Analytics
title: 日志处理参数
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 日志处理参数{#log-processing-parameters}

指向有关 Log Processing.cfg 文件中特定参数的其他信息的链接。

<!--
c_data_filters.xml
-->

## Data filters {#data-filters}

[!DNL Log Processing.cfg] 文件中定义的过滤器包括以下各项：

* End Time（结束时间）
* Hash Threshold（哈希阈值）
* Start Time（开始时间）

The filtering defined by these parameters occurs after log entries leave the decoders and after transformations but before their evaluation by the [!DNL Log Entry Condition]. 通常情况下，更改这些参数中的任何一个都会导致数据集的组成发生变化。

The recommended technique for using [!DNL Sensor] data sources to construct a dataset that covers a specific period of time is to use the Start Time and End Time parameters for the dataset.

使用 Start Time（开始时间）和 End Time（结束时间）参数要优于使用其他方法（例如移动日志文件以按目录将它们分隔开）。通过设置数据集的开始时间和结束时间，Data Workbench Server 可自动仅使用那些在给定时间间隔内发生的日志条目。假定结束时间为过去的时间，Data Workbench Server 通常会使用相同的日志条目集来更新数据集，即使对于通过添加新转换更新的数据集也是如此。

<!--
c_log_entry_con.xml
-->

## 日志条目

从本质上讲，这是一个对可用日志条目进行过滤的过程。If the [!DNL Log Entry Condition] returns a value of false, the log entry is filtered out of the available set of log entries.

通过 [!DNL Log Entry Condition] 使用条件操作(请参阅 [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md))描述该问题，并可以使用由(请参阅 [!DNL Sensor] Data Workbench *Guide[!DNL Sensor]*[!DNL Log Processing.cfg] )收集的任何输入字段或文件中包含的转换生成的任何扩展字段来定义测试条件。 [!DNL Log Entry] 条件在日志处理期间应用，也可以在转换期间应用。

This example demonstrates the use of the [!DNL log entry condition] for website data. You can use the [!DNL Log Entry Condition] to create datasets that focus on a specific portion of the website or visitors performing some specific action on the site.

The [!DNL Log Entry Condition] in this example creates a dataset that includes only those log entries that are part of the site&#39;s store. 通过使用 [!DNL RECondition test] 匹配模式和字段 [!DNL "/store/.*"] 作为正则 [!DNL cs-uri-stem] 表达式的输入，数据集中只包含以字符串开头的 [!DNL "/store/"] 网页。

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## 密钥拆分 {#key-split}

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

[!DNL Group Maximum Key Bytes] 指定可为单个跟踪ID处理的事件数据的最大数量。 超过此限制的数据会被数据集构建过程过滤出去。[!DNL Split Key Bytes]（拆分键字节数）表示单个跟踪 ID 拆分为多个元素时依据的字节数。系统会根据概率分布大约按此字节数对元素进行拆分。[!DNL Split Key Space Ratio] 并控 [!DNL Split Key Bucket Space] 制密钥分割的内存利用和故障率。

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes]、 [!DNL Split Key Bytes]、 [!DNL Split Key Space Ratio]和 [!DNL Split Key Bucket Space] all必须声明才能正常使用键拆分。 在未咨询 Adobe 的情况下，请不要随便更改这些参数的值。

