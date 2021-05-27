---
description: Math 转换允许对日志条目中的字段使用算术运算。
title: Math
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 97%

---

# 数学{#math}

Math 转换允许对日志条目中的字段使用算术运算。

运算可以包括十进制整数和浮点常量。

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
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
   <td colname="col1"> 表达式 </td> 
   <td colname="col2"> <p>描述要执行的计算的算术表达式。 </p> <p> 您可以使用下面列出的任何运算和函数，并且可以在表达式中包含字段名称： </p> <p> 操作 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> 加 (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> 减 (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> 乘 (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> 除 (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> 余数 (%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> 求幂 (^) </li>
     </ul></p> <p>函数 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x)。如果 x 为正数则返回 1，如果 x 为零则返回 0，如果 x 为负数则返回 –1。 </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x)。返回 x 的绝对值。 </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> floor(x)。返回小于或等于 x 的最大整数。 </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x)。返回 x 的最近似整数。 </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x)。返回以 b 为底的 x 的对数。 </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> min(x,y,...)。返回其所有参数的最小值。 </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...)。返回其所有参数的最大值。 </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output（输出） </td> 
   <td colname="col2"> 包含算术运算结果的字段名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

本示例使用从网站流量收集的数据字段，名为 x-page-duration 的新字段的计算方式是从 x-timestamp 中减去 x-last-pv-timestamp，然后再加 1。只有在用户定义的字段 x-last-pv-timestamp（它表示访客最近一次页面查看的时间戳）被填充或“不为空”的情况下，才会计算输出。

![](assets/cfg_TransformationType_Math.png)

有关[!DNL Not Empty]条件的信息，请参阅[条件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。
