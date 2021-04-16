---
description: 显示在构建转换时有哪些适用约定的表格。
title: 构建转换的约定
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 96%

---

# 构建转换的约定{#conventions-for-constructing-transformations}

显示在构建转换时有哪些适用约定的表格。

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 约定 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 顺序执行 </td> 
   <td colname="col2"> <p>数据集配置文件内的转换会按顺序（即按它们在配置文件中列出的顺序）应用于日志条目。因此，转换必须按照输出用作其他转换的输入的顺序列出。更具体地说，如果一个转换的输出用作另一个转换的输入，则在数据集配置文件中应务必先列出前一个转换，然后再列出后一个转换。否则，Data Workbench Server 会生成错误。 </p> <p> 处理阶段提供了一种对多个数据集包含文件中定义的转换进行排序的方式。对于与特定处理阶段关联的所有数据集包含文件，转换基于其输入和输出进行排序。此外，如果一个阶段中的多个数据集包含文件将数据作为转换结果输出到同一个字段，则 Data Workbench Server 会生成错误。 </p> <p> 有关各阶段的详细信息，请参阅  <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 日志处理配置文件</a>、 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> 转换配置文件</a>，以及 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 数据集包含文件</a>。 </p> <p>“<span class="wintitle">转换依赖关系图</span>”可以显示一个字段是如何被一系列转换修改的。请参阅<a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md">数据集配置工具</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输出名称 </td> 
   <td colname="col2"> 大多数转换指定一个输出字段。如果输出是一个用户定义的扩展字段，则此字段的名称必须以“x–”开头。输出字段名称不能包含空格或特殊字符。扩展字段的名称可以采用混合大小写（如“x-NewCampaignName”或“x-New-Campaign-Name”）以提高可读性，但软件会将其视为不区分大小写。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输入字段 </td> 
   <td colname="col2"> <p>输入字段是指某个基准字段或从先前转换输出生成的用户创建字段。如果需要常量字符串，可以使用加引号的字符串代替基准字段或用户创建的字段。 </p> <p> 有关 Data Workbench Server 可处理的一些常见定义数据字段的列表，请参阅 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> 事件数据记录字段</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 简单字符串和字符串矢量 </td> 
   <td colname="col2"> 所有转换都针对字符串和/或字符串矢量进行操作。简单字符串是字符的文本序列。字符串矢量包含零个简单字符串或按特定顺序排列的多个简单字符串。 </td> 
  </tr> 
 </tbody> 
</table>
