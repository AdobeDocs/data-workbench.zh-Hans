---
description: 若要创建区段维度，需要先在工作区中进行选择，然后向可视化中添加该区段。
title: 创建区段维度
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 64%

---

# 创建区段维度{#create-a-segment-dimensions}

若要创建区段维度，需要先在工作区中进行选择，然后向可视化中添加该区段。

**创建区段维度**

1. 向工作区中添加区段可视化。例如：

   ![](assets/vis_Segment.png)

1. 向工作区中添加要用于定义区段的可视化，然后进行所需的选择以定义区段。
1. 在区段可视化中，右键单击要在其后添加新区段的区段标签，然后单击&#x200B;**[!UICONTROL Add Segment]**。

   >[!NOTE]
   >
   >要创建新的第一个区段，请右键单击&#x200B;**[!UICONTROL Segments]**&#x200B;标签，然后单击&#x200B;**[!UICONTROL Add Segment]**。

   ![](assets/vis_SegmentNew.png)

   新的区段（名为“新区段”）会出现在该可视化中。“其他”区段表示您定义的区段中未包含的所有数据：通过此区段可以有效地了解数据集数据和区段数据之间的差异。

1. 右键单击新创建的区段，然后单击&#x200B;**[!UICONTROL Rename Segment]**。
1. 在名称字段中为您的新区段键入描述性名称。

   >[!NOTE]
   >
   >如果某个量度值（如[!DNL Site]中的特定访客）符合多个区段的条件，则该量度值将仅包含在其匹配的第一个列出的区段中。

**保存区段维度**

1. 右键单击区段标签，然后单击&#x200B;**[!UICONTROL Save Dimension]**。 出现[!DNL Save Dimension As]窗口。 默认的保存位置是User\*配置文件名称*\Dimension文件夹。
1. 在[!DNL File name]字段中，为要另存为维度的区段键入一个描述性名称，然后单击&#x200B;**[!UICONTROL Save]**。

只要使用可视化，就可以访问区段维度。也可以使用区段导出功能导出与您保存的维度中的元素关联的数据。

有关区段导出功能的详细信息以及要针对您的需求对其进行配置的说明，请参阅 [配置导出区段](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
