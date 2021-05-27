---
description: 通过处理工作区并将其指定为报表来生成报表。
title: 生成报表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 生成报表{#generating-reports}

通过处理工作区并将其指定为报表来生成报表。

[!DNL Report] 会根据其他文件设置， [!DNL Every] 按文件 [!DNL Report.cfg] 参数中设置的间隔(例如 [!DNL "day]”，该参数每天处理报表)生成 [!DNL Report.cfg] 报表。

在生成报表时，完成百分比会显示在该特定报表的缩略图下的[!DNL Reports]选项卡中。 如果[!DNL Report]在报告生成过程中遇到问题，则最新的错误消息会显示在报表集文件夹的[!DNL Reports]选项卡上。 如果[!DNL Report]确实遇到特定报表的错误，它会继续处理集中的其他报表。

您可以使用[!DNL Report.cfg]文件中的[!DNL Report Types]参数，以以下任何或所有格式在报表集中生成报表：

* Microsoft Excel文件（[!DNL .xls]或[!DNL .xlsx]）
* 可移植网络图形文件([!DNL .png])
* 缩略图([!DNL .jpg])

除了指定的输出类型外， [!DNL Report]还会创建一个与报表相同的[!DNL .xml]文件。 此&#x200B;*`<report name>`*.xml文件包含报表描述，该描述以Data Workbench显示在报表缩略图下方的[!DNL Reports]选项卡上。 这样，在通过报表门户分发报表时，便可使用该描述。 有关[!DNL Report Portal]的信息，请参阅[使用报表门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果重定义内部量度，则系统会因值错误而异常运行。 除非某个量度读取了 100% 数据，否则将不会生成报表。建议不要更改量度定义。
