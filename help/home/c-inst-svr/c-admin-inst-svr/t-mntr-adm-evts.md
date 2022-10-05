---
description: 您应定期监控事件日志文件以跟踪记录到 <yyyymmdd>-event.txt文件，默认位于Insight Server安装目录的Events文件夹中。
title: 监控管理事件(Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# 监控管理事件{#monitoring-administrative-events}

{{eol}}

您应定期监控事件日志文件以跟踪记录到 `<YYYYMMDD>-event.txt` 文件默认位于Insight Server安装目录的Events文件夹中。

**推荐频率：** 每5-10分钟

您可以使用 [!DNL Server Files Manager] in [!DNL Insight]，您的自动管理工具 [!DNL *-event.txt] 文件或Windows事件查看器。

>[!NOTE]
>
>管理事件日志与Windows事件日志完全分开，但包含一些相同的事件。 管理事件日志仅包含有关 [!DNL Insight Server] 事件。

**要通过[!DNL Server Files Manager]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击活动的图标 [!DNL Insight Server] 单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Events]** 查看其内容。
1. 右键单击 *服务器名称* 列，然后单击 **[!UICONTROL Make Local]**. 中的文件名旁会显示一个复选标记 [!DNL Temp] 列。
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 该事件文件会显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/vis_FileManager_eventfile.png)

   的 [!DNL Server.log] 文件 [!DNL Trace] 文件夹 [!DNL Insight Server] 安装目录包含更详细的日志记录信息。

**通过Windows事件查看器查看事件**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改管理事件日志目录**

管理事件日志配置文件， [!DNL Administrative Events Log.cfg]，指定将事件日志记录输出到的目录。

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。

1. 右键单击 [!DNL Insight Server] 要配置并单击 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Administrative Event Logs.cfg] 文件位于此目录中。

1. 右键单击 *服务器名称* 列 [!DNL Administrative Event Logs.cfg] 单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Administrative Event Logs.cfg].

1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 在 [!DNL Administrative Event Logs.cfg] 窗口，单击 **[!UICONTROL component]** 查看其内容。 默认路径为 [!DNL Events] 文件夹 [!DNL Insight Server] 安装目录。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在路径参数中，键入要将事件日志记录数据输出到的目录的名称。
1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.
   1. 在 [!DNL Server Files Manager]，右键单击 [!DNL Temp] 列和选择 **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
