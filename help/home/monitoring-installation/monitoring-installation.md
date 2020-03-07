---
description: 有关安装Data Workbench监视配置文件的说明。
solution: Analytics
title: 安装监视配置文件
topic: Data workbench
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装监视配置文件{#installing-the-monitoring-profile}

有关安装Data Workbench监视配置文件的说明。

## 安装步骤 {#section-d4355dbea8a447f48ab168db6ccff612}

1. 配置新的传感器实例，就像它将用于标记的网页数据收集一样。 确保zig.gif文件位于传感器Web服务器文档根目录中。 传感器可以与显示器配置文件在同一主机上运行。 （如果为此目的使用文本文件，则不会出现此问题。）

   >[!NOTE]
   >
   >此传感器实例必须专用于仅接收来自监视代理的通信。 此外，如果您为此集合重新设定了Web服务器的用途，传感器可以配置为在其他端口上运行。

1. 在文 [!DNL txlogd.conf] 件中，有默认行：

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   对于Data Workbench监视配置文件应用程序（或任何“已标记”的页面实施），必须删除图像类型才能通过GIF文件进行收集。 更新的行是：

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. 将其复 [!DNL insight_monitor.zip/insight_monitor_agent] 制到临时位置。
1. 为您 [!DNL insight_monitor_agent.cfg] 的环境更新文件。 请按照配置文件中的注释操作：

   **监视配置文件：**

   ![](assets/monitor_agent_cfg_sensor.png)

   定义收集所有信息的位置并提供URL地址。 这需要是专用传感器，除此应用程序外，不会收到任何通信。

   ![](assets/monitor_agent_cfg_dump.png)

   存在路径(假定存在e:磁盘。 您可能希望为您的环境更改此路径。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   在运行转换配置文件时，Data Workbench可能无响应。 如果进程连续三次无响应，则此值允许您发送警报。 这是一种减少虚假阳性警报的方法。

   ![](assets/monitor_agent_cfg_groups.png)

   这是您设置环境和组维的位置。 这可能与主持人不同。

   这里，您 ![](assets/monitor_agent_cfg_debug.png)可以通过查看此路径中的错误日志准确了解监视器代理正在做什么。

   ![](assets/monitor_agent_cfg_tempdb.png)

   这是在内部使用temp db。 当达到容量时，可能会提醒它。 这与物理磁盘的使用情况不同。

1. 将 ** insight_monitor_agent文件夹复制到运行Data Workbench Server的每个DPU和FSU主机。 配置文件中指示的默认位置是，但 [!DNL e:\insight_monitor_agent] 您可以更改此位置。

1. 添加一个Windows计划任务，每隔10分钟调用一次代理（在处理速率计算中假定此时间段）。 计划是 [!DNL e:insight_monitor/insight_monitor_agent.exe]。 参数为config-file e:\insight_monitor\insight_monitor.cfg。 从e:\insight_monitor开始。 运行执行任务的用户必须具有读／写Win32 OLE对象的权限 [!DNL e:\insight_monitor][!DNL root\CIMV2] （需要该权限才能确定Data Workbench Server服务启动模式并检查本地磁盘上的空间百分比）

1. 确认VSL文件正随着监视器记录的累积而开始增长。 这将需要一些时间，因为小安装中的流量将非常低（每10分钟，代理程序就只发送一次针对特定主机数据的点击，以及每个处理配置文件的点击）。
1. 解压缩insight_monitor.zip\profiles\Insight Historic to a temporary location。
1. 更新[!DNL [!DNL profile.cfg]]和[!DNL [!DNL dataset\cluster.cfg]]中的主机名 [!DNL dataset\segment export.cfg]称。

1. 将文件更新到Data Workbench配置文件目录。
1. 将日志服务器和路 [!DNL dataset\log processing.cfg] 径更新到传感器VSL的累积位置。
1. [(可选] )也可以对配置文件和 [!DNL Insight Profile Status] 执行相 [!DNL Insight Server Status]同。 此外，状态配置文件应在夜间重新处理，并设置一个拖尾的两天窗口。 添加Windows计划任务：计划是 [!DNL e:\insight_monitor\insight_reprocess.exe]。 理由是 [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]。 留 [!DNL start in] 空。 为“分析服务器状态”添 *加另一个计划任务*。 *insight_reprocess.exe需要* log processing.cfg的读／写 ** 访问权限才能更新开始时间。

1. 此外，状态配置文件应在夜间重新处理，并设置一个拖尾的两天窗口。 添加Windows计划任务：该程序为 *e:\insight_monitor\insight_reprocess.exe*。 理由是— [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 将开 *头留空* 。 为添加另一个计划任务 [!DNL "insight server status"]。 [!DNL insight_reprocess.exe] 需要读／写访问权 [!DNL log processing.cfg] 限才能更新开始时间。 确认每个配置文件在监视器VSL累积时正在读取。 同样，由于音量极低，这将需要一些时间，可能需要几个小时。

## 安装说明 {#section-17722441ab0046fcbcb46b957d56230a}

* **在授权测试环境中配置监视配置文件**。 测试环境包随Data Workbench的实施提供，允许您安装和配置应用程序。 如果在生产FSU或DPU服务器上安装，则需要将服务器配置为在单独的端口上运行。
* **为监视配置文件专门部署新传感器**。 您需要将新的传感器实例安装到运行监视配置文件的服务器。 这是除传感器生产实例之外的。 （在生产或非生产服务器上安装传感器不收取任何额外费用，具体是为监视配置文件。）
* **在数据工作台维护期间禁用监视器代理**。 为避免污染正常运行时间和性能指标，可将服务InsightServer(Omniture Insight Server)的服务启动模式设置为手动。 方便的PowerShell命令 *是set-service -name insightserver -startuptype手册*。 在维护后将其重新设置为自动： *set-service -name insightserver -startuptype automatic*. 另一个选项是临时禁用监视代理计划的任务。
* **状态配置文件需要一个尾部窗口** ，以删除旧主机和配置文件以及旧主机配置文件映射。 但是，如果事件数据量太小，以至于Data Workbench不会将其缓冲到中，则可能需要相当大的时间扩展窗口大小，才能使其处理。
* **代理从Data Workbench详细状态中收集整个和最旧的截止时间**，该状态以本地主机时间报告，假定事件数据日志时间戳为UTC（如VSL文件中）。 如果事件数据时间戳位于非UTC时区中，则生成的Insight Profile Status配置文件中的截止时间将被偏移。 如 **果所有** event data time stamps都在同一时区中，则可将该偏移添加到 *Insight Profile Status\metrics\as of delay minutes.metric中*。

* **引入了两个新维度，以帮助客户在不同状态(如生产、升级、测试服务器和处于其他状态的服务器**)下对其服务器进行分组。 例如，如果您在寻找“正常运行时间”，那么您只在生产模式下查看服务器。 因此，“组”维度只是根据您的需要任意分组服务器的另一种方式。 例如，在监视配置文件中，您可以设置托管您的部门正在提供服务的文件，如运营、开发或营销。

