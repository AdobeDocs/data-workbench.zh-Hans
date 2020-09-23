---
description: 您应定期监视事件日志文件以跟踪Insight Server系统事件消息，这些消息记录在<YYYYMMDD>-事件.txt文件中，默认位于Insight Server安装目录的事件文件夹中。
solution: Analytics
title: 监控管理事件
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 4%

---


# 监控管理事件{#monitoring-administrative-events}

您应定期监视事件日志文件以跟踪Insight Server系统事件消息，这些消息默认记录 `<YYYYMMDD>-event.txt` 到Insight Server安装目录中文件夹中的事件文件夹。

**推荐频率：** 每5-10分钟

您可以使用中、自 [!DNL Server Files Manager] 动化 [!DNL Insight]管理工具、文件或Windows [!DNL *-event.txt] 事件查看器监视这些事件。

>[!NOTE]
>
>管理事件日志与Windows事件日志完全分离，但包含一些相同事件。 管理事件日志仅包含有关事件的 [!DNL Insight Server] 信息。

**视图事件.txt文件[!DNL Server Files Manager]**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击活动图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Events]** 以视图其内容。
1. 右键单击所需文件旁边 *的“服务器* 名称”列中的复选标记，然后单击 **[!UICONTROL Make Local]**。 该列中的文件名旁边将显示一个复选 [!DNL Temp] 标记。
1. 右键单击列中的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 事件文件显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/vis_FileManager_eventfile.png)

   安装 [!DNL Server.log] 目录内的文 [!DNL Trace] 件夹中 [!DNL Insight Server] 的文件包含更详细的日志记录信息。

**通过Windows视图查看器事件**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改管理事件日志目录**

管理事件日志配置文 [!DNL Administrative Events Log.cfg]件指定事件日志输出到的目录。

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。

1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Components]** 以视图其内容。 [!DNL Administrative Event Logs.cfg] 文件位于此目录中。

1. Right-click the check mark in the *server name* column for [!DNL Administrative Event Logs.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Administrative Event Logs.cfg].

1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 在窗口 [!DNL Administrative Event Logs.cfg] 中，单击 **[!UICONTROL component]** 以视图其内容。 默认路径是安 [!DNL Events] 装目录中的 [!DNL Insight Server] 文件夹。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在路径参数中，键入要输出事件记录数据的目录的名称。
1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
   1. 在列 [!DNL Server Files Manager]中，右键单击该文件的复选标记， [!DNL Temp] 然后选择 **[!UICONTROL Save to]** > **[!UICONTROL server name]**。

