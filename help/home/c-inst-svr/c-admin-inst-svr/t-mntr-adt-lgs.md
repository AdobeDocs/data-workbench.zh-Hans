---
description: 审核日志文件跟踪与Insight Server的所有尝试连接和从Insight Server断开连接，每个连接都记录在<YYYYMMDD>-access.txt文件中，默认位于Insight Server安装目录的“审核”文件夹中。
title: 监控审计日志
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 监控审计日志{#monitoring-audit-logs}

审核日志文件跟踪与Insight Server的所有尝试连接和从Insight Server断开连接，每个连接都记录在`<YYYYMMDD>-access.txt`文件中，默认位于Insight Server安装目录的“审核”文件夹中。

**推荐频度：** 每天或根据需要进行故障排除

当对连接到[!DNL Insight Server]的问题进行故障诊断时，审核日志会非常有用。 您可以使用自动管理工具或直接查看[!DNL access.txt]文件来监控这些日志。

**要通过[!DNL Server Files Manager]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击活动[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Audit]**&#x200B;以查看其内容。
1. 右键单击所需文件旁边&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中的文件名旁边会显示一个复选标记。
1. 右键单击[!DNL Temp]列中的新复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 审核日志显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/cfg_accesscontrol_accessFile.png)
