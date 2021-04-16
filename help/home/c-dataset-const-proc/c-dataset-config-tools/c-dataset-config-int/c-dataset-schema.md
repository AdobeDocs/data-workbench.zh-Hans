---
description: 数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度）以及这些维度之间的关系。
title: 数据集架构
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 76%

---

# 数据集架构{#dataset-schema}

数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度）以及这些维度之间的关系。

此外，[!DNL Dataset Schema]接口显示您定义的任何派生维度以及配置为隐藏的任何扩展维度。

![](assets/vis_DatasetSchema_Example.png)

本节讨论以下主题：

* [使用数据集模式界面解释维度类型](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [显示维度的默认可视化](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [显示维度的特定可视化](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## 使用数据集架构界面解释维度类型 {#section-16a0a12b11334c07bec558c0b7d260b1}

下表列表了维类型及其名称在[!DNL Dataset Schema]接口中显示的颜色。 示例维度（来自以上示例）的父项也有所提及。

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 维度类型 </th> 
   <th colname="col2" class="entry"> 颜色 </th> 
   <th colname="col3" class="entry"> 示例维度和父项 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 可计数 </td> 
   <td colname="col2"> 粉红色 </td> 
   <td colname="col3"> <p>访客 - 在此架构中，“访客”是一个根可计数维度。 </p> <p> 会话 - 父项是“访客”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正规 </td> 
   <td colname="col2"> 黄色 </td> 
   <td colname="col3"> DenormalPage - 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 派生 </td> 
   <td colname="col2"> 蓝色 </td> 
   <td colname="col3"> 下一页 - 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多对多 </td> 
   <td colname="col2"> 粉红色和绿色（来自父项的主干是粉红色，而维度名称是绿色。） </td> 
   <td colname="col3"> 搜索词 - 父项是“会话”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 数值 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> 确切页面持续时间 - 父项是“页面查看”。在此示例中，“确切页面持续时间”是一个隐藏的数值维度。请参阅此表中的“隐藏”维度类型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 简单 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> 页面 - 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> 小时 - 父项是“会话”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐藏 </td> 
   <td colname="col2"> 隐藏维度是相应维度类型颜色的较暗版本。例如，隐藏的数值维度是较暗的、不太明亮的绿色。 </td> 
   <td colname="col3"> 确切页面持续时间 - 父项是“页面查看”。 </td> 
  </tr> 
 </tbody> 
</table>

## 显示维度的默认可视化  {#section-1bbb73a5cbb34ffb844eb1932db85318}

* 在[!DNL Dataset Schema]接口中，单击所需的维度。 将显示默认的可视化。例如，如果默认的可视化是显示“会话数”和选定维度的表格，则单击 URI 维度时，Data Workbench 将显示一个表格，其中的 URI 按“会话数”进行排列。

>[!NOTE]
>
>如果要更改显示的默认可视化，请参阅《Data Workbench用户指南》**&#x200B;中的“配置界面和分析功能”一章。

## 显示维度的特定可视化 {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* 在[!DNL Dataset Schema]接口中，右键单击所需的维度，然后单击&#x200B;**[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*。
