---
description: 有关监视事件数据空间和更改传感器数据日志目录的信息。
solution: Analytics
title: 监控事件数据空间
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---


# 监控事件数据空间{#monitoring-event-data-space}

有关监视事件数据空间和更改传感器数据日志目录的信息。

**推荐频率：** 每5-10分钟

[!DNL Insight Server] 根据配置，每 [!DNL Sensor] 天在数据处理单元或文件服务器单元上存储一个日志文件。 日志文件的大小和它们所需的数据存储空间量取决于许多变量，例如，记录的网站数和Web服务器每秒接收的请求数。

典型安装 [!DNL Insight Server] (或群 [!DNL Insight Server] 集)能够存储多TB的数据，假设实现使用Adobe建议的机器 [!DNL Insight Server] 硬件。

通常，所有日志数据都保留在计算 [!DNL Insight Server] 机上。 如果需要在计算机上提供更多存储空间，您可以将除当前最新日志文件之外的所有数据存储介质（zip驱动器、磁带等）移动到另一台计算机或数据介质。 移动数据不需要您停止， [!DNL Insight Server]而且它不会影响任何可能连接到并使用连续 [!DNL Insights] 数据的数据中 [!DNL Insight Server] 可用的功能。 如果您不处理或重新处理分析数据集，则保留对所有以前数据的访问权，并且新数据仍在中可用 [!DNL Insight]。 如果您处理或重新处理分析数据集，则直到处理完成后才能访问数据。

默认情况下，由生成并传 [!DNL Sensor] 输到的事件数 [!DNL Insight Server] 据存储在安 [!DNL Logs] 装目录的文 [!DNL Insight Server] 件夹中。 “通信”配置文 [!DNL Communications.cfg]件指定读取的事件数据日志文件的位置 [!DNL Insight Server]。

**更改数据的日志目[!DNL Sensor]录**

1. 在> [!DNL Insight]选项卡上 [!DNL Admin] ，单 [!DNL Dataset and Profile] 击缩略图以打 **[!UICONTROL Servers Manager]** 开“服务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击 **[!UICONTROL Components]** 以视图其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. 右键单击列中新创建的复选标 [!DNL Temp] 记，然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗口 [!DNL Communications.cfg] 中，单击 **[!UICONTROL component]** 以视图其内容。
1. 在窗口 [!DNL Communications.cfg] 中，单击 **[!UICONTROL Servers]** 以视图其内容。 可能会出现几种类型的服务器：文件服务器、日志服务器、初始化服务器、状态服务器、发送服务器或复制服务器。
1. 查找LoggingServer(即写入其要 [!DNL Sensor] 处理的日志文件的位置), [!DNL Insight Server]然后单击其编号以视图菜单。

   ![步骤信息](assets/cfg_communications_examplevalues_logging.png)

   The default log directory is the [!DNL Logs] folder within the [!DNL Insight Server] installation directory.

1. 编辑 Log Directory（日志目录）参数以反映日志文件的所需位置。

   >[!NOTE]
   >
   >请勿修改 LoggingServer 的其他任何参数。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   “服务器”节点下可能会列出多个文件服务器，因此您可能需要视图其中许多文件服务器的内容(通过在列表中单击其编号)，以找到具有要修改的本地日志路径的服务器。 [!DNL Servers]

1. 编辑本地路径以反映文件的所需 [!DNL .vsl] 位置。

   >[!NOTE]
   >
   >请勿修改FileServer的任何其他参数。

   尽管日志文件的位置在文件中已经更 [!DNL Communications.cfg] 改，但可以通过指定/Logs/作为FileServer的URI，将这些文 [!DNL Server Files Manager] 件映射到文件的“日志”目录。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记， [!DNL Temp] 然后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

