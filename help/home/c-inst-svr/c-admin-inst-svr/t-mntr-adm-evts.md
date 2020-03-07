---
description: 您应定期监视活动日志文件以跟踪Insight Server系统活动消息，这些消息记录到<YYYYMMDD>-event.txt文件中，默认情况下该文件位于Insight Server安装目录的“活动”文件夹中。
solution: Insight
title: 监视管理事件
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 监视管理事件{#monitoring-administrative-events}

您应定期监视活动日志文件以跟踪Insight Server系统活动消息，这些消息记录到默认位于Insight Server安装目录的“活动”文件夹中的文件中。 `<YYYYMMDD>-event.txt`

**推荐频率：** 每5-10分钟

您可以使用中、自动管 [!DNL Server Files Manager] 理工 [!DNL Insight]具、文件或Windows活动查 [!DNL *-event.txt] 看器监视这些事件。

>[!NOTE]
>
>管理事件日志与Windows事件日志完全不同，但包含一些相同的事件。 “管理事件日志”仅包含有关事件的 [!DNL Insight Server] 信息。

**通过[!DNL Server Files Manager]**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击活动图标，然 [!DNL Insight Server] 后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Events]** 查看其内容。
1. 右键单击所需文件旁边的 *服务器名称* 列中的复选标记，然后单击 **[!UICONTROL Make Local]**。 该列中的文件名旁边将显示一个复选 [!DNL Temp] 标记。
1. 右键单击列中的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 该事件文件显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/vis_FileManager_eventfile.png)

   安装 [!DNL Server.log] 目录内的文 [!DNL Trace] 件夹中的文 [!DNL Insight Server] 件包含更详细的日志记录信息。

**通过Windows活动查看器查看活动**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改“管理事件日志”目录**

“管理事件日志”配置文 [!DNL Administrative Events Log.cfg]件指定将事件记录输出到的目录。

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。

1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。

1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Administrative Event Logs.cfg] 文件位于此目录中。

1. Right-click the check mark in the *server name* column for [!DNL Administrative Event Logs.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Administrative Event Logs.cfg].

1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 在窗 [!DNL Administrative Event Logs.cfg] 口中，单 **[!UICONTROL component]** 击以查看其内容。 默认路径是安 [!DNL Events] 装目录中的 [!DNL Insight Server] 文件夹。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在“路径”参数中，键入要将事件记录数据输出到的目录的名称。
1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。
   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > **[!UICONTROL server name]**。

