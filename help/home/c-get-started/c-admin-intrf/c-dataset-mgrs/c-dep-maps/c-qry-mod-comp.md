---
description: 有关查询模型组件的概念性信息。
title: 查询模型组件
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 70%

---

# 查询模型组件{#query-model-components}

{{eol}}

有关查询模型组件的概念性信息。

下图显示了一幅依赖关系图，其中的节点表示在配置文件的 Dimensions、Metrics 和 Filters 文件夹中定义的查询模型的量度、派生维度和过滤器，以及数据集中定义的与它们通过某种方式相关联的扩展维度。

![](assets/vis_DependencyMap_QueryModel.png)

* 黄绿色节点表示过滤器。
* 紫色节点表示量度。
* 蓝绿色节点表示派生维度。
* 绿色节点表示扩展维度（在数据集中定义）。
* 红色节点表示存在损坏或循环依赖关系或其他错误的量度、派生维度或过滤器。

>[!NOTE]
>
>由于依赖关系图设计为适应非循环依赖关系，因此循环依赖关系中涉及的节点可能无法在图中正确显示。 通过在 [!DNL Search] 框中。 有关 [!DNL Search] 功能，请参阅 [在地图中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).
