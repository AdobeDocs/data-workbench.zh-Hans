---
description: 有关安装Data Workbench监控配置文件的说明。
title: 安装监控配置文件
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# 安装监控配置文件{#installing-the-monitoring-profile}

有关安装Data Workbench监控配置文件的说明。

## 安装步骤{#section-d4355dbea8a447f48ab168db6ccff612}

1. 配置新的传感器实例，如同它将用于标记的网页数据收集一样。 确保zig.gif文件位于传感器Web服务器文档根目录中。 传感器可以在与监视器配置文件相同的主机上运行。 （如果为此目的使用文本文件，则不会出现此问题。）

   >[!NOTE]
   >
   >此传感器实例必须专用于仅接收来自监视代理的通信。 此外，如果您为此集合重新安排Web服务器的用途，传感器可配置为在其他端口上运行。

1. 在[!DNL txlogd.conf]文件中，有默认行：

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   对于Data Workbench监控配置文件应用程序（或任何“已标记”的页面实施），必须删除图像类型才能通过GIF文件收集。 更新后的行是：

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. 将[!DNL insight_monitor.zip/insight_monitor_agent]复制到临时位置。
1. 更新环境的[!DNL insight_monitor_agent.cfg]文件。 请按照配置文件中的注释操作：

   **监控配置文件：**

   ![](assets/monitor_agent_cfg_sensor.png)

   定义您收集所有信息的位置并提供URL地址。 这需要是专用传感器，除此应用程序外，不会收到任何流量。

   ![](assets/monitor_agent_cfg_dump.png)

   有一些路径(假定存在e:磁盘。 您可能希望为环境更改此路径。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   有时，在运行转换配置文件时，Data Workbench可能无响应。 如果某个过程连续三次无响应，则通过此值可发送警报。 这是一种减少误报警报的方法。

   ![](assets/monitor_agent_cfg_groups.png)

   在这里可设置环境和组维度。 这可能与主机不同。

   这是![](assets/monitor_agent_cfg_debug.png)，通过查看此路径中的错误日志，您可以准确地查看监视器代理正在执行的操作。

   ![](assets/monitor_agent_cfg_tempdb.png)

   这是在内部使用temp数据库。 当达到容量时，可能会收到警报。 这与物理磁盘的使用情况不同。

1. 将&#x200B;*insight_monitor_agent*&#x200B;文件夹复制到运行Data Workbench Server的每个DPU和FSU主机。 配置文件中指示的默认位置为[!DNL e:\insight_monitor_agent]，但您可以更改此位置。

1. 添加Windows计划任务，每10分钟调用一次代理（在处理率计算中假定此时段）。 程序为[!DNL e:insight_monitor/insight_monitor_agent.exe]。 参数为config-file e:\insight_monitor\insight_monitor.cfg 。 从e:\insight_monitor开始。 执行任务的用户必须具有读/写[!DNL e:\insight_monitor]和读取Win32 OLE对象[!DNL root\CIMV2]的权限（确定Data Workbench Server服务启动模式并检查本地磁盘上的空间百分比所需）

1. 确认VSL文件会随着监视器记录的积累而开始增长。 这将需要一些时间，因为在小型安装中，流量将非常低（每10分钟，代理就只发送一次特定于主机的数据点击，另外每个处理配置文件点击一次）。
1. 解压缩insight_monitor.zip\profiles\Insight Historic to a temporary location 。
1. 更新[!DNL profile.cfg]、[!DNL dataset\cluster.cfg]和[!DNL dataset\segment export.cfg]中的主机名。

1. 将文件更新到Data Workbench配置文件目录。
1. 将[!DNL dataset\log processing.cfg]中的日志服务器和路径更新到传感器VSL的累积位置。
1. [] （可选）使用用户档案和执行 [!DNL Insight Profile Status] 相同 [!DNL Insight Server Status]操作。此外，应在夜间重新处理状态配置文件，并在尾随的两天窗口内进行处理。 添加Windows计划任务：程序为[!DNL e:\insight_monitor\insight_reprocess.exe]。 参数为[!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 将[!DNL start in]留空。 为&#x200B;*&quot;insight server status&quot;*&#x200B;添加另一个计划任务。 *insight_reprocess.* exe需要读/写权限才能 *进行日志处理。* cfgto更新开始时间。

1. 此外，应在夜间重新处理状态配置文件，并在尾随的两天窗口内进行处理。 添加Windows计划任务：程序为&#x200B;*e:\insight_monitor\insight_reprocess.exe*。 参数为 — [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 将&#x200B;*start in*&#x200B;留空。 为[!DNL "insight server status"]添加另一个计划任务。 [!DNL insight_reprocess.exe] 需要读/写访 [!DNL log processing.cfg] 问权限才能更新开始时间。确认每个用户档案在累计时都在读取监视器VSL。 同样，由于音量极低，这将需要一些时间 — 可能需要数小时。

## 安装说明{#section-17722441ab0046fcbcb46b957d56230a}

* **在授权测试环境中配置监控配置文件**。Data Workbench实施中包含测试环境包，允许您安装和配置应用程序。 如果在生产FSU或DPU服务器上安装，则需要将服务器配置为在单独的端口上运行。
* **专门为监视配置文件部署新传感器**。您需要将新的传感器实例安装到运行监视配置文件的服务器。 这是传感器生产实例的补充。 (在生产或非生产服务器上安装传感器（专门用于监视配置文件）无需额外付费。)
* **在Data Workbench维护期间禁用监视器代理**。为避免污染正常运行时间和性能指标，您可以将服务启动模式设置为手动为服务InsightServer(Omniture Insight Server)。 方便的PowerShell命令是&#x200B;*set-service -name insightserver -startuptype manual*。 在维护后将其重新设置为自动：*set-service -name insightserver -startuptype automatic*。 另一个选项是临时禁用监视器代理计划任务。
* **状态配置文件需要以尾随窗** 口拖放旧主机和配置文件，以及旧主机配置文件映射。但是，如果事件数据量如此小，以至于Data Workbench无法缓冲它，则您可能需要相当大地扩展窗口大小，才能对其进行处理。
* **代理从Data Workbench详细状态中收集整体和最早的截至时间状态**，该状态以本地主机时间报告(假定事件数据日志时间戳为UTC(与在VSL文件中一样))。如果事件数据时间戳位于非UTC时区，则“Insight Profile Status”（分析配置文件状态）生成配置文件的截止时间将被偏移。 如果事件数据时间戳的&#x200B;**所有**&#x200B;都位于同一时区，则可以将该偏移添加到&#x200B;*分析配置文件Status\metrics\as of delay minutes.metric*。

* **引入了两个新维度，以帮助客户在服务器处于不同状态(如生产、暂存、测试服务器和处于其他状态的服务器**)时对其服务器进行分组。例如，如果您要查找“正常运行时间”，则仅在生产模式下查看服务器。 因此，组维度只是根据您的需要任意分组服务器的另一种方式。 例如，在“监视配置”文件中，您可以设置由哪个托管您的部门正在提供服务，如“操作”、“开发”或“营销”。
