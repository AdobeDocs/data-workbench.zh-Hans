---
description: Merge 转换从输入字段（通常是字符串矢量）获取值，将它们组合为由给定分隔符分隔的单一字符串，并将结果字符串放在给定输出字段中。
title: 合并
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 90%

---

# 合并{#merge}

{{eol}}

Merge 转换从输入字段（通常是字符串矢量）获取值，将它们组合为由给定分隔符分隔的单一字符串，并将结果字符串放在给定输出字段中。

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 评论 </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 默认 </td> 
   <td colname="col2"> 在满足条件但输入值不可用时所使用的默认值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔符 </td> 
   <td colname="col2"> <p>用于在单个输出字符串中分隔输入字符串矢量的各个元素的字符串。 </p> <p> 如果按住 Ctrl 键并且右键单击 Delimiter（分隔符）参数内部，则会显示“<span class="wintitle">插入</span>”菜单。此菜单包含通常用作分隔符的特殊字符列表。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 组合以形成输出字符串的字符串值矢量。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输出 </td> 
   <td colname="col2"> 输出字符串的名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

在此示例中，假定字符串的输入矢量包含一组选择购买的产品。这些产品放在单一输出字符串中并采用“::”（两个冒号）分隔。

![](assets/cfg_TransformationType_Merge.png)

因此，如果输入字段x-products包含字符串值B57481、C46355和Z97123，则生成的输出字符串x-show-products将为B57481::C46355::Z97123。
