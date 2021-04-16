---
description: 您应定期监视事件日志文件以跟踪Insight Server系统事件消息，这些消息记录到<YYYYMMDD>-事件.txt文件，默认情况下该文件位于Insight Server安装目录中的事件文件夹中。
title: 监控管理事件
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 4%

---

# 监控管理事件{#monitoring-administrative-events}

您应定期监视事件日志文件以跟踪Insight Server系统事件消息，这些消息记录到`<YYYYMMDD>-event.txt`文件，默认情况下位于Insight Server安装目录的事件文件夹中。

**建议频率：** 每5-10分钟

您可以使用[!DNL Insight]中的[!DNL Server Files Manager]、自动管理工具、[!DNL *-event.txt]文件或Windows事件查看器监视这些事件。

>[!NOTE]
>
>管理事件日志与Windows事件日志完全不同，但包含一些相同事件。 管理事件日志仅包含有关[!DNL Insight Server]事件的信息。

**要视图事件.txt文件，请通过[!DNL Server Files Manager]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。
1. 右键单击活动[!DNL Insight Server]的图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Events]**&#x200B;视图其内容。
1. 右键单击所需文件旁边的&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Temp]列中，文件名旁边会显示一个复选标记。
1. 右键单击[!DNL Temp]列中的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 事件文件显示在新的Microsoft Windows记事本窗口中。

   ![步骤信息](assets/vis_FileManager_eventfile.png)

   安装目录[!DNL Insight Server]中[!DNL Trace]文件夹中的[!DNL Server.log]文件包含更详细的日志记录信息。

**要通过Windows视图查看器事件事件**

* 单击 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改管理事件日志目录**

管理事件日志配置文件[!DNL Administrative Events Log.cfg]指定将事件日志记录输出到的目录。

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开Servers Manager工作区。

1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;视图其内容。 [!DNL Administrative Event Logs.cfg] 文件位于此目录中。

1. 右键单击[!DNL Administrative Event Logs.cfg]的&#x200B;*服务器名称*&#x200B;列中的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Administrative Event Logs.cfg]的[!DNL Temp]列中显示复选标记。

1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 在[!DNL Administrative Event Logs.cfg]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;视图其内容。 默认路径是[!DNL Insight Server]安装目录中的[!DNL Events]文件夹。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在“路径”参数中，键入要输出事件日志数据的目录名。
1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]**，然后单击&#x200B;**[!UICONTROL Save]**。
   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL server name]**。
