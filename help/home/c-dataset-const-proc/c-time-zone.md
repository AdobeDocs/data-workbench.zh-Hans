---
description: 关于时区代码和格式的信息。
title: 时区代码
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 72%

---

# 时区代码{#time-zone-codes}

关于时区代码和格式的信息。

Data Workbench Server 中大部分基于时间的参数都采用以下格式指定：

* Month DD, YYYY HH:MM:SS TZone
* 示例：August 13, 2013 22:30:00 EST

时区是采用以下与系统无关的时区格式（“协调世界时”）表示的：

* UTC +hhmm dstrules

符号 (+) 可以是加号 (+) 或减号 (-)，hhmm 是与 UTC 的时差（以小时和分钟为单位）。可选变量 dstrules 指定一组用于实施夏令时或类似时钟调整政策的规则。

如果指定dstrules，则[!DNL Base]配置文件的Dataset\TimeZone目录（对于未与特定数据集关联的配置文件）或数据集配置文件（对于特定于数据集的配置文件）中必须存在名为[!DNL dstrules.dst]的制表符分隔文件。 该文件为夏令时指定了一组与时区无关的规则。您在不同的年份会有不同的规则集。[!DNL Base]配置文件中由Adobe提供的[!DNL DST.dst]文件指定了2005年《能源政策法案》（自2007年起生效）所确立的标准美国规则以及前几年的美国规则。

下面列出了“时区”的示例条目：

* 美国东部夏令时：时区 = string: UTC -0500 DST
* 无时差和无 dstrules 的 UTC 时间（与 GMT 对应）：时区 = string: UTC -0000

使用此格式时，Data Workbench Server、Data Workbench 和报表计算机的系统时区都不需要与指定时区相同。此外，Data Workbench Server 计算机上的所有活动数据集配置文件都不必具有相同的时区设置。

下表包含可用于在基于时间的参数中指定时区的代码列表。

## 时区代码表 {#section-b4f965b872c543e2ac52a3c94410d076}

如果您要实施夏令时或类似的时钟调整策略，则必须在Data Workbench Server计算机的配置文件名称[!DNL \Dataset\Timezone]目录中保存包含相应规则的[!DNL .dst]文件。

| 代码 | 时区 | 与 GMT 的时差 |
|---|---|---|
| gmt | 格林威治标准时间 | 0 |
| est | 东部标准时间 | 5 |
| edt | 东部夏令时 | 5 |
| cst | 中部标准时间 | 6 |
| cdt | 中部夏令时 | 6 |
| mst | 山地标准时间 | 7 |
| mdt | 山地夏令时 | 7 |
| pst | 太平洋标准时间 | 8 |
| pdt | 太平洋夏令时 | 8 |
