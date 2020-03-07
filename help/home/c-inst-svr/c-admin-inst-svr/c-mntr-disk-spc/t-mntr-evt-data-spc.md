---
description: 有关监视事件数据空间和更改传感器数据日志目录的信息。
solution: Insight
title: 监视事件数据空间
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# 监视事件数据空间{#monitoring-event-data-space}

有关监视事件数据空间和更改传感器数据日志目录的信息。

**推荐频率：** 每5-10分钟

[!DNL Insight Server] 根据您的配置， [!DNL Sensor] 每天在数据处理单元或文件服务器单元上存储一个日志文件。 日志文件的大小和它们所需的数据存储空间量取决于许多变量，例如，记录的网站数量和Web服务器每秒收到的请求数。

典型的安装 [!DNL Insight Server] (或群集 [!DNL Insight Server] )能够存储多TB的数据，假设实施使用Adobe为计算机推荐的 [!DNL Insight Server] 硬件。

通常，所有日志数据都会保留在计算机 [!DNL Insight Server] 上。 如果需要在计算机上提供更多的数据存储空间，您可以将除当前最新日志文件以外的所有日志文件移动到另一台计算机或数据存储介质（zip驱动器、磁带等）。 移动数据不需要您停止 [!DNL Insight Server]，并且不会影响任何可能连接到并使用连续数据 [!DNL Insights] 的数据中 [!DNL Insight Server] 可用的功能。 如果您不处理或重新处理分析数据集，则保留对所有以前数据的访问权，并且新数据将继续在中可用 [!DNL Insight]。 如果您处理或重新处理分析数据集，则直到处理完成后才能访问数据。

默认情况下，由生成并传输到 [!DNL Sensor] 的事件数据 [!DNL Insight Server] 存储在安装目 [!DNL Logs] 录的文件夹 [!DNL Insight Server] 中。 “通信”配置文 [!DNL Communications.cfg]件指定由读取的事件数据日志文件的位置 [!DNL Insight Server]。

**更改数据的日志目[!DNL Sensor]录**

1. 在“ [!DNL Insight]>”选项卡 [!DNL Admin] 中， [!DNL Dataset and Profile] 单击缩略图以打开“服 **[!UICONTROL Servers Manager]** 务器管理器”工作区。
1. 右键单击要配置的 [!DNL Insight Server] 图标，然后单击 **[!UICONTROL Server Files]**。
1. 在中， [!DNL Server Files Manager]单击以 **[!UICONTROL Components]** 查看其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. Right-click the check mark in the *server name* column for [!DNL Communications.cfg] and click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Communications.cfg].
1. 右键单击列中新创建的复选标记， [!DNL Temp] 然后单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在窗 [!DNL Communications.cfg] 口中，单 **[!UICONTROL component]** 击以查看其内容。
1. 在窗 [!DNL Communications.cfg] 口中，单 **[!UICONTROL Servers]** 击以查看其内容。 可能会显示几种类型的服务器：文件服务器、日志服务器、初始化服务器、状态服务器、发送服务器或复制服务器。
1. 查找LoggingServer(在LoggingServer中写入其 [!DNL Sensor] 要由其处理的日志文件), [!DNL Insight Server]然后单击其编号以查看菜单。

   ![步骤信息](assets/cfg_communications_examplevalues_logging.png)

   The default log directory is the [!DNL Logs] folder within the [!DNL Insight Server] installation directory.

1. 编辑 Log Directory（日志目录）参数以反映日志文件的所需位置。

   >[!NOTE]
   >
   >请勿修改 LoggingServer 的其他任何参数。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   “服务器”节点下可能列出多个文件服务器，因此您可能需要查看其中许多文件服务器的内容（通过单击列表中的数字），以找到具有要修改的“本地路径”的服务器。 [!DNL Servers]

1. 编辑本地路径以反映文件的所需位 [!DNL .vsl] 置。

   >[!NOTE]
   >
   >请勿修改FileServer的任何其他参数。

   尽管日志文件的位置在文件中已更改，但您可以通过将/Logs/指定为FileServer的URI，将这些文件映射到 [!DNL Communications.cfg][!DNL Server Files Manager] Logs目录。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单 **[!UICONTROL (modified)]** 击窗口顶部，然后单击 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]右键单击列中文件的复选标记，然 [!DNL Temp] 后选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

