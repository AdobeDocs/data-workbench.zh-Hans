---
description: 通过处理工作区并将其指定为报表来生成报表。
title: 生成报表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 生成报表{#generating-reports}

通过处理工作区并将其指定为报表来生成报表。

[!DNL Report] 按文件中参数中设 [!DNL Every] 置的间 [!DNL Report.cfg] 隔(如 [!DNL "day]“”，每天处理报告)生成报表，并基于其他文 [!DNL Report.cfg] 件设置。

生成报告时，完成百分比显示在特定报告的缩略图下的[!DNL Reports]选项卡上。 如果[!DNL Report]在生成报表时遇到问题，则报表集文件夹的[!DNL Reports]选项卡上会显示最新的错误消息。 如果[!DNL Report]确实遇到特定报表的错误，它将继续处理集中的其他报表。

可使用[!DNL Report.cfg]文件中的[!DNL Report Types]参数，以下列任何或所有格式生成报表集中的报表：

* Microsoft Excel文件（[!DNL .xls]或[!DNL .xlsx]）
* 可移植网络图形文件([!DNL .png])
* 缩略图([!DNL .jpg])

除指定的输出类型外，[!DNL Report]还会创建一个与您的报告同名的[!DNL .xml]文件。 此&#x200B;*`<report name>`*.xml文件包含报表的缩略图下方[!DNL Reports]选项卡的Data Workbench中显示的报表说明。 这样，在通过报告门户分发报表时，便可使用说明。 有关[!DNL Report Portal]的信息，请参阅[使用报告门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果重定义内部量度，则系统会因值错误而异常工作。 除非某个量度读取了 100% 数据，否则将不会生成报表。建议不要更改量度定义。
