---
description: 通过电子邮件重新发送报表的步骤。
title: 通过电子邮件重新发送报表
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 通过电子邮件重新发送报表{#resending-reports-by-email}

{{eol}}

通过电子邮件重新发送报表的步骤。

如果 **[!UICONTROL Allow Report Regeneration]** 参数 [!DNL Report.cfg] 文件设置为 [!DNL True]，当您对 [!DNL Report.cfg] 文件并将该文件保存回服务器，报表服务器会自动重新生成该集中的报表。 它不会通过电子邮件重新发送报表。

1. 在 [!DNL Reports] 选项卡，为要重新发送的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**。的参数 [!DNL Report.cfg] 显示。
1. 更改 **[!UICONTROL Start Date]** 参数指定要重新发送报表的将来时间。
1. 通过右键单击保存文件 **[!UICONTROL Report.cfg (modified)]** ，然后单击 **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
此集中的报表将重新生成，并通过电子邮件发送给指定的收件人。
