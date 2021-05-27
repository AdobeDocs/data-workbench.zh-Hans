---
description: 在生成报表后，报表会根据其Report.cfg文件中的设置来分发集中的报表。
title: 分发报表
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# 分发报表{#distributing-reports}

在生成报表后，报表会根据其Report.cfg文件中的设置来分发集中的报表。

[!DNL Report] 允许您使用以下方法在报表集中分发报表：

* **电子邮件：** 要通过电子邮件(内 [!DNL .png] 联或作为附件)将报表分发为Excel文件、文件或缩略图，请在报表集的文件中指定“邮件报表” [!DNL Report.cfg] 参数。该集中的所有报表都将通过电子邮件发送给指定收件人。

* **共享目录：** 要将报表作为Excel文件、文 [!DNL .png] 件或缩略图分发到共享目录，请在报表集文件的“输出根”参数中指定 [!DNL Report.cfg] 目录。

* **报表门户：** 报表门户允许您通过Web浏览器查看报表。Adobe的[!DNL Report Portal]显示以Excel或[!DNL .png]文件生成的报表，但不显示以缩略图([!DNL .jpg])生成的报表。 要将报表分发到门户，请在报表集[!DNL Report.cfg]文件的“输出根”参数中指定用于该门户的Web服务器的文档根。 有关安装和使用[!DNL Report Portal]的更多信息，请参阅[使用报表门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>要读取[!DNL Report]当前支持的输出，您必须具有能够以所需格式显示报表的应用程序。 例如，要查看[!DNL .xlsx]文件，您必须安装Microsoft Excel 2007或更高版本。

您还可以使用这些生成和分发选项的组合。 例如，如果您设置[!DNL Report Types]参数以生成作为Excel和[!DNL .png]文件的报表集，然后设置[!DNL Mail Report]和[!DNL Output Root]参数，则该集中的所有报表都将分发到指定的输出目录（可能可在门户中查看），并通过一封电子邮件发送给收件人。

有关配置报表集的步骤，请参阅[使用报表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 有关特定[!DNL Report.cfg]参数的更多信息，请参阅[Report.cfg参数](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
