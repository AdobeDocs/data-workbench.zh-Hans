---
description: 有关查询模型组件的概念性信息。
solution: Analytics
title: 查询模型组件
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Query model components{#query-model-components}

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
>由于依赖关系图设计为适应非循环依赖关系，因此循环依赖关系中涉及的节点可能无法在映射上正确显示。 You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. 有关该功能的详细信 [!DNL Search] 息，请参阅 [在地图中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

