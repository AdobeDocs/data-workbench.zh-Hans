---
description: Data Workbench配置文件状态配置文件根据配置文件提供有关Data Workbench Server运行状况的当前信息，而不是根据服务器指标或历史数据提供。
solution: Analytics
title: 数据工作台配置文件状态工作区
topic: Data workbench
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据工作台配置文件状态工作区{#data-workbench-profile-status-workspace}

Data Workbench配置文件状态配置文件根据配置文件提供有关Data Workbench Server运行状况的当前信息，而不是根据服务器指标或历史数据提供。

## 数据工作台配置文件状态 {#section-65d1fa393cfd450cbacef3cba823fcc1}

此状态配置文件提供了Data Workbench Server的最新信息，但并非相当实时，因为代理每10分钟轮询一次，并且报告始终包含这10分钟的延迟。 更准确地说，此配置文件生成的数据集提供了代理对服务器的最新观察，代理的默认轮询时间通常为10分钟。

有关在Data Workbench配置文件状态配置文件中使用的维的其他参考信息，请参阅 [Insight配置文件状态配置文件](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)。

![](assets/Status_General_Status.png)

此报告更多用于监控操作，而非组件或特定流量波动。

![](assets/Status_General_page.png)

这让我们了解谁处于什么模式：如果我们看到某个配置文件的“快速输入”速率较高，则该配置文件处于“快速输入”模式。

如果“停止”量度为1，则服务器将停止。 如果值为0，则服务器不会停止。

**大批量加载的日志读取**

![](assets/Status_General_stalled_log.png)

