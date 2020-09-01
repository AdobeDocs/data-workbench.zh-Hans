---
description: 有关安装Data Workbench监视用户档案的说明。
solution: Analytics
title: 安装监控配置文件
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: 300b4fb872e9a48cb90297c29a2f93e0db60e7c2
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---


# 安装监控配置文件{#installing-the-monitoring-profile}

有关安装Data Workbench监视用户档案的说明。

## 安装步骤 {#section-d4355dbea8a447f48ab168db6ccff612}

1. 配置新的传感器实例，就像它将用于标记的网页数据收集一样。 确保zig.gif文件位于传感器Web服务器文档根中。 传感器可以与监视器用户档案在同一主机上运行。 （如果为此使用文本文件，则不会出现此问题。）

   >[!NOTE]
   >
   >此传感器实例必须专用于仅接收来自监视代理的通信。 此外，如果您重新设定此集合的Web服务器的用途，传感器可配置为在其他端口上运行。

1. 文件 [!DNL txlogd.conf] 中有默认行：

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   对于Data Workbench监视用户档案应用程序（或任何“已标记”页面实施），必须删除图像类型才能通过GIF文件进行收集。 更新后的行是：

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. 将其复 [!DNL insight_monitor.zip/insight_monitor_agent] 制到临时位置。
1. 为您 [!DNL insight_monitor_agent.cfg] 的环境更新文件。 按照配置文件中的注释操作：

   **监视配置文件：**

   ![](assets/monitor_agent_cfg_sensor.png)

   定义收集所有信息的位置并提供URL地址。 它必须是专用传感器，除此应用程序外，不会收到任何通信。

   ![](assets/monitor_agent_cfg_dump.png)

   存在路径(假定存在e:磁盘。 您可能希望为环境更改此路径。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   运行“转换”用户档案时，数据工作台可能没有响应。 如果进程连续三次无响应，则通过此值可发送警报。 这是一种减少虚假阳性警报的方法。

   ![](assets/monitor_agent_cfg_groups.png)

   这是您设置环境和组维的位置。 这可能与主机不同。

   这里您 ![](assets/monitor_agent_cfg_debug.png)可以通过查看此路径中的错误日志来准确了解监视代理正在执行的操作。

   ![](assets/monitor_agent_cfg_tempdb.png)

   这是在内部使用temp db。 当达到容量时，可能会收到警报。 这与物理磁盘的使用情况不同。

1. 将insight_ *monitor_agent文件夹复制到运行Data Workbench Server的每个DPU* 和FSU主机。 配置文件中指示的默认位置为， [!DNL e:\insight_monitor_agent] 但您可以更改此位置。

1. 添加一个Windows计划任务，每隔10分钟调用代理（在处理速率计算中假定此时间段）。 项目是 [!DNL e:insight_monitor/insight_monitor_agent.exe]。 参数为config-file e:\insight_monitor\insight_monitor.cfg。 开始位于e:\insight_monitor。 运行任务的用户必须具有读／写Win32 OLE对 [!DNL e:\insight_monitor] 象的权限( [!DNL root\CIMV2] 需要确定Data Workbench Server服务开始模式并检查本地磁盘上的空间百分比)

1. 确认VSL文件在监视器记录累积时开始增长。 这将需要一些时间，因为在小型安装中通信量将非常低(每10分钟，代理只发送一次针对主机特定数据的点击，每个处理用户档案一次点击)。
1. 解压缩insight_monitor.zip\profiles\Insight Historic to a temporary location。
1. 更新、 [!DNL profile.cfg]和 [!DNL dataset\cluster.cfg]中的主机名 [!DNL dataset\segment export.cfg]。

1. 将文件更新到Data Workbench用户档案目录。
1. 将日志服务器和路 [!DNL dataset\log processing.cfg] 径更新到传感器VSL正在累积的位置。
1. [(可选] )对用户档案和执行 [!DNL Insight Profile Status] 相同操 [!DNL Insight Server Status]作。 此外，状态用户档案应在夜间重新处理，并带有尾随的两天窗口。 添加Windows计划任务:项目是 [!DNL e:\insight_monitor\insight_reprocess.exe]。 理由是 [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 留 [!DNL start in] 空。 为“insight server status”添 *加另一个计划任务*。 *insight_reprocess.exe* 需要对log processing.cfg *进行读／写访问* ，以更新开始时间。

1. 此外，状态用户档案应在夜间重新处理，并带有尾随的两天窗口。 添加Windows计划任务:项目为 *e:\insight_monitor\insight_reprocess.exe*。 理由是— [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 将 *开始留* 空。 为添加另一个计划任务 [!DNL "insight server status"]。 [!DNL insight_reprocess.exe] 需要读／写访问 [!DNL log processing.cfg] 权限才能更新开始时间。 确认每个用户档案在累计时正在读取监视器VSL。 同样，由于音量极低，这将需要一些时间——可能需要数小时。

## 安装说明 {#section-17722441ab0046fcbcb46b957d56230a}

* **在授权测试用户档案中配置监视环境**。 测试环境包随Data Workbench的实施提供，允许您安装和配置应用程序。 如果在生产FSU或DPU服务器上安装，则需要将服务器配置为在单独的端口上运行。
* **专门为监视用户档案部署新传感器**。 您需要将新的传感器实例安装到运行监视用户档案的服务器。 这是传感器生产实例的补充。 (在生产服务器或非生产服务器上安装传感器不收取额外费用，专门用于监视用户档案。)
* **在数据工作台维护期间禁用监视器代理**。 为避免污染正常运行时间和性能指标，您可以将服务InsightServer(Omniture Insight服务器)的服务开始模式设置为手动。 方便的PowerShell命令 *是set-service -name insightserver -startuptype手册*。 在维护后将其重新设置为自动： *set-service -name insightserver -startuptype automatic*。 另一个选项是临时禁用监视器代理的计划任务。
* **状态用户档案需要一个尾部窗口** ，以删除旧主机和用户档案以及旧主机-用户档案映射。 但是，如果事件数据量如此小，以至于数据工作台不会将其缓冲，则可能需要将窗口的大小扩展相当大，才能使其处理。
* **代理从事件工作台收集整个和最早的截止时间详细状态**，该状态以本地主机时间报告，假定数据日志时间戳为UTC(如VSL文件)。 如果事件用户档案时间戳位于非UTC时区中，则在生成的“分析状态”用户档案中，截止时间将被偏移。 如 **果所有** 事件用户档案时间戳位于同一时区中，则可将该偏移量添加到Insight *Status\metrics\as of delay minutes.metric*。

* **引入了两个新维度，以帮助客户在服务器处于不同状态(如生产**、暂存、测试服务器和处于其他状态的服务器)时对其服务器进行分组。 例如，如果您希望获得“正常运行时间”，则只在生产模式下查看服务器。 因此，组维度只是根据您的需要任意分组服务器的另一种方式。 例如，在监视配置文件中，您可以设置托管您的部门的服务的设备，如运营、开发或营销。

