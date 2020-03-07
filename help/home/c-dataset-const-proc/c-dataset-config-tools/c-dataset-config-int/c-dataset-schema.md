---
description: 数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度）以及这些维度之间的关系。
solution: Analytics
title: 数据集架构
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 数据集架构{#dataset-schema}

数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度）以及这些维度之间的关系。

In addition, the [!DNL Dataset Schema] interface shows any derived dimensions that you have defined, as well as any extended dimensions that are configured to be hidden.

![](assets/vis_DatasetSchema_Example.png)

本节讨论以下主题：

* [使用数据集架构界面解释维类型](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [显示维度的默认可视化](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [显示维度的特定可视化](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## 使用数据集架构界面解释维度类型 {#section-16a0a12b11334c07bec558c0b7d260b1}

The following table lists the dimension types and the colors in which their names appear in the [!DNL Dataset Schema] interface. 示例维度（来自以上示例）的父项也有所提及。

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

## 显示维度的默认可视化 {#section-1bbb73a5cbb34ffb844eb1932db85318}

* In the [!DNL Dataset Schema] interface, click the desired dimension. 将显示默认的可视化。例如，如果默认的可视化是显示“会话数”和选定维度的表格，则单击 URI 维度时，Data Workbench 将显示一个表格，其中的 URI 按“会话数”进行排列。

>[!NOTE]
>
>If you want to change the default visualization that displays, see the Configuring Interface and Analysis Features chapter in the *Data Workbench User Guide*.

## 显示维度的特定可视化 {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* 在界 [!DNL Dataset Schema] 面中，右键单击所需的维度，然后单击 **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*。
