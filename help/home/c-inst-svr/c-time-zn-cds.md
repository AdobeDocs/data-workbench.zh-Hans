---
description: 有关Insight Server中基于时间的参数的格式说明。
title: 时区代码
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 62%

---

# 时区代码{#time-zone-codes}

有关Insight Server中基于时间的参数的格式说明。

[!DNL Insight Server] 中大部分基于时间的参数都采用以下格式指定：

*月DD，YYYY HH:MM:SS时区*

示例：August 13, 2013 22:30:00 EST

时区是采用以下与系统无关的时区格式（“协调世界时”）表示的：

UTC +hhmm *dstrules*

符号 (+) 可以是加号 (+) 或减号 (-)，*hhmm* 是与 UTC 的时差（以小时和分钟为单位）。可选变量 *dstrules* 指定一组用于实施夏令时或类似时钟调整政策的规则。

如果指定&#x200B;*dstrules*，则名为&#x200B;*[!DNL dstrules]>* [!DNL .dst]的制表符分隔文件必须存在于基本配置文件（对于未与特定数据集关联的配置文件）或数据集配置文件（对于特定于数据集的配置文件）的Dataset\TimeZone目录中。 该文件为夏令时指定了一组与时区无关的规则。您在不同的年份会有不同的规则集。“基本”配置文件中由 Adobe 提供的 [!DNL DST.dst] 文件指定了根据 2005 年能源政策法案（从 2007 年开始生效）建立的标准美国规则，以及前些年的美国规则。

下面列出了“时区”的示例条目：

* 美国东部夏令时：时区 = string: UTC -0500 DST
* 没有偏移和&#x200B;*dstrules*&#x200B;的UTC时间（对应于GMT）：时区=字符串：UTC -0000

使用此格式时，[!DNL Insight Server]、[!DNL Insight]和[!DNL Report]计算机的系统时区不需要与指定时区相同。 此外，[!DNL Insight Server] 计算机上的所有活动数据集配置文件都不必具有相同的时区设置。

下表包含可用于在基于时间的参数中指定时区的代码列表。

## 时区代码表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>如果要实施夏令时或类似的时钟调整策略，则必须在&#x200B;*配置文件名称*\Dataset\Timezone directory on the [!DNL Insight Server]计算机中保存包含相应规则的[!DNL .dst]文件。

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
