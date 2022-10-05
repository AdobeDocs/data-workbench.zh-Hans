---
description: 通过处理工作区并将其指定为报表来生成报表。
title: 生成报表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 生成报表{#generating-reports}

{{eol}}

通过处理工作区并将其指定为报表来生成报表。

[!DNL Report] 会按 [!DNL Every] 参数 [!DNL Report.cfg] 文件(例如 [!DNL "day]”，该报表每天处理报告)，并基于其他 [!DNL Report.cfg] 文件设置。

在生成报表时，完成百分比会显示在 [!DNL Reports] 选项卡。 如果 [!DNL Report] 在生成报表时遇到问题，最近的错误消息会显示在 [!DNL Reports] 选项卡。 如果 [!DNL Report] 确实会遇到特定报表的错误，它会继续处理集中的其他报表。

您可以使用以下任意或全部格式在报表集中生成报表 [!DNL Report Types] 参数 [!DNL Report.cfg] 文件：

* Microsoft Excel文件( [!DNL .xls] 或 [!DNL .xlsx])
* 可移植网络图形文件( [!DNL .png])
* 缩略图( [!DNL .jpg])

除了指定的输出类型外， [!DNL Report] 创建 [!DNL .xml] 与报表名称相同的文件。 此 *`<report name>`*.xml文件包含报表的描述，该描述以Data Workbench显示在 [!DNL Reports] 选项卡。 这样，在通过报表门户分发报表时，便可使用该描述。 有关 [!DNL Report Portal]，请参阅 [使用报表门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>如果重定义内部量度，则系统会因错误值而异常运行。 除非某个量度读取了 100% 数据，否则将不会生成报表。建议不要更改量度定义。
