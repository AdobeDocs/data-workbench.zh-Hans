---
description: Data Workbench包含内置维度。
title: 内置维度
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 15%

---

# 内置维度{#built-in-dimensions}

{{eol}}

Data Workbench包含内置维度。

下表列出了Data Workbench的可用内置维度：

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 详细信息 </th> 
   <th colname="col3" class="entry"> 级别 </th> 
   <th colname="col4" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 无 </td> 
   <td colname="col2"> 派生 </td> 
   <td colname="col3"> 不适用 </td> 
   <td colname="col4">具有一个与所有维度的所有元素相关的元素“”。 通过“无”来评估量度，与通过任何维度来评估量度类似。 <p>的 <span class="filepath"> 筛选[无=""]</span> 等于 <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一个（隐藏） </td> 
   <td colname="col2"> 数值 </td> 
   <td colname="col3"> 不适用 </td> 
   <td colname="col4">元素“1”，其也具有序数值 <span class="filepath"> = 1</span>，与所有维度的所有元素相关。 “一个”维度通常用于使用以下语法构建计数： <p><span class="filepath"> sum(one，Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
