---
description: 有关监视事件数据空间和更改传感器数据日志目录的信息。
title: 监控事件数据空间
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---

# 监控事件数据空间{#monitoring-event-data-space}

{{eol}}

有关监视事件数据空间和更改传感器数据日志目录的信息。

**推荐频率：** 每5-10分钟

[!DNL Insight Server] 存储每个 [!DNL Sensor] 数据处理单元或文件服务器单元的每日流量，具体取决于您的配置。 日志文件的大小和所需的数据存储空间量取决于许多变量，例如，正在记录的网站数量和您的Web服务器每秒收到的请求数。

典型的 [!DNL Insight Server] (或 [!DNL Insight Server] 群集)能够存储多TB的数据，这假定该实施使用Adobe建议的硬件 [!DNL Insight Server] 机器。

通常，所有日志数据都会保留在 [!DNL Insight Server] 机器。 如果需要在计算机上提供更多的数据存储空间，则可以将除当前日志文件之外的所有日志文件移动到其他计算机或数据存储介质（zip驱动器、磁带等）。 移动数据不需要停止 [!DNL Insight Server]，并且它不会影响任何 [!DNL Insights] 可能与 [!DNL Insight Server] 和处理连续数据。 如果您不处理或重新处理分析数据集，则保留对所有先前数据的访问权限，并且新数据将继续在 [!DNL Insight]. 如果您处理或重新处理分析数据集，则在处理完成之前无法访问该数据。

默认情况下，由 [!DNL Sensor] 并发送至 [!DNL Insight Server] 存储在 [!DNL Logs] 文件夹 [!DNL Insight Server] 安装目录。 通信配置文件， [!DNL Communications.cfg]，指定读取的事件数据日志文件的位置 [!DNL Insight Server].

**更改的日志目录 [!DNL Sensor] 数据**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，单击 **[!UICONTROL Servers Manager]** 缩略图以打开“服务器管理器”工作区。
1. 右键单击 [!DNL Insight Server] 要配置并单击 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，单击 **[!UICONTROL Components]** 查看其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. 右键单击 *服务器名称* 列 [!DNL Communications.cfg] 单击 **[!UICONTROL Make Local]**. 在 [!DNL Temp] 列 [!DNL Communications.cfg].
1. 右键单击 [!DNL Temp] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Communications.cfg] 窗口，单击 **[!UICONTROL component]** 查看其内容。
1. 在 [!DNL Communications.cfg] 窗口，单击 **[!UICONTROL Servers]** 查看其内容。 可能会显示多种类型的服务器：文件服务器、日志记录服务器、初始化服务器、状态服务器、发送服务器或复制服务器。
1. 查找LoggingServer，其中 [!DNL Sensor] 写入其要由处理的日志文件 [!DNL Insight Server]，然后单击其编号以查看菜单。

   ![步骤信息](assets/cfg_communications_examplevalues_logging.png)

   默认的日志目录为 [!DNL Logs] 文件夹 [!DNL Insight Server] 安装目录。

1. 编辑 Log Directory（日志目录）参数以反映日志文件的所需位置。

   >[!NOTE]
   >
   >请勿修改 LoggingServer 的其他任何参数。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   多个文件服务器可能列在“服务器”节点下，因此您可能需要查看其中许多服务器的内容(通过单击 [!DNL Servers] 列表)以查找具有待修改的本地路径的服务器。

1. 编辑本地路径以反映 [!DNL .vsl] 文件。

   >[!NOTE]
   >
   >请勿修改FileServer的任何其他参数。

   尽管日志文件的位置已在 [!DNL Communications.cfg] 文件中，您可以将这些文件映射到 [!DNL Server Files Manager] 指定/Logs/作为FileServer的URI。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击 **[!UICONTROL (modified)]** ，然后单击 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，右键单击 [!DNL Temp] 列和选择 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
