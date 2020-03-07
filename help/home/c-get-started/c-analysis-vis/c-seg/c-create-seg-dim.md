---
description: 若要创建区段维度，需要先在工作区中进行选择，然后向可视化中添加该区段。
solution: Analytics
title: 创建区段维
topic: Data workbench
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建区段维{#create-a-segment-dimensions}

若要创建区段维度，需要先在工作区中进行选择，然后向可视化中添加该区段。

**创建区段维度**

1. 向工作区中添加区段可视化。例如：

   ![](assets/vis_Segment.png)

1. 向工作区中添加要用于定义区段的可视化，然后进行所需的选择以定义区段。
1. In the segment visualization, right-click the label of the segment after which you want the new segment to be added and click **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >要创建新的第一个区段，请右键单击标 **[!UICONTROL Segments]** 签并单击 **[!UICONTROL Add Segment]**。

   ![](assets/vis_SegmentNew.png)

   新的区段（名为“新区段”）会出现在该可视化中。“其他”区段表示您定义的区段中未包含的所有数据：通过此区段可以有效地了解数据集数据和区段数据之间的差异。

1. Right-click the newly created segment and click **[!UICONTROL Rename Segment]**.
1. 在名称字段中为您的新区段键入描述性名称。

   >[!NOTE]
   >
   >If a metric value, such as a particular visitor in [!DNL Site], meets the criteria of multiple segments, the metric value is included in only the first listed segment that it matches.

**保存区段维度**

1. Right-click the Segments label and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears. 默认的保存位置是User\*配置文件名称*\Dimensions文件夹。
1. In the [!DNL File name] field, type a descriptive name for the segments that you are saving as a dimension and click **[!UICONTROL Save]**.

只要使用可视化，就可以访问区段维度。也可以使用区段导出功能导出与您保存的维度中的元素关联的数据。

有关区段导出功能的详细信息以及要针对您的需求对其进行配置的说明，请参阅 [配置导出区段](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
