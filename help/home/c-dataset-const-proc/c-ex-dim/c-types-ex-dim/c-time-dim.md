---
description: 时间维度允许您基于为 Input Time (1970 epoch)（输入时间（1970 纪元））参数指定的任何时间戳字段，创建一组定期或绝对本地时间维度（例如“日”、“周日期”、“每天时间”、“预订时间”等）。
title: 时间维度
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
exl-id: f9534b24-3a16-4220-bac2-bc541e121005
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 100%

---

# 时间维度{#time-dimensions}

时间维度允许您基于为 Input Time (1970 epoch)（输入时间（1970 纪元））参数指定的任何时间戳字段，创建一组定期或绝对本地时间维度（例如“日”、“周日期”、“每天时间”、“预订时间”等）。

在定义时间维度时，您还可以指定 Week Start Day（每周开始日期）参数，选择星期一以外的日期来用作为一星期的开始日期。只要维度具有不同的名称，您就可以在数据集中定义多个时间维度集。

时间维度由以下参数定义：

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
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
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关扩展维度的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维度 </td> 
   <td colname="col2"> <p>可以将维度名称指定为以下任何周期： </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> 日 </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> 每周时间 </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> 小时 </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> 小时 </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> 月 </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> 周 </li> 
     </ul> </p> <p> 您在此处输入的名称是显示在 Data Workbench 的维度菜单和可视化中的名称。如果您将时间维度的名称保留为空，则数据集中将不会创建该维度。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden（隐藏） </td> 
   <td colname="col2"> 确定维度是否显示在 Data Workbench 界面中。默认情况下，此参数设为 false。例如，如果维度仅用作量度的基础，则可以将此参数设为 true，以在 Data Workbench 显示中隐藏维度。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Time (1970 epoch)（输入时间（1970 纪元）） </td> 
   <td colname="col2"> <p>用作输入的时间戳字段的名称。 </p> <p> <p>注意：字段的值必须代表自 1970 年 1 月 1 日 00:00:01 之后的秒数。如果输入时间不是有效的时间（1970 年到 2037 年），转换过程将失败，并且 Data Workbench Server 将生成错误。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> 父维度的名称。任何可计数维度都可以是父维度。对于 Web 数据，父项是“会话”。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Week Start Day（每周开始日期） </td> 
   <td colname="col2"> <p>用作每周第一天的日期。 </p> <p> 此参数会影响“星期”维度、“周日期”维度以及按周定义的任何报告时间维度。 </p> </td> 
   <td colname="col3"> Mon </td> 
  </tr> 
 </tbody> 
</table>

此示例基于用户定义的输入字段 x-time-1970 创建了一组时间维度。这一组时间维度名为“会话时间”。由于每个维度的父项都是“会话”维度，因此时间维度的每个元素都与某个会话开始的时间相对应。Week Start Day（每周开始日期）参数指定了“周”维度的每一周都从星期一开始。

![](assets/cfg_Transformation_Dim_TimeDim.png)
