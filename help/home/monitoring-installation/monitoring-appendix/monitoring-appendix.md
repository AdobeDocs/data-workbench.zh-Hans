---
description: 本文档介绍了用户档案，以及Data Workbench监控用户档案采用的字段、维度和量度。
title: Data Workbench 配置文件维度和量度
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench 配置文件维度和量度{#data-workbench-profile-dimensions-and-metrics}

本文档介绍了用户档案，以及Data Workbench监控用户档案采用的字段、维度和量度。

要监视Data Workbench服务器，数据是使用一个脚本收集的，该脚本在解析详细状态的同时还捕获特定服务器信息。 然后，Data Workbench服务器信息会传递到页面标记调用，以便Data Workbench传感器收集并保存到VSL文件。

## Data Workbench监控配置文件{#section-b5b1234f55c3407dae8e68b031b7cd7f}使用的配置文件

这些配置文件提供了用于查看服务器状态和性能数据的维度和量度：

* [Dimension（位于“分析配置文件状态”配置文件中）](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension在Insight Server状态配置文件中](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension在Insight历史配置文件中](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [Insight历史监控配置文件中的量度](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

“状态”配置文件允许您从操作角度查看Data Workbench当前的执行情况。 **配置文件状态**&#x200B;配置文件和&#x200B;**服务器状态**&#x200B;配置文件从详细状态和Data Workbench Server收集数据。 收集的所有数据都放入`cs-uri-query`字段中供使用。

**历史配置文件**&#x200B;允许您使用历史数据评估配置和硬件更改的影响。 历史配置文件可能最有用，因为它允许您评估配置和硬件更改随时间的推移所产生的影响。
