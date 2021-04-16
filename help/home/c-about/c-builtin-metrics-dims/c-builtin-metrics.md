---
description: Data Workbench包含内置量度。
title: 内置量度
uuid: 1e4d91dc-0130-4296-8395-fd2ddb03f6ef
exl-id: a8a2a8dd-dc13-4eb3-92ce-09f02252ecf0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---

# 内置量度{#built-in-metrics}

Data Workbench包含内置量度。

下表列表了Data Workbench的可用内置量度：

| 内置量度 | 描述 |
|---|---|
| 截至 | 自1600年1月1日00:00 UTC以来，以100纳秒间隔显示的数据集的截止时间。 As Of时间戳是数据集中已绝对处理所有数据的最新时间。 |
| 读取日志字节 | 在日志处理阶段迄今已处理的压缩数据的总量（以字节为单位）。 |
| 日志字节总数 | 与配置的日志源标准以及数据集的开始和结束日期范围相匹配的日志文件中的压缩数据总量（以字节为单位）。 如果日志处理模式配置文件中暂停了日志处理，则日志字节总数将与日志字节读取相同。 |
| 日志处理进度 | Insight Server数据处理的日志处理阶段完成百分比。 |
| 解码日志条目总数 | 作为Insight Server数据处理日志处理阶段的一部分成功解码的日志文件中的条目数。 |
| 筛选日志条目总数 | 在解码后，日志文件中的条目数被自动过滤器接受，日志条目条件和作为Insight Server数据处理的日志处理阶段的一部分应用的其他过滤器。 |
| 日志条目总数 | 日志文件中迄今已经由Insight Server数据处理的日志处理阶段处理的条目数。 |
| 已处理日志条目总数 | 已并入Adobe数据集的已过滤日志条目数。 |
| 转换进度 | Insight Server数据处理的转换阶段完成百分比。 |
| 未压缩日志字节读取 | 在日志处理阶段迄今已处理的未压缩数据的总量（以字节为单位）。 |
