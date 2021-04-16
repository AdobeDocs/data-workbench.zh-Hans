---
description: 使用Data Workbench历史用户档案，了解配置、硬件和其他更改如何随着时间的推移影响性能、稳定性和服务器容量。
title: Data Workbench 历史工作区
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Data Workbench 历史工作区{#data-workbench-historic-workspace}

使用Data Workbench历史用户档案，了解配置、硬件和其他更改如何随着时间的推移影响性能、稳定性和服务器容量。

“历史用户档案”包括基于用户档案的[用户档案性能](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d)数据集和&#x200B;**[!UICONTROL Performance]**&#x200B;选项卡下基于服务器的[服务器性能](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09)数据集。 从Data Workbench Server的过去的性能角度查看，这些是最常用的数据集。 此外，还可以通过选择&#x200B;**[!UICONTROL Up Time]**&#x200B;选项卡来视图[组件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)和[处理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)。

![](assets/Historic_Performance.png)

此外，还可以通过选择&#x200B;**[!UICONTROL Up Time]**&#x200B;选项卡来视图[组件](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)和[处理模式](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66)。

有关在Data Workbench历史用户档案中使用的维的其他参考信息，请参阅Insight历史用户档案中的[Dimension。](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## 用户档案性能工作区{#section-184a86f9de054970bf68515bb9dea85d}

此数据集包含以下有关Data Workbench监视的相关量度。

* 快速输入每分钟兆字节 — 在初始日志处理期间显示大量数据输入的量度。
* 快速合并兆字节每分钟 — 显示转换的量度。

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>要对您的用户档案进行实际性能评估，请查看速率，而不是已用的日历时间。 该速率以每10分钟轮询一次之间更改的值来衡量。

## 服务器性能工作区{#section-5dad5870384b40e094d50173fcd90a09}

此数据集监视超出包含用户档案范围的服务器量度，并包括以下用于Data Workbench监视的相关服务器量度。

* 估计扫描分钟数 — 估计查询分辨率时间。
* 轮询延迟毫秒 — 通过测量完成每个组件的整个服务周期所需的时间来指示软件有多忙。

![](assets/Historic_Server_Performance.png)

## 组件工作区{#section-5be7223abb384784bafe7b37c764ea66}

此数据集位于Up Time选项卡下。

![](assets/Up_Time.png)

组件数据集包含组件运行状况的两个方面：

* 通信量度 — Data Workbench Server进程是否响应？
* “所有组件”量度 — “详细状态”页顶部是主机在Data Workbench Server进程中提供服务的组件的列表。 如果任何组件处于错误状态，则它将列在“错误中的组件”(Components in Error)表中。

![](assets/Up_Time_components.png)

## 处理模式工作区{#section-3e1dedb9474e4b4ba513240943e76817}

此工作区位于“启动时间”选项卡下。 此工作区允许您观察快速输入、快速合并和实时模式所花费的时间。

![](assets/Up_Time_Processing_mode.png)

此数据集提供重要的服务器负载特征，如标识

* 星期（例如，星期二和星期三的快速输入率），
* 一天中的小时（在“快速输入”模式下，一天的百分比是多少？）
