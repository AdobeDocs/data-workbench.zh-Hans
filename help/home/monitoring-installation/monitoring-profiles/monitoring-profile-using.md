---
description: “Data Workbench用户档案状态”用户档案根据用户档案（而非服务器量度或历史数据）提供有关Data Workbench服务器运行状况的最新信息。
title: Data Workbench 配置文件状态工作区
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench 配置文件状态工作区{#data-workbench-profile-status-workspace}

“Data Workbench用户档案状态”用户档案根据用户档案（而非服务器量度或历史数据）提供有关Data Workbench服务器运行状况的最新信息。

## Data Workbench用户档案状态{#section-65d1fa393cfd450cbacef3cba823fcc1}

此状态用户档案提供Data Workbench Server最新但不是很实时的信息，因为代理每10分钟轮询一次，报告始终包含此10分钟的延迟。 更准确地说，此用户档案生成的数据集提供了代理对服务器的最新观察，代理的默认轮询周期通常为10分钟。

有关在Data Workbench用户档案状态用户档案中使用的维的其他参考信息，请参阅[分析用户档案状态用户档案](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)。

![](assets/Status_General_Status.png)

此报告更多用于监控操作，而非组件或特定流量波动。

![](assets/Status_General_page.png)

这让我们了解谁处于何种模式：如果某个用户档案的“快速输入”速率较高，则该用户档案处于“快速输入”模式。

如果“停止”量度为1，则服务器将停止。 如果值为0，则服务器不会停止。

**大批量加载的日志读取**

![](assets/Status_General_stalled_log.png)
