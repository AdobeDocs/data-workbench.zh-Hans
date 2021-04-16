---
description: Data Workbench包括内置维度。
title: 内置维度
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 15%

---

# 内置维度{#built-in-dimensions}

Data Workbench包括内置维度。

下表列表了Data Workbench的可用内置维：

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
   <td colname="col4">具有与所有维的所有元素相关的单个元素“”。 在“无”上评估量度就像在无维度上评估量度。 <p><span class="filepath">过滤器[None=""]</span>等效于<span class="filepath"> [True]</span>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一个（隐藏） </td> 
   <td colname="col2"> 数值 </td> 
   <td colname="col3"> 不适用 </td> 
   <td colname="col4">元素"1"也具有序数值<span class="filepath"> = 1</span>，与所有维度的所有元素相关。 One dimension通常用于使用以下语法构建计数： <p><span class="filepath"> sum(one，Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
