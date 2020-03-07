---
description: 设置Insight Server中基于时间的参数的格式说明。
solution: Insight
title: 时区代码
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 时区代码{#time-zone-codes}

设置Insight Server中基于时间的参数的格式说明。

[!DNL Insight Server] 中大部分基于时间的参数都采用以下格式指定：

*月DD,YYYY HH:MM:SS TimeZone*

示例：August 13, 2013 22:30:00 EST

时区是采用以下与系统无关的时区格式（“协调世界时”）表示的：

UTC +hhmm *dstrules*

符号 (+) 可以是加号 (+) 或减号 (-)，*hhmm* 是与 UTC 的时差（以小时和分钟为单位）。可选变量 *dstrules* 指定一组用于实施夏令时或类似时钟调整政策的规则。

If you specify *dstrules*, a tab-delimited file named *&lt;[!DNL dstrules]>* [!DNL .dst] must be present within the Dataset\TimeZone directory of either the Base profile (for configuration files that are not associated with a particular dataset) or the dataset profile (for configuration files that are dataset-specific). 该文件为夏令时指定了一组与时区无关的规则。您在不同的年份会有不同的规则集。“基本”配置文件中由 Adobe 提供的 [!DNL DST.dst] 文件指定了根据 2005 年能源政策法案（从 2007 年开始生效）建立的标准美国规则，以及前些年的美国规则。

下面列出了“时区”的示例条目：

* 美国东部夏令时：时区 = string: UTC -0500 DST
* UTC time with no offset and no *dstrules* (corresponding to GMT): Time Zone = string: UTC -0000

When this format is used, the system time zone of [!DNL Insight Server], [!DNL Insight], and [!DNL Report] machines need not be the same as the specified time zone. 此外，[!DNL Insight Server] 计算机上的所有活动数据集配置文件都不必具有相同的时区设置。

下表包含可用于在基于时间的参数中指定时区的代码列表。

## 时区代码表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>If you are implementing Daylight Saving Time or a similar clock-shifting policy, you must save the [!DNL .dst] file containing the appropriate rules in the *profile name*\Dataset\Timezone directory on the [!DNL Insight Server] machine.

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

