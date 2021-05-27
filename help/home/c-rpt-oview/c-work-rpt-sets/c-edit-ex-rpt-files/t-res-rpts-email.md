---
description: 通过电子邮件重新发送报表的步骤。
title: 通过电子邮件重新发送报表
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# 通过电子邮件重新发送报表{#resending-reports-by-email}

通过电子邮件重新发送报表的步骤。

如果[!DNL Report.cfg]文件中的&#x200B;**[!UICONTROL Allow Report Regeneration]**&#x200B;参数设置为[!DNL True]，则当您对[!DNL Report.cfg]文件进行更改并将该文件保存回服务器时，报表服务器会自动重新生成该集中的报表。 它不会通过电子邮件重新发送报表。

1. 在[!DNL Reports]选项卡上，为要重新发送的报表集选择子文件夹（选项卡或下拉子目录）。
1. 单击 **[!UICONTROL Report.cfg]**。此报表集的[!DNL Report.cfg]参数将显示。
1. 将&#x200B;**[!UICONTROL Start Date]**&#x200B;参数更改为要重新发送报告的将来时间。
1. 右键单击参数顶部的&#x200B;**[!UICONTROL Report.cfg (modified)]**&#x200B;并单击&#x200B;**[!UICONTROL Save to]***&lt;**[!UICONTROL server location]**>*保存文件。
此集中的报表将重新生成，并通过电子邮件发送给指定的收件人。
