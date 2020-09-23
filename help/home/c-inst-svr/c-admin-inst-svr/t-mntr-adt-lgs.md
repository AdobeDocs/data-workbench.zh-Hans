---
description: 审核日志文件跟踪Insight Server的所有尝试连接和断开连接，每个连接都记录在<YYYYMMDD>-access.txt文件中，该文件默认位于Insight Server安装目录的审核文件夹中。
solution: Analytics
title: 监控审计日志
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# 监控审计日志{#monitoring-audit-logs}

审核日志文件跟踪所有尝试连接到Insight Server和从Insight Server断开连接的情况，每个连接都记录在默 `<YYYYMMDD>-access.txt` 认位于Insight Server安装目录的审核文件夹中的文件中。

**推荐频率：** 每天或根据需要进行故障排除

在对连接到的问题进行故障诊断时，审核日志可能非常有用 [!DNL Insight Server]。 您可以使用自动化管理工具或直接查看文件来监视 [!DNL access.txt] 这些日志。

**要视图access.txt文件，请通过[!DNL Server Files Manager]**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击活动图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Audit]** 以视图其内容。
1. 右键单击所需文件旁边 *的“服务器* 名称”列中的复选标记，然后单击 **[!UICONTROL Make Local]**。 该列中的文件名旁边将显示一个复选 [!DNL Temp] 标记。
1. 右键单击列中的新复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 审核日志显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/cfg_accesscontrol_accessFile.png)

