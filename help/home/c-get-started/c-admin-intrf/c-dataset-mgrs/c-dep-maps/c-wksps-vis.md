---
description: 有关工作区和可视化的概念性信息。
solution: Analytics
title: 工作区和可视化
topic: Data workbench
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Workspaces and visualizations{#workspaces-and-visualizations}

有关工作区和可视化的概念性信息。

下图显示了一张依赖关系图，其中的节点表示在配置文件中定义的工作区、报表、菜单选项和地球层。This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>如果选 [!DNL Query Model] 择显示选项时未启用显示 [!DNL Workspaces and Visualizations] 选项，则会显示错误消息。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色节点表示工作区或报表。
* 黄绿色节点表示菜单选项。
* 红色节点表示存在损坏或循环依赖关系或其他错误的工作区、报表、菜单选项或地球层。

>[!NOTE]
>
>由于依赖关系图设计为适应非循环依赖关系，因此循环依赖关系中涉及的节点可能无法在映射上正确显示。 You can search for circular dependencies by typing “circular dependency” in the [!DNL Search] text box. 有关该功能的详细信 [!DNL Search] 息，请参阅 [在地图中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

有关映射中其他节点的说明，请参阅查 [询模型组件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)。
