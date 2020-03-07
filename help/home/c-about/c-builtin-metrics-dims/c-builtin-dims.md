---
description: 数据工作台包括内置维。
solution: Analytics
title: 内置维度
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 内置维度{#built-in-dimensions}

数据工作台包括内置维。

下表列出了Data Workbench的可用内置维：

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
   <td colname="col4">具有与所有维的所有元素相关的单个元素“”。 在“无”上评估度量与在无维上评估度量类似。 <p>过 <span class="filepath"> 滤器[None=""]</span> 等于 <span class="filepath"> [True]</span>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一个（隐藏） </td> 
   <td colname="col2"> 数值 </td> 
   <td colname="col3"> 不适用 </td> 
   <td colname="col4">元素“1”也具有序数值 <span class="filepath"> = 1</span>，它与所有维的所有元素相关。 One dimension通常用于使用以下语法构建计数： <p><span class="filepath"> sum(one, Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

