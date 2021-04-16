---
description: 数值维度包含有序的数值元素，并且与其父可计数维度有一对多的关系。
title: 数值维度
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 97%

---

# 数值维度{#numeric-dimensions}

数值维度包含有序的数值元素，并且与其父可计数维度有一对多的关系。

您可以将数值维度视为父维度元素数值属性的表示形式。例如，如果您在处理 Web 数据，则可以定义数值维度“会话收入”，该维度为“会话”维度中的每个会话定义收入额（以美元为单位）。每个会话都有单个关联的收入额，但多个会话可以有相同的关联收入额。因此，“会话收入”维度与“会话”维度有一对多的关系。

数值维度通常用于定义对值求和、统计条件出现次数或者查找最小值或最大值的量度。例如，可使用以下“会话收入”维度来定义名为“收入”的量度：sum(Session_Revenue, Session)。如果以这种方式进行定义，则“收入”量度将提供选定会话的收入总额。

数值维度不能作为其他维度的父项。

数值维度由以下参数定义：

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 在 Data Workbench 中显示的描述性维度名称。维度名称不能包含连字符 (-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clip Values（剪辑值） </td> 
   <td colname="col2"> true 或 false。指定是否要对输入值（在 Operation（运算）之后）进行剪辑，使其介于最小值和最大值之间。如果 Clip Values（剪辑值）为 true，则会对值进行剪辑，使其介于该范围之内。如果 Clip Values（剪辑值）为 false，则不会为父维度元素返回任何值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关扩展维度的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 输入字段可用于创建数值维度的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fixed Size（固定大小） </td> 
   <td colname="col2"> true 或 false。控制维度中的元素数量（基数）。如果为 true，则从最小到最大的所有元素都会包含在维度中。如果为 false，则在添加值时，维度大小也会随之增大。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden（隐藏） </td> 
   <td colname="col2"> 确定维度是否显示在 Data Workbench 界面中。默认情况下，此参数设为 false。例如，如果维度仅用作量度的基础，则可以将此参数设为 true，以在 Data Workbench 显示中隐藏维度。 </td> 
   <td colname="col3"> 假 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> <p>与指定运算一起使用的值或您想要统计出现次数的输入值。 </p> <p> 如果此字段是字符串矢量，则该矢量中的每个元素都会进行计算。例如，长度为 3 且运算为 COUNT 的矢量会将 3 添加到计数中。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min（最小） </td> 
   <td colname="col2"> 最终维度结果的下限。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max（最大） </td> 
   <td colname="col2"> 最终维度结果的上限。 </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Offset（偏移） </td> 
   <td colname="col2"> 请参阅此表中的 Scale（缩放）。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operation（运算） </td> 
   <td colname="col2"> <p>可用的运算如下所示： </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> COUNT：将使用符合维度条件的所有日志条目之间 <span class="wintitle">Input</span>（输入）字段中非空值的总数。如果 <span class="wintitle">Input</span>（输入）字段是矢量字段，则会统计每个日志条目中非空值的总数。 </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> FIRST NONBLANK：使用第一个非空输入值，无论其是否来自第一个日志条目。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果该值不是数字，则不会使用任何值。 </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> FIRST ROW：使用与父维度元素相关的第一个日志条目的值，即使输入为空也是如此。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> LAST NONBLANK：使用最后一个非空输入值，无论其是否来自最后一个日志条目。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果该值不是数字，则不会使用任何值。 </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> LAST ROW：使用与父维度元素相关的最后一个日志条目的值，即使输入为空也是如此。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SUM：将使用符合维度条件的所有日志条目之间 <span class="wintitle">Input</span>（输入）字段中所有数值的总和。如果没有这样的日志条目或找不到任何数值，则使用数值 0。 </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN 或 MAX：将使用在符合维度条件的所有日志条目之间 <span class="wintitle">Input</span>（输入）字段中找到的最小或最大数值。如果没有这样的日志条目或数值，则不会使用任何值。 </li> 
     </ul> </p> <p> <p>注意：您应该指定一个运算以确保维度按照预期进行定义。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> 父维度的名称。任何可计数维度都可以是父维度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale（缩放） </td> 
   <td colname="col2"> <p>为了生成维度的序数值，运算结果会按如下方式进行转换： </p> <p> (scale * input) + offset </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如果[!DNL Operation]没有产生任何值，或[!DNL Clip Values]为false且该值不在[!DNL Min]和[!DNL Max]之间，则数值维度的任何元素都与父维度的元素无关。

此示例使用从网站流量收集的事件数据来说明数值维度的定义。这个名为“广告查看计数器”的数值维度会对访客在指定会话期间查看广告的次数进行统计。假定所有广告资源都通过将 ad= 作为 cs-uri-query 的一部分从 Web 服务器请求。在该示例中，主要关注访客查看广告的次数 (COUNT) 值，而不是字段中的实际值。

![](assets/cfg_Transformation_Dim_Numeric.png)
