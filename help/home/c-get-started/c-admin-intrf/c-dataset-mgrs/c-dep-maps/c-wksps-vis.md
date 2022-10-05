---
description: 有关工作区和可视化的概念性信息。
title: 工作区和可视化图表
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 47%

---

# 工作区和可视化图表{#workspaces-and-visualizations}

{{eol}}

有关工作区和可视化的概念性信息。

下图显示了一张依赖关系图，其中的节点表示在配置文件中定义的工作区、报表、菜单选项和地球层。仅当 [!DNL Query Model] 显示选项。

>[!NOTE]
>
>如果 [!DNL Query Model] 选择 [!DNL Workspaces and Visualizations] 显示选项时，会显示一条错误消息。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色节点表示工作区或报表。
* 黄绿色节点表示菜单选项。
* 红色节点表示存在损坏或循环依赖关系或其他错误的工作区、报表、菜单选项或地球层。

>[!NOTE]
>
>由于依赖关系图设计为适应非循环依赖关系，因此循环依赖关系中涉及的节点可能无法在图中正确显示。 通过在 [!DNL Search] 框中。 有关 [!DNL Search] 功能，请参阅 [在地图中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

有关地图上其他节点的描述，请参阅 [查询模型组件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
