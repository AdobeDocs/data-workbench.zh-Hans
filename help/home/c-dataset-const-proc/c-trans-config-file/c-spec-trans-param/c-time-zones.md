---
description: Transformation.cfg 文件中的 Time Zone（时区）参数控制数据集配置文件中所有本地时间的时间维度、时间转换（例如，定义 x-local-timestring 字段）和格式设置。
solution: Analytics
title: 时区
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 时区{#time-zones}

Transformation.cfg 文件中的 Time Zone（时区）参数控制数据集配置文件中所有本地时间的时间维度、时间转换（例如，定义 x-local-timestring 字段）和格式设置。

>[!NOTE]
>
>“时区”参数不影响系统级功能，如状态中的时间戳和事件日志，这些功能以系统本地时间表示。

Time Zone（时区）参数支持以下与系统无关的时区格式（“协调世界时”）：

时区 = string: UTC +hhmm dstrules

符号 (+) 可以是加号 (+) 或减号 (-)，*hhmm* 是与 UTC 的时差（以小时和分钟为单位）。可选变量 *dstrules* 指定一组用于实施夏令时或类似时钟调整政策的规则。

如果指定 *dstrules*，则以制表符分隔的文件 [!DNL dstrules .dst] 必须位于数据集配置文件的 Dataset\TimeZone 子目录内。该文件为夏令时指定了一组与时区无关的规则。您在不同的年份会有不同的规则集。“基本”配置文件中由 Adobe 提供的 [!DNL DST.dst] 文件指定了根据 2005 年能源政策法案（从 2007 年开始生效）建立的标准美国规则，以及前些年的美国规则。

下面列出了“时区”的示例条目：

* 美国东部夏令时：时区 = string: UTC -0500 DST
* 没有时差和 dstrules 变量的 UTC 时间：时区 = string: UTC -0000

When this format is used, the system time zone of data workbench server, data workbench, and [!DNL Report] machines need not be the same as the specified time zone. 此外，Data Workbench Server 计算机上的所有活动数据集配置文件都不必具有相同的时区设置。

Adobe 建议不要在单个 Data Workbench Server 计算机或 Data Workbench Server 群集中运行多个数据集配置文件。

Data Workbench 用户将在数据集配置文件的时区中看到数据（而不是在他们的系统时区中）。Adobe 建议 Data Workbench Server 计算机的系统时区最好与其数据集中使用的时区相同。

>[!NOTE]
>
>You can specify a Time Zone parameter in the [!DNL Log Processing.cfg] file, where it is used for time conversions during log processing. 有关文件中“时区”参数的信息，请参 [!DNL Log Processing.cfg] 阅日志处 [理配置文件](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。
