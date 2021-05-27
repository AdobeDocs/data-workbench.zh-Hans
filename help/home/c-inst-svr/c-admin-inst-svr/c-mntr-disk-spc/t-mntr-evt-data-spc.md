---
description: 有关监视事件数据空间和更改传感器数据日志目录的信息。
title: 监控事件数据空间
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 6%

---

# 监控事件数据空间{#monitoring-event-data-space}

有关监视事件数据空间和更改传感器数据日志目录的信息。

**推荐频率：** 每5-10分钟

[!DNL Insight Server] 根据您的配置， [!DNL Sensor] 每天在数据处理单元或文件服务器单元上存储一个日志文件。日志文件的大小和所需的数据存储空间量取决于许多变量，例如，正在记录的网站数量和您的Web服务器每秒收到的请求数。

典型的[!DNL Insight Server]（或[!DNL Insight Server]群集）安装能够存储多TB的数据，这是假设该实施使用Adobe为[!DNL Insight Server]计算机推荐的硬件。

通常，所有日志数据都会保留在[!DNL Insight Server]计算机上。 如果需要在计算机上提供更多的数据存储空间，则可以将除当前日志文件之外的所有日志文件移动到其他计算机或数据存储介质（zip驱动器、磁带等）。 移动数据不要求您停止[!DNL Insight Server]，并且不影响任何[!DNL Insights]中可能连接到[!DNL Insight Server]并使用连续数据的功能。 如果您不处理或重新处理分析数据集，则保留对所有先前数据的访问权限，并且新数据将继续在[!DNL Insight]中可用。 如果您处理或重新处理分析数据集，则在处理完成之前无法访问该数据。

默认情况下，由[!DNL Sensor]生成并传输到[!DNL Insight Server]的事件数据存储在[!DNL Insight Server]安装目录的[!DNL Logs]文件夹中。 通信配置文件[!DNL Communications.cfg]指定由[!DNL Insight Server]读取的事件数据日志文件的位置。

**更改数据的日志目 [!DNL Sensor] 录**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]选项卡上，单击&#x200B;**[!UICONTROL Servers Manager]**&#x200B;缩略图以打开“服务器管理器”工作区。
1. 右键单击要配置的[!DNL Insight Server]图标，然后单击&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，单击&#x200B;**[!UICONTROL Components]**&#x200B;以查看其内容。 [!DNL Communications.cfg] 文件位于此目录中。
1. 右键单击&#x200B;*服务器名称*&#x200B;列中[!DNL Communications.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL Temp]列中会出现[!DNL Communications.cfg]的复选标记。
1. 右键单击[!DNL Temp]列中新建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Communications.cfg]窗口中，单击&#x200B;**[!UICONTROL component]**&#x200B;以查看其内容。
1. 在[!DNL Communications.cfg]窗口中，单击&#x200B;**[!UICONTROL Servers]**&#x200B;以查看其内容。 可能会显示多种类型的服务器：文件服务器、日志记录服务器、初始化服务器、状态服务器、发送服务器或复制服务器。
1. 找到LoggingServer（[!DNL Sensor]在其中写入其日志文件以供[!DNL Insight Server]处理），然后单击其编号以查看菜单。

   ![步骤信息](assets/cfg_communications_examplevalues_logging.png)

   默认的日志目录是[!DNL Insight Server]安装目录中的[!DNL Logs]文件夹。

1. 编辑 Log Directory（日志目录）参数以反映日志文件的所需位置。

   >[!NOTE]
   >
   >请勿修改 LoggingServer 的其他任何参数。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   Servers节点下可能列出了多个FileServers，因此您可能需要查看其中许多FileServers的内容（通过单击[!DNL Servers]列表中的编号），以查找具有待修改的本地路径的服务器。

1. 编辑本地路径以反映[!DNL .vsl]文件的所需位置。

   >[!NOTE]
   >
   >请勿修改FileServer的任何其他参数。

   尽管日志文件的位置在[!DNL Communications.cfg]文件中已发生更改，但您可以通过指定/Logs/作为FileServer的URI，将这些文件映射到[!DNL Server Files Manager]的Logs目录。

1. 通过执行以下操作，将更改保存到服务器：

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，右键单击[!DNL Temp]列中文件的复选标记，然后选择&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
