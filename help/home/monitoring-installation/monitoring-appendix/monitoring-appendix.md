---
description: 本文档描述用户档案，包括其字段、维度和数据工作台监视用户档案使用的量度。
title: Data Workbench 配置文件维度和量度
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench 配置文件维度和量度{#data-workbench-profile-dimensions-and-metrics}

本文档描述用户档案，包括其字段、维度和数据工作台监视用户档案使用的量度。

要监视Data Workbench Server，数据会使用一个脚本进行收集，该脚本在分析详细状态的同时捕获特定服务器信息。 然后，Data Workbench Server信息会传递到页面标记调用，以便Data Workbench Sensor收集并保存到VSL文件。

## 用户档案由Data Workbench监控用户档案{#section-b5b1234f55c3407dae8e68b031b7cd7f}使用

这些用户档案提供维度和量度，允许您视图服务器状态和性能数据：

* [Dimension在Insight用户档案状态用户档案](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension在Insight Server状态用户档案](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension在Insight Historic用户档案](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight Historical Monitoring用户档案中的量度](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

“状态”用户档案允许您从操作角度查看Data Workbench当前的执行情况。 **用户档案状态**&#x200B;用户档案和&#x200B;**服务器状态**&#x200B;用户档案从详细状态和Data Workbench Server收集数据。 所有收集的数据都将放入`cs-uri-query`字段中以供使用。

**历史用户档案**&#x200B;允许您使用历史数据评估配置和硬件更改的影响。 历史用户档案可能最有用，因为它允许您评估配置和硬件更改随时间的变化的影响。
