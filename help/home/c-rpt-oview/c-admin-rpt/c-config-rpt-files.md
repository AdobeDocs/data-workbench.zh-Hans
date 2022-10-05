---
description: 在报表门户中，您可以以Excel文件(.xls或.xlsx)或.png文件的形式查看由报表服务器生成的报表。
title: 配置 Report.cfg 文件
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# 配置 Report.cfg 文件{#configuring-report-cfg-files}

{{eol}}

在报表门户中，您可以以Excel文件(.xls或.xlsx)或.png文件的形式查看由报表服务器生成的报表。

在 [!DNL Report Portal]，则必须在 [!DNL Report.cfg] 文件：

* 在 **[!UICONTROL Output Root]** 参数，指定用于门户的web服务器的文档根目录。
* 在 **[!UICONTROL Report Types]** 参数，指定Excel、png和/或缩略图作为要生成的报表类型。

When [!DNL Report Server] 会以您指定的格式生成报表，它会将这些文件放置到web服务器的文档根目录中，在安装过程中，您可以在该目录中配置 [!DNL Report Portal] 以访问报告。

有关特定 [!DNL Report.cfg] 参数，请参阅 [Report.cfg参数](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
