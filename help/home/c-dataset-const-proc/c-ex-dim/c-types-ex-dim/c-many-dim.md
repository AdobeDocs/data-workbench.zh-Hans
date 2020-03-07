---
description: 多对多维度与其父可计数维度有多对多的关系。
solution: Analytics
title: 多对多维度
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 多对多维度{#many-to-many-dimensions}

多对多维度与其父可计数维度有多对多的关系。

您可以将多对多维度视为其父维度中每个元素一组值的表示形式。例如，多对多维度“搜索短语”是“会话”级别的维度（其父项是“会话”）。它表示与“会话”维度中的每个会话相关联的搜索短语集。单个搜索短语可以用在任意数量的会话中，并且单个会话可以包含零个或以上搜索短语。因此，“搜索短语”维度与“会话”维度有多对多的关系。

多对多维度由以下参数定义：

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 向 Data Workbench 中的用户显示的描述性维度名称。维度名称不能包含连字符 (-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments（备注） </td> 
   <td colname="col2"> 可选。有关扩展维度的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition（条件） </td> 
   <td colname="col2"> 在父项与输入字段值之间建立关系应该具备的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden（隐藏） </td> 
   <td colname="col2"> 确定维度是否显示在 Data Workbench 界面中。默认情况下，此参数设为 false。例如，如果维度仅用作量度的基础，则可以将此参数设为 true，以在 Data Workbench 显示中隐藏维度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> <p>与父维度（父项）相关的值。如果此字段为字符串矢量，则该矢量的每个元素都与父项有自己的关系。 </p> <p> <p>注意：如果某个父维度元素的每个日志条目输入值为空，则多对多维度的元素都不会与该父维度元素相关联。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> 父维度的名称。任何可计数维度都可以是父维度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用从网站流量收集的事件数据说明了多对多维度的定义。此多对多维度名为“选定的产品”，它将会话与访客在该会话期间购买的产品相关联。x-products 字段包含值矢量，其中每个值都与一个页面查看相关联，而页面查看反过来又与会话相关联。

![](assets/cfg_Transformation_Dim_ManytoMany.png)

通过创建此类转换，您可以在 Data Workbench 中创建一个可视化，描述选定产品维度与涉及每种产品的会话数量之间的关系。
