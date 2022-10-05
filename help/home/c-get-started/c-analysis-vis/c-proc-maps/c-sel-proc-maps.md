---
description: 可以在流程图中进行选择，以创建包含或排除与某个特定节点关联的数据的过滤器。
title: 从流程图中选择
uuid: 7fd00090-c9ab-4bb6-8584-7de7b6f4b68c
exl-id: 8ede395f-906a-49e0-8ff8-b43a326275e5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 81%

---

# 从流程图中选择{#make-a-selection-from-a-process-map}

{{eol}}

可以在流程图中进行选择，以创建包含或排除与某个特定节点关联的数据的过滤器。

在流程图中进行选择涉及流程图的组维度，该维度确定基本维度的元素（即流程图中的节点）如何组合以形成节点之间的连接。

>[!NOTE]
>
>您可以更改流程图的默认组维度。 请参阅 [配置流程图](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-proc-maps.md#task-4a95730b18a14bc790a77c013832b2d6).

当您在流程图中根据节点做出选择时，即选择了包含该节点的组维度的所有元素。为了更好地了解组维度的作用，考虑以下示例：

* 可以按给其打分的观看者来组合影片。每个观看者都是“用户”维度的一个元素，因此“用户”维度将是该流程图的组维度。当您从某个特定影片的节点进行选择时，即会创建一个过滤器，该过滤器显示已给该影片打分或未给该影片打分的用户的数据。
* 可以按在其中查看页面的会话来组合网站页面。每个会话都是“会话”维度的一个元素，因此“会话”维度将是该流程图的组维度。当您从某个特定页面的节点进行选择时，即会创建一个过滤器，该过滤器显示查看或未查看该页面的会话的数据。

**进行选择**

1. 右键单击流程图中的任何节点。
1. 单击以下选项之一，以基于该节点进行选择：

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL through node name]**:过滤数据以包含通过节点的组维度的所有元素，方法是过滤掉未通过节点的所有会话。

   * **[!UICONTROL Select]*** **[!UICONTROL group dimension name +s]*** **[!UICONTROL NOT through node name]**:通过过滤掉通过节点的所有会话，过滤数据以包含未通过节点的组维度的所有元素。

![](assets/vis_2DProcessMap_Selections_Movie.png)

![](assets/vis_2DProcessMap_Selections_Page.png)

当在 3D 流程图中进行选择时，进行选择的节点将带有圆圈。每个长方块周围出现的基准帮助您比较带有选择和不带选择的量度值。请参阅 [了解基准](../../../../home/c-get-started/c-vis/c-ustd-benchmks.md#concept-c7b0f4102e92458096f8c4765cbe2914).

![](assets/vis_3DProcessMap_Selection.png)
