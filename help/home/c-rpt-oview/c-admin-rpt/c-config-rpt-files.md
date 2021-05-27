---
description: 在报表门户中，您可以以Excel文件(.xls或.xlsx)或.png文件的形式查看由报表服务器生成的报表。
title: 配置 Report.cfg 文件
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# 配置 Report.cfg 文件{#configuring-report-cfg-files}

在报表门户中，您可以以Excel文件(.xls或.xlsx)或.png文件的形式查看由报表服务器生成的报表。

要在[!DNL Report Portal]中显示报表集，必须在该报表集的[!DNL Report.cfg]文件中设置以下参数：

* 在&#x200B;**[!UICONTROL Output Root]**&#x200B;参数中，指定用于门户的Web服务器的文档根目录。
* 在&#x200B;**[!UICONTROL Report Types]**&#x200B;参数中，将Excel、png和/或缩略图指定为要生成的报表类型。

当[!DNL Report Server]以您指定的格式生成报表时，它会将这些文件放在Web服务器的文档根目录中，在安装过程中，您可以配置[!DNL Report Portal]以访问报表。

有关特定[!DNL Report.cfg]参数的更多信息，请参阅[Report.cfg参数](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
