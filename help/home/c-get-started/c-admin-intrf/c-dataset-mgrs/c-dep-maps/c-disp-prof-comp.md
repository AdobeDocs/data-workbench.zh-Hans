---
description: 您可以选择显示配置文件的数据集组件、查询模型组件或依赖关系图中的工作区、报表、菜单选项和地球层。
solution: Analytics
title: 显示配置文件组件
topic: Data workbench
uuid: c904dcb7-6bb9-445c-be55-0573f88928ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 显示配置文件组件{#display-profile-components}

您可以选择显示配置文件的数据集组件、查询模型组件或依赖关系图中的工作区、报表、菜单选项和地球层。

**选择要显示的组件**

1. Right-click within the dependency map and click **[!UICONTROL Display]**.
1. 选择以下一个或多个要在图中显示的选项。将在您启用的每一个显示选项的左侧显示一个 X。

   * **用于显示数据集组件的数据集** 。 请参阅 [数据集组件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-dataset-comp.md#concept-4afe28ad29d14eca8a5000847254c293)。 If you choose to display the dataset components, you have the option to [!DNL Include File Blocks] on the map. See [Working with File Blocks](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).

   * **查询模型** ，以显示查询模型组件。 请参阅 [查询模型组件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)。

   * **工作区和可视化** ，用于显示工作区、报表、菜单选项和地球层。 See [Workspaces and Visualizations](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wksps-vis.md#concept-abbd4fb115ff47f49f879466ce274921). This option works only if the [!DNL Query Model] display option is enabled.

>[!NOTE]
>
>如果选 [!DNL Query Model] 择显示选项时未启用显示 [!DNL Workspaces and Visualizations] 选项，则会显示错误消息。

如果您无法看到图上的所有节点，则可以移动或缩放该图以显示整张图，或重点显示图上某一特定区域。有关缩放操作的详细信息，请参阅 [缩放可视化](../../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

在单击某个节点时，会突出显示依赖于该节点的所有节点以及该节点依赖的所有节点，并且还会显示它们的名称。

![](assets/vis_DependencyMap_HighlightedPath.png)

>[!NOTE]
>
>依赖关系图中高亮显示的路径不构成选择。

右键单击某节点，可以看到有关图中显示的每个组件的标识信息，并可以选择可用来查看该组件更多详细信息或编辑该组件的菜单选项。此外，您还可以执行文本搜索和显示有关转换和扩展维度的性能信息。
