---
description: 在生成报表后，报表会根据其Report.cfg文件中的设置来分发集中的报表。
title: 分发报表
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# 分发报表{#distributing-reports}

{{eol}}

在生成报表后，报表会根据其Report.cfg文件中的设置来分发集中的报表。

[!DNL Report] 允许您使用以下方法在报表集中分发报表：

* **电子邮件：** 要将报表作为Excel文件分发， [!DNL .png] 文件或通过电子邮件（内嵌或作为附件）显示的缩略图，请在报表集的 [!DNL Report.cfg] 文件。 该集中的所有报表都将通过电子邮件发送给指定收件人。

* **共享目录：** 要将报表作为Excel文件分发， [!DNL .png] 文件或缩览图到共享目录，请在报表集的“输出根”参数中指定目录 [!DNL Report.cfg] 文件。

* **报表门户：** 报表门户允许您通过Web浏览器查看报表。 Adobe [!DNL Report Portal] 显示以Excel或 [!DNL .png] 文件，但不是作为缩略图生成的文件( [!DNL .jpg])。 要将报表分发到门户，请在报表集的“输出根”参数中指定用于该门户的Web服务器的文档根 [!DNL Report.cfg] 文件。 有关安装和使用的更多信息 [!DNL Report Portal]，请参阅 [使用报表门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>读取当前支持的输出 [!DNL Report]，则必须具有能够以所需格式显示报表的应用程序。 例如，要查看 [!DNL .xlsx] 文件，则必须具有Microsoft Excel 2007或更高版本。

您还可以使用这些生成和分发选项的组合。 例如，如果您将 [!DNL Report Types] 用于生成报表集的参数，以及 [!DNL .png] 文件，然后设置 [!DNL Mail Report]和 [!DNL Output Root] 参数中，该集中的所有报表都将分发到指定的输出目录（可能可在门户中查看），并通过电子邮件发送给收件人。

有关配置报表集的步骤，请参阅 [使用报表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). 有关特定 [!DNL Report.cfg] 参数，请参阅 [Report.cfg参数](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
