---
description: Data Workbench监视用户档案的安装说明。
title: 安装监控配置文件
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# 安装监控配置文件{#installing-the-monitoring-profile}

Data Workbench监视用户档案的安装说明。

## 安装步骤{#section-d4355dbea8a447f48ab168db6ccff612}

1. 配置新的传感器实例，就像它将用于标记的网页数据收集一样。 确保zig.gif文件位于传感器Web服务器文档根目录中。 传感器可以与监视器用户档案在同一主机上运行。 （如果为此使用文本文件，则不会出现此问题。）

   >[!NOTE]
   >
   >此传感器实例必须专用于仅接收来自监视代理的通信。 此外，如果您为此集合重新设定Web服务器的用途，传感器可配置为在其他端口上运行。

1. 在[!DNL txlogd.conf]文件中，有默认行：

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   对于Data Workbench监视用户档案应用程序（或任何“已标记”页面实施），必须删除图像类型才能通过GIF文件收集。 更新后的行是：

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. 将[!DNL insight_monitor.zip/insight_monitor_agent]复制到临时位置。
1. 为您的环境更新[!DNL insight_monitor_agent.cfg]文件。 请按照配置文件中的注释操作：

   **监视配置文件：**

   ![](assets/monitor_agent_cfg_sensor.png)

   定义收集所有信息的位置并提供URL地址。 此传感器必须是专用传感器，除此应用程序外，不会收到任何通信。

   ![](assets/monitor_agent_cfg_dump.png)

   存在路径(假定存在e:磁盘。 您可能希望为您的环境更改此路径。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   运行“转换”用户档案时，Data Workbench可能没有响应。 如果进程连续三次无响应，则通过此值可以发送警报。 这是减少虚假阳性警报的方法。

   ![](assets/monitor_agent_cfg_groups.png)

   这是您设置环境和组维度的位置。 这可能与主机不同。

   这是![](assets/monitor_agent_cfg_debug.png)此处，您可以通过查看此路径中的错误日志来准确了解监视器代理正在执行的操作。

   ![](assets/monitor_agent_cfg_tempdb.png)

   这是在内部使用temp db。 当达到容量时，它可能会收到警报。 这与物理磁盘的使用情况不同。

1. 将&#x200B;*insight_monitor_agent*&#x200B;文件夹复制到运行Data Workbench Server的每个DPU和FSU主机。 配置文件中指示的默认位置为[!DNL e:\insight_monitor_agent]，但您可以更改此位置。

1. 添加Windows计划任务，每10分钟调用一次代理（在处理速率计算中假定此时间段）。 项目为[!DNL e:insight_monitor/insight_monitor_agent.exe]。 参数为config-file e:\insight_monitor\insight_monitor.cfg。 开始位于e:\insight_monitor。 运行执行任务的用户必须具有读/写[!DNL e:\insight_monitor]和读取Win32 OLE对象[!DNL root\CIMV2]的权限(需要确定Data Workbench Server服务开始模式并检查本地磁盘上的空间百分比)

1. 确认VSL文件正随着监视记录的累积而开始增长。 这将需要一段时间，因为在小型安装中，流量将非常低(每10分钟，代理就只发送一次针对特定主机的数据的点击，以及每个处理用户档案一次点击)。
1. 解压缩insight_monitor.zip\profiles\Insight Historic to a temporary location。
1. 更新[!DNL profile.cfg]、[!DNL dataset\cluster.cfg]和[!DNL dataset\segment export.cfg]中的主机名。

1. 将文件更新到Data Workbench用户档案目录。
1. 将[!DNL dataset\log processing.cfg]中的日志服务器和路径更新到传感器VSL的累积位置。
1. [可] 选，对用户档案和执行 [!DNL Insight Profile Status] 相同 [!DNL Insight Server Status]。此外，状态用户档案应在夜间重新处理，并设置一个拖尾的两天窗口。 添加Windows计划任务:项目为[!DNL e:\insight_monitor\insight_reprocess.exe]。 参数为[!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 将[!DNL start in]留空。 为&#x200B;*&quot;insight server status&quot;*&#x200B;添加另一个计划任务。 *insight_reprocess.exe需要* 对日志处理.cfgto的读 */写访问* 权限来更新开始时间。

1. 此外，状态用户档案应在夜间重新处理，并设置一个拖尾的两天窗口。 添加Windows计划任务:项目为&#x200B;*e:\insight_monitor\insight_reprocess.exe*。 参数为 — [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 将&#x200B;*开始留空。*&#x200B;为[!DNL "insight server status"]添加另一个计划任务。 [!DNL insight_reprocess.exe] 需要读/写访问权 [!DNL log processing.cfg] 限才能更新开始时间。确认每个用户档案在累积时都在读取VSL。 同样，由于音量极低，这将需要一些时间 — 可能需要几个小时。

## 安装说明{#section-17722441ab0046fcbcb46b957d56230a}

* **在授权测试环境中配置监视用户档案**。测试环境包随Data Workbench的实施提供，允许您安装和配置应用程序。 如果在生产FSU或DPU服务器上安装，则需要将服务器配置为在单独的端口上运行。
* **专门为监视用户档案部署新传感器**。您需要向运行监视用户档案的服务器安装新的传感器实例。 这是除传感器生产实例之外的。 (在生产或非生产服务器上安装传感器不收取额外费用，专门用于监控用户档案。)
* **在Data Workbench维护期间禁用监视器代理**。为避免污染正常运行时间和性能指标，您可以将服务开始模式设置为手动InsightServer(Omniture Insight Server)服务。 方便的PowerShell命令是&#x200B;*set-service -name insightserver -startuptype manual*。 在维护后将其重新设置为自动：*set-service -name insightserver -startuptype automatic*。 另一个选项是临时禁用监视器代理计划的任务。
* **“状态”用户档案需要一个** 尾部窗口来丢弃旧主机和用户档案以及旧主机 — 用户档案映射。但是，如果事件数据量如此小，以至于Data Workbench不会将其缓冲到其中，则可能需要将窗口的大小扩展相当大，才能使其处理。
* **代理从Data Workbench详细状态中收集整体和最早的截至时间**，该状态以本地主机时间报告，假设事件数据日志时间戳为UTC(与VSL文件一样)。如果事件用户档案时间戳位于非UTC时区中，则在生成的“分析数据状态”用户档案中，截止时间将被偏移。 如果您的事件用户档案时间戳的&#x200B;**所有**&#x200B;都位于同一时区中，则可以将该偏移添加到&#x200B;*Insight  Status\metrics\as of delay minutes.metric*。

* **引入了两个新维度，以帮助客户对处于不同状态的服务器进行分组**，如生产、升级、测试服务器和处于其他状态的服务器。例如，如果您希望获得“正常运行时间”，则只在生产模式下查看服务器。 因此，组维度只是根据您的需要任意分组服务器的另一种方式。 例如，在“监视配置”文件中，您可以设置由您的部门提供服务的主机，如运营、开发或营销。
