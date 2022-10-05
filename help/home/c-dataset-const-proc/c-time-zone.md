---
description: 关于时区代码和格式的信息。
title: 时区代码和格式
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 70%

---

# 时区代码{#time-zone-codes}

{{eol}}

关于时区代码和格式的信息。

Data Workbench Server 中大部分基于时间的参数都采用以下格式指定：

* Month DD, YYYY HH:MM:SS TZone
* 示例：2013年8月13日22:30:东部标准时间00

时区是采用以下与系统无关的时区格式（“协调世界时”）表示的：

* UTC +hhmm dstrules

符号 (+) 可以是加号 (+) 或减号 (-)，hhmm 是与 UTC 的时差（以小时和分钟为单位）。可选变量 dstrules 指定一组用于实施夏令时或类似时钟调整政策的规则。

如果指定dstrules，则以制表符分隔的文件名为 [!DNL dstrules.dst] 必须位于 [!DNL Base] 配置文件（用于未与特定数据集关联的配置文件）或数据集配置文件（用于特定于数据集的配置文件）。 该文件为夏令时指定了一组与时区无关的规则。您在不同的年份会有不同的规则集。的 [!DNL DST.dst] 文件由Adobe在 [!DNL Base] 用户档案指定了2005年《能源政策法》（从2007年开始生效）所确立的美国标准规则以及美国以前年份的规则。

下面列出了“时区”的示例条目：

* 美国东部夏令时：时区 = string: UTC -0500 DST
* 无时差和无 dstrules 的 UTC 时间（与 GMT 对应）：时区 = string: UTC -0000

使用此格式时，Data Workbench Server、Data Workbench 和报表计算机的系统时区都不需要与指定时区相同。此外，Data Workbench Server 计算机上的所有活动数据集配置文件都不必具有相同的时区设置。

下表包含可用于在基于时间的参数中指定时区的代码列表。

## 时区代码表 {#section-b4f965b872c543e2ac52a3c94410d076}

如果您实施夏令时或类似的时钟调整策略，则必须保存 [!DNL .dst] 包含配置文件名称中相应规则的文件 [!DNL \Dataset\Timezone] data workbench server计算机上的目录。

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
