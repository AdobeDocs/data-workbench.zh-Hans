---
description: 密度图可视化在直方图内以阴影矩形的形式显示各个元素。
title: 密度图
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 84%

---

# 密度图{#density-map}

{{eol}}

密度图可视化在直方图内以阴影矩形的形式显示各个元素。

矩形大小取决于元素值，较大的值用面积较大的矩形表示。这类似于圆形分析图，此可视化让您可以快速了解哪些元素在所选维度中占最大百分比。

![](assets/density_map_day_visits.png)

要创建密度图：

1. 打开新工作区。

   打开一个新工作区以后，您需要单击&#x200B;**添加** > **临时解锁**。
1. 单击 **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. 选择 **[!UICONTROL Dimension]** 中。

   例如，选择 **[!UICONTROL Time]** > **[!UICONTROL Days]**.

   相反，选择 **[!UICONTROL Time]** > **[!UICONTROL Hours]** 会为您提供更多值较小的元素，这些元素显示为较小的矩形。

   >[!NOTE]
   >
   >您将需要根据需要选取一个包含多个元素的维度。 目前限制每个维度的元素最多为 200 个。

1. 您可以通过打开 **[!UICONTROL Visualization]** > **[!UICONTROL Table]** 和从表格中选择要在映射中显示的元素。

   ![](assets/density_map_day_selections.png)

   图会反应出表格上所做的选择。

1. 将鼠标悬停在小元素上，这会在光标附近以文本显示各自的名称和值。
1. 通过右键单击并选择来掩盖元素 **[!UICONTROL Mask]**，然后选择一个选项。

   ![](assets/density_map_day_mask.png)

   要显示所有屏蔽的节点，请选择 **[!UICONTROL Unhide All]**.

1. 右键单击并选择可聚焦元素 **[!UICONTROL Spotlight]**，然后选择一个选项。 聚焦可以在一定范围内突出显示元素，并且可以将元素以暗色显示。
1. 向工作区中添加颜色图例。您可以使用颜色图例识别图中的值。

   您可以向工作区中添加颜色图例，节点将根据数据的其他维度改变颜色。
1. 右键单击图标题并从菜单中选择，可以更改维度或量度。

   ![](assets/density_map_change_dim.png)

1. 通过右键单击单元格并选择 **[!UICONTROL Add Callout]**. 您可以从菜单中选择不同的类型或可视化。

   ![](assets/density_map_callout.png)

1. 与在所有可视化中一样，您可以在标题栏上方右键单击，以显示基本命令：关闭、保存、导出到 Microsoft Excel、排序、复制、最小化、无边框（不带边框显示可视化）。

   ![](assets/density_map_export.png)

1. 与其他可视化相似，您可以在密度图上选择和取消选择多个元素：

* 单击可选择一个元素。
* Ctrl + 单击可选择多个元素。
* Shift + 单击可取消选择一个元素。
* 在所选元素内右键单击可打开一个菜单。然后，选择 **[!UICONTROL Deselect]** 或 **[!UICONTROL Deselect All]** 以清除选定的元素。

## 其他选项 {#section-d77defb012424de4a7ced8e5c93115bc}

右键单击密度图会打开一个菜单，其中包含以下选项：

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 添加 标注 </td> 
   <td colname="col2">在可视化中添加文本或图表作为标注，以便进一步识别或描述元素。 <p>您也可以根据密度图中的所选元素，选择空白的量度图例、表格、折线图、或散点图。然后根据需要，向这些空白可视化添加量度和维度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 蒙版 </td> 
   <td colname="col2">蒙版选项让您可以隐藏所选元素。右键单击以显示“蒙版”选项。 <p><span class="uicontrol">隐藏此元素</span> - 选择此选项会掩盖您选择的单个元素。 </p> <p><span class="uicontrol">隐藏所选内容</span> - 选择此选项会掩盖您选择的多个元素。 </p> <p><span class="uicontrol">显示前</span> - 选择此选项将根据密度图中的值，仅显示前 100、50、25 或 10 个元素。 </p> <p><span class="uicontrol">显示后</span> - 选择此选项将根据密度图中的值，仅显示后 100、50、25 或 10 个元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 焦点 </td> 
   <td colname="col2"> 聚焦可以在一定范围内突出显示元素，并且可以将元素以暗色显示。右键单击以打开一个选项菜单。 <p><span class="uicontrol">显示前</span> - 选择此选项将根据密度图中的值，仅突出显示前 100、50、25 或 10 个元素。 </p> <p><span class="uicontrol">显示后</span> - 选择此选项将根据密度图中的值，仅突出显示后 100、50、25 或 10 个元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>取消选择 </p> <p>取消全选 </p> </td> 
   <td colname="col2"> <p> 选择这些命令会取消选择当前元素（如果已选），或取消选择所有已选的元素。 </p> </td> 
  </tr> 
 </tbody> 
</table>
