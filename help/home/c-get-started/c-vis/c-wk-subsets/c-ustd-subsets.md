---
description: 有关子集的概念性信息。
title: 了解子集
uuid: ed185b63-dbb3-4ed4-9403-cf4dc8be2ff1
exl-id: a75b36f9-d34d-4a4a-8a2c-15ae5461823c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 67%

---

# 了解子集{#understanding-subsets}

有关子集的概念性信息。

使用子集时，请记住以下事项：

* 现在，所有您的基准都与子集有关，而不是与整个数据集有关，当分析具体的子集时该项更有用。请参阅 [了解基准](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).
* 使用子集会影响所有工作区，因为该子集会全局应用于Data Workbench。
* 子集仅影响量度和非正规维度，对正规纬度不具影响。
* 使用[!DNL Report]时，子集不会影响已发布以供他人查看的报表中的数据。
* 应用后，子集对配置文件中的所有后续工作都有效，包括下次打开此Data Workbench实例时，直到将其删除为止。
* 指示已应用子集的唯一位置就是通过右键单击工作区访问的上下文菜单。

   ![](assets/mnu_Subset.png)

* 必须联机工作才能更改或删除子集。如果脱机工作且应用了子集，则无法查看整个数据集的结果。请参阅[脱机工作和联机工作](../../../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54)。

   >[!NOTE]
   >
   >子集的大小受位于单个Data Workbench服务器上的过滤器中的数据量的限制。 因此，如果Data Workbench集跨一个Data Workbench服务器群集，则子集的数据仅来自群集中的一个数据集服务器。

大型零售商用户想创建一个特定工作周数据的子集（本地缓存），然后仅对该周的数据运行查询。为此，该用户针对感兴趣的日期创建一个子集。

以下示例显示一个“访客数”随时间变化的条形图和一个“流量”量度图例。第一个图不包含任何选择：显示了数据集中的所有数据。第二个图显示 Days = {...} by Visitors 子集的数据，其中 Days 基于“日”维度中 4 月 1 日到 4 月 5 日的元素选择。

![](assets/client-sub1.png)
