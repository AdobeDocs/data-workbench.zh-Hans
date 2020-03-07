---
description: 在Report Portal中，可以将Report Server生成的报表查看为Excel文件（.xls或。xlsx）或。png文件。
solution: Analytics
title: 配置Report.cfg文件
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置Report.cfg文件{#configuring-report-cfg-files}

在Report Portal中，可以将Report Server生成的报表查看为Excel文件（.xls或。xlsx）或。png文件。

要在中显示报表集， [!DNL Report Portal]必须在该报表集的文件中设置 [!DNL Report.cfg] 以下参数：

* 在参 **[!UICONTROL Output Root]** 数中，指定用于门户的Web服务器的文档根目录。
* 在参 **[!UICONTROL Report Types]** 数中，指定Excel、png和／或缩略图作为要生成的报表类型。

以您 [!DNL Report Server] 指定的格式生成报表时，会将这些文件放在Web服务器的文档根目录中，在安装过程中，您将配置访问报 [!DNL Report Portal] 表的位置。

有关特定参数的更 [!DNL Report.cfg] 多信息，请参 [阅Report.cfg参数](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
