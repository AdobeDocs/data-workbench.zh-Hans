---
description: 简单维度与其父可计数维度有一对多的关系。
solution: Analytics
title: 简单维度
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 简单维度{#simple-dimensions}

简单维度与其父可计数维度有一对多的关系。

简单维度始终是可计数维度的子项。您可以将简单维度视为其父维度中元素属性的表示形式。例如，如果您在处理 Web 数据，则可以定义“访客反向链接”维度，该维度是一个简单维度，其父维度为“访客”。它表示“访客”维度中每个访客的第一个 HTTP 反向链接。“访客”维度中的每个访客都只有一个访客反向链接，但多个访客可以具有相同的访客反向链接。因此，“访客反向链接”维度与“访客”维度有一对多的关系。

简单维度由以下参数定义：

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> 在 Data Workbench 中显示的描述性维度名称。维度名称不能包含连字符 (-)。 </td> 
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
   <td colname="col2"> 与父维度（父项）相关的值字段。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Load File（加载文件） </td> 
   <td colname="col2"> <p>可选。关系的可用值文件。您可以在下列任一情况下使用加载文件： </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> 值按照您想要保留在 Data Workbench 显示中的特定顺序排列。例如，您可能想要创建元素（一年中的季度）始终按年代顺序显示的“季度”维度。 </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> 您希望为数据中可能找不到但需要出现在 Data Workbench 显示中的值创建占位符。 </li> 
     </ul> </p> <p> 如果遇到文件中不存在的值，则在 Data Workbench 中查看时，该值会添加到这些值的末尾。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operation（运算） </td> 
   <td colname="col2"> <p>可用的运算如下所示： </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> FIRST NONBLANK：使用第一个非空输入值，无论其是否来自第一个日志条目。如果 Input（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。 </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> FIRST ROW：使用与父维度元素相关的第一个日志条目的值，即使输入为空也是如此。如果 Input（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> LAST NONBLANK：使用最后一个非空输入值，无论其是否来自最后一个日志条目。如果 Input（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。 </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> LAST ROW：使用与父维度元素相关的最后一个日志条目的值，即使输入为空也是如此。如果 Input（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
     </ul> </p> <p> <p>注意：如果“运算”没有生成任何值，或为特定的日志条目生成了空值，则父维度的对应元素将与简单维度的“无”元素相关联。 </p> </p> <p> 您应该指定一个运算以确保维度按照预期进行定义。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> 父维度的名称。任何可计数维度都可以是父维度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用从网站流量收集的事件数据和加载文件说明了简单维度的定义。

以调查网站访客最喜欢的 Girl Scout 饼干为例。有一个网页会捕获此投票，并将其以名称-值对 favoritecookie 的形式返回到 Web 服务器。每个访客只统计一次投票，但是访客可以根据需要改变他们的主意并重新投票。这是一对多的关系：一个访客可以拥有多次投票，但每次投票仅与一个访客相关联。因此，维度的父项是访客（每个访客只有一次投票），运算为 LAST ROW（以便他们可以改变主意并重新投票）。

所有类型的饼干都必须存在占位符，以便没有收到投票的饼干类型也会出现在 Data Workbench 显示中。因此，定义了一个加载文件，其中包含可以选择的饼干类型列表。此文件的内容（保存在名为 [!DNL cookietypes.txt] 的文件中）如下所示：

Animal Treasures

Caramel Delights

Lemon Pastry Creams

Peanut Butter Patties

Shortbreads

Thin Mints

最终维度的定义如下所示：

![](assets/cfg_Transformation_Dim_Simple.png)

