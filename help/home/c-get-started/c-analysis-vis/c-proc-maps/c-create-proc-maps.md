---
description: 可以通过将条形图、表格和层次视图中的元素拖放到空白流程图上来创建 2D 和 3D 流程图。
solution: Analytics
title: 创建流程图
topic: Data workbench
uuid: dbcde637-0411-4296-99ca-5510e0285e4b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Create a process map{#create-a-process-map}

可以通过将条形图、表格和层次视图中的元素拖放到空白流程图上来创建 2D 和 3D 流程图。

可以添加的元素必须是流程图基本维度的元素。也可以将节点从一个流程图拖放到另一个流程图，前提是这两个流程图使用的是相同的基本维度。此外，可以缩放或移动整个流程图，以聚焦某个特定节点，或者也可以将其更改为其他可视化类型。请参阅 [缩放可视化](../../../../home/c-get-started/c-vis/c-zoom-vis.md#concept-7e33670bb5344f78a316f1a84cc20530).

**使用表格或条形图向流程图中添加元素**

* 从基本维度与流程图相同的任何表格或条形图中，按 Ctrl+Alt 的同时单击各个元素并将其拖动到流程图。鼠标光标会显示“否”一词，直到鼠标到达流程图为止。

   >[!NOTE]
   >
   >可以添加的元素必须是流程图基本维度的元素。

   ![](assets/vis_2DProcessMap_addPages.png)

**使用层次视图向流程图中添加元素**

>[!NOTE]
>
>Adobe建议您从要分析的层次结构的最高级别添加节点。

1. From any table or bar graph with the same base dimension as the process map, right-click an element or the label of the base dimension and click **[!UICONTROL Hierarchy View]**.
1. 按 Ctrl+Alt 的同时单击元素并将其拖动到流程图。鼠标光标会显示“否”一词，直到鼠标到达流程图为止。

   >[!NOTE]
   >
   >可以添加的元素必须是流程图基本维度的元素。

   将单个元素拖动到流程图上会仅为该元素创建流程图节点，但如果您选择多个元素（一个组）或包含多个元素的文件夹，则从层次中拖动会为该组或文件夹创建单个节点。For example, if you are working with website data, dragging a folder named [!DNL site.com/cgi-bin] onto a map makes a node called [!DNL site.com/cgi-bin/*], which represents all pages and directories that are children of that folder.

有关页面层次视图的详细信息，请参阅应 [用层次视图](../../../../home/c-get-started/c-analysis-vis/c-tables/c-hier-vews.md#concept-b461183424a841eb94f8143a0eaf9bff)。

**从一个流程图向另一个流程图中添加节点**

>[!NOTE]
>
>流程图必须具有相同的基本维度。

* 使用以下方法将节点从第一个流程图复制到第二个流程图：

   * 若要复制单个节点，请单击并将每个节点拖动到第二个流程图。
   * 若要复制多个节点，请在按住 Ctrl 的同时单击并拖动，以在要复制的节点周围创建一个框，然后单击突出显示的节点并将其拖动到第二个流程图。所有突出显示的节点便会复制到第二个流程图。
