---
description: 数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度），并提供这些维度之间的关系视图。
solution: Analytics
title: 数据集架构界面
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dataset Schema interface{#dataset-schema-interface}

数据集架构界面显示在任何转换数据集配置文件中定义的扩展维度（可计数、简单、多对多、数值、非正规和时间维度），并提供这些维度之间的关系视图。

In addition, the [!DNL Dataset Schema] interface shows any derived dimensions that you have defined, as well as any extended dimensions that are configured to be hidden.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>您可以从架构图中搜索维。 按搜索字符串找到的维度名称会突出显示，并且对于在附属子维度中找到的任何点击，父类的线条会更改颜色。当您通过滚动方式提供可查看的层次和上下文时，可计数维度将保持可见状态。

**使用界面解释维类[!DNL Dataset Schema]型**

The following table lists the dimension types and the colors in which their names appear in the [!DNL Dataset Schema] interface. 示例维度（来自以上示例）的父项也有所提及。

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
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
   <td colname="col3"> <p>“访客”- 在此架构中，“访客”是一个根可计数维度。 </p> <p>“会话”- 父项是“访客”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 非正规 </td> 
   <td colname="col2"> 黄色 </td> 
   <td colname="col3"> “非正规页面”- 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 派生 </td> 
   <td colname="col2"> 蓝色 </td> 
   <td colname="col3"> “下一页”- 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多对多 </td> 
   <td colname="col2"> 粉红色和绿色（来自父项的主干是粉红色，而维度名称是绿色。） </td> 
   <td colname="col3"> “搜索词”- 父项是“会话”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 数值 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> “确切页面持续时间”- 父项是“页面查看”。在此示例中，“确切页面持续时间”是一个隐藏的数值维度。请参阅此表中的“隐藏”维度类型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 简单 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> “页面”- 父项是“页面查看”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间 </td> 
   <td colname="col2"> 绿色 </td> 
   <td colname="col3"> “小时”- 父项是“会话”。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐藏 </td> 
   <td colname="col2"> 隐藏维度是相应维度类型颜色的较暗版本。例如，隐藏的数值维度是较暗的、不太明亮的绿色。 </td> 
   <td colname="col3"> “确切页面持续时间”- 父项是“页面查看”。 </td> 
  </tr> 
 </tbody> 
</table>

有关这些维度类型的详细信息，请参阅《数据集配置指南》**。

**显示维度的默认可视化**

* In the [!DNL Dataset Schema] interface, click the desired dimension. 将显示默认的可视化。例如，如果默认可视化是显示会话和选定维的表，并单击URI维，则Data Workbench将显示一个表，其中按会话显示URI。

   >[!NOTE]
   >
   >如果要更改显示的默认可视化，请参阅数 [据集架构界面](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)。

**显示维度的特定可视化**

* 在界 [!DNL Dataset Schema] 面中，右键单击所需的维度，然后单击 **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*。

