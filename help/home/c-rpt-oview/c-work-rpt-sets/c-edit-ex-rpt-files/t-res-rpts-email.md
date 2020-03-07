---
description: 通过电子邮件重新发送报告的步骤。
solution: Analytics
title: 按电子邮件重新发送报告
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 按电子邮件重新发送报告{#resending-reports-by-email}

通过电子邮件重新发送报告的步骤。

如果文 **[!UICONTROL Allow Report Regeneration]** 件中的参数 [!DNL Report.cfg] 被设置为 [!DNL True][!DNL Report.cfg] ，则当您对文件进行更改并将该文件保存回服务器时，Report Server会自动重新生成该集中的报告。 它不会通过电子邮件重新发送报告。

1. 在选 [!DNL Reports] 项卡上，为要重新发送的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**. 此报告集 [!DNL Report.cfg] 的参数显示。
1. 将参 **[!UICONTROL Start Date]** 数更改为要重新发送报告的将来时间。
1. Save the file by right-clicking **[!UICONTROL Report.cfg (modified)]** at the top of the parameters and clicking **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
此集中的报表会重新生成，并通过电子邮件发送给指定的收件人。
