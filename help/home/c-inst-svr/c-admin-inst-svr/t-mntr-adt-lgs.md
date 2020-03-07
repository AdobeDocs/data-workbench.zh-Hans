---
description: 审核日志文件跟踪与Insight Server的所有尝试连接和断开连接，每个连接都记录在<YYYYMMDD>-access.txt文件中，默认情况下，该文件位于Insight Server安装目录的审核文件夹中。
solution: Insight
title: 监视审计日志
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 监视审计日志{#monitoring-audit-logs}

审核日志文件跟踪与Insight Server的所有尝试连接和断开连接，每个连接都记录在Insight Server安装目录的“审核”文件夹中默认位置的文件中。 `<YYYYMMDD>-access.txt`

**推荐频率：** 每天或根据需要进行疑难解答

在对连接到的问题进行疑难解答时，审核日志可能非常有用 [!DNL Insight Server]。 您可以使用自动化管理工具或直接查看文件来监视 [!DNL access.txt] 这些日志。

**通过[!DNL Server Files Manager]**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击活动图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Audit]** 查看其内容。
1. 右键单击所需文件旁边的 *服务器名称* 列中的复选标记，然后单击 **[!UICONTROL Make Local]**。 该列中的文件名旁边将显示一个复选 [!DNL Temp] 标记。
1. 右键单击列中的新复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 审核日志显示在新的Microsoft Windows“记事本”窗口中。

   ![步骤信息](assets/cfg_accesscontrol_accessFile.png)

