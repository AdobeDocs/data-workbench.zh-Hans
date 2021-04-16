---
description: 非正规维度与其父可计数维度有一对一的关系。
title: 非正规维度
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 85%

---

# 非正规维度{#denormal-dimensions}

非正规维度与其父可计数维度有一对一的关系。

只要所需的维度对于其父项的每个元素都包含一个唯一的元素，您就可以定义非正规维度。例如，[!DNL EMail Address]是父级为访客的非正规维度。 每个“访客”都有一个电子邮件地址，“电子邮件地址”维度中的每个元素都是单个访客的电子邮件地址。即使两个访客拥有相同的电子邮件地址，这些地址也将是“电子邮件地址”维度的不同元素。

您可以在任何表可视化和详细信息表中使用非正规维度，也可以使用该维度创建过滤器。此外，您还可以将非正规维度与Data Workbench Server的区段导出功能结合使用，以导出具有大量值的字段（如[!DNL Tracking ID]或[!DNL EMail Address]）的值。 由于您想要导出的任何区段数据都必须定义为配置文件内的维度，因此您必须创建非正规维度来存储字段数据的原始字符串。

>[!NOTE]
>
>在需要正常维度的表或其他可视化中使用非正规维度时，将自动创建派生的非正规维度。 派生非正规维度与父维度有一对多的关系。

有关明细表可视化和过滤器的信息，请参阅《Data Workbench 用户指南》**&#x200B;中的“分析可视化”一章。有关区段导出的信息，请参阅《Data Workbench 用户指南》**&#x200B;中的“配置界面和分析功能”一章。

>[!NOTE]
>
>非正规尺寸在查询时间和磁盘空间方面可能非常昂贵。 父项为[!DNL Page View]且平均输入字符串为50字节的非正规维度可向典型大型数据集中的缓冲区添加25 GB的视图，相当于大约13个简单或数字页面维度，或大约125个会话级别维度。 在未对性能影响进行仔细评估的情况下，请勿将非正规维度添加到数据集中。

非正规维度由以下参数定义：

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col1"> 条件 </td> 
   <td colname="col2"> 在父项与输入字段值之间建立关系应该具备的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden（隐藏） </td> 
   <td colname="col2"> 确定维度是否显示在 Data Workbench 界面中。默认情况下，此参数设为 false。例如，如果维度仅用作量度的基础，则可以将此参数设为 true，以在 Data Workbench 显示中隐藏维度。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 与父维度（父项）相关的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalized Elements（正规化元素） </td> 
   <td colname="col2"> 性能调整参数，用于指定要将名称存储在系统内存中的维度元素数量。如果将此参数设为更大值，则会导致非正规维度使用更多的 RAM，但这同时会加快查询速度。默认值为 16383。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Operation（运算） </td> 
   <td colname="col2"> <p>可用的运算如下所示： </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> FIRST NONBLANK：使用第一个非空输入值，无论其是否来自第一个日志条目。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。 </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> FIRST ROW：使用与父维度元素相关的第一个日志条目的值，即使输入为空也是如此。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> LAST NONBLANK：使用最后一个非空输入值，无论其是否来自最后一个日志条目。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。 </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> LAST ROW：使用与父维度元素相关的最后一个日志条目的值，即使输入为空也是如此。如果 <span class="wintitle">Input</span>（输入）是一个矢量字段，则会使用相关日志条目的矢量中的第一行。如果此值为空或不是数字，或者相关日志条目不符合维度的条件，则不会使用任何值。 </li> 
     </ul> </p> <p> <p>注意：如果运算没有产生值，则使用空值 ("")。 </p> </p> <p> 您应该指定一个运算以确保维度按照预期进行定义。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> 父维度的名称。任何可计数维度都可以是父维度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例中显示的非正规维度将字段 x-trackingid 中的所有数据都用作输入，并将这些数据包含在名为“访客 ID”的维度中。对于您创建的访客区段，可以导出“访客 ID”维度（以及其他任何已定义维度）中的数据。

![](assets/cfg_Transformation_Dim_Denormal.png)
