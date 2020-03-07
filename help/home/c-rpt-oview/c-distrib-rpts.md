---
description: 生成报告后，Report会根据其Report.cfg文件中的设置分发该集中的报告。
solution: Analytics
title: 分发报告
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 分发报告{#distributing-reports}

生成报告后，Report会根据其Report.cfg文件中的设置分发该集中的报告。

[!DNL Report] 允许您使用以下方法在集中分发报表：

* **电子邮件：** 要通过电子邮件( [!DNL .png] 串联或附件)将报表分发为Excel文件、文件或缩略图，请在报表集的文件中指定“邮件报表”参 [!DNL Report.cfg] 数。 该集中的所有报告都通过电子邮件发送给指定收件人。

* **共享目录：** 要将报表作为Excel文件、文 [!DNL .png] 件或缩略图分发到共享目录，请在报表集文件的“输出根目录”参数中指定该目 [!DNL Report.cfg] 录。

* **报告门户：** 报告门户允许您通过Web浏览器查看报告。 Adobe会显示 [!DNL Report Portal] 以Excel或文件形式生成的报 [!DNL .png] 表，但不显示以缩略图形式生成的报表( [!DNL .jpg])。 要将报告分发到门户，请在报告集文件的“输出根”参数中指定用于门户的Web服务器的文档根 [!DNL Report.cfg] 目录。 有关安装和使用的详细信息， [!DNL Report Portal]请参阅 [使用报告门户](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>要读取当前支持的输出， [!DNL Report]您必须拥有一个能够以所需格式显示报表的应用程序。 例如，要查看 [!DNL .xlsx] 文件，您必须安装Microsoft Excel 2007或更高版本。

您还可以使用这些生成和分发选项的组合。 例如，如果设置参数以生成Excel和文件格式的报表集，然后设置 [!DNL Report Types][!DNL .png][!DNL Mail Report][!DNL Output Root] and参数，则该集中的所有报表将分发到指定的输出目录（可能在门户中查看），并通过电子邮件发送给收件人。

有关配置报表集的步骤，请参阅 [使用报表集](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)。 有关特定参数的更 [!DNL Report.cfg] 多信息，请参 [阅Report.cfg参数](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
