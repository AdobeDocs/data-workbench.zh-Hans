---
description: 审核日志文件跟踪与Insight Server的所有尝试连接和从Insight Server断开连接，每个连接都记录在 <yyyymmdd>-access.txt文件，默认位于Insight Server安装目录的“审核”文件夹中。
title: 监控审核日志
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 监控审核日志{#monitoring-audit-logs}

{{eol}}

审核日志文件跟踪与Insight Server的所有尝试连接和从Insight Server断开连接，每个连接都记录在 `<YYYYMMDD>-access.txt` 文件默认位于Insight Server安装目录的“审核”文件夹中。

**推荐频率：** 每天或根据需要进行故障排除

在对连接到的问题进行故障诊断时，审核日志可能会非常有用 [!DNL Insight Server]. 您可以使用自动管理工具或通过查看 [!DNL access.txt] 文件。

**要通过[!DNL Server Files Manager]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击活动的图标 [!DNL Insight Server] 单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Audit]** 查看其内容。
1. 右键单击 *服务器名称* 列，然后单击 **[!UICONTROL Make Local]**. 中的文件名旁会显示一个复选标记 [!DNL Temp] 列。
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 审核日志显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/cfg_accesscontrol_accessFile.png)
