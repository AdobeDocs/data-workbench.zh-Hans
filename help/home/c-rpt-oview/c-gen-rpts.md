---
description: 通过处理工作区并将其指定为报告，生成报告。
solution: Analytics
title: 生成报告
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 生成报告{#generating-reports}

通过处理工作区并将其指定为报告，生成报告。

[!DNL Report] 以文件中参数中设置的间 [!DNL Every] 隔( [!DNL Report.cfg] 如 [!DNL "day]，每天处理报告)，并基于其他文件设置生成报 [!DNL Report.cfg] 告。

生成报告时，该特定报告的缩略图下方的 [!DNL Reports] 选项卡上会显示完成百分比。 如 [!DNL Report] 果在生成报表时遇到问题，则报表集文件夹中的 [!DNL Reports] 选项卡上会显示最近的错误消息。 如果 [!DNL Report] 某个特定报表确实遇到错误，它会继续处理该集中的其他报表。

您可以使用文件中的参数，以下列任何或所有格式在报表集中生成 [!DNL Report Types] 报表 [!DNL Report.cfg] :

* Microsoft Excel文件( [!DNL .xls] 或 [!DNL .xlsx])
* 便携式网络图形文件( [!DNL .png])
* 缩略图( [!DNL .jpg])

除了指定的输出类型之外，还 [!DNL Report] 会创建 [!DNL .xml] 一个与报告同名的文件。 此 *`<report name>`*.xml文件包含报表描述，该描述显示在报表缩略图下方的 [!DNL Reports] 选项卡上的Data Workbench中。 这样，在通过报告门户分发报告时，可以使用描述。 有关的信息，请参 [!DNL Report Portal]阅使 [用报告门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果重定义内部度量，则系统会因值错误而意外行为。 除非指标为100%，否则您的报告将不会生成。 建议您不要更改度量定义。
