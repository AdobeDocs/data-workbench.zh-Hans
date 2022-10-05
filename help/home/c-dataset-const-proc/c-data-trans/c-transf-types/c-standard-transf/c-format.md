---
description: Format 转换获取一组输入并设置它们的格式，以创建与给定结构匹配的输出。
title: 格式
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---

# 格式{#format}

{{eol}}

Format 转换获取一组输入并设置它们的格式，以创建与给定结构匹配的输出。

该转换处理简单字符串或字符串矢量，并通过将给定格式应用到每个输入值，直至转换所有输入值来生成输出。

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> 格式 </td> 
   <td colname="col2"> <p>用于指定输出外观的格式设置字符串。 </p> <p> %1% 是指来自第一个输入矢量的值，%2% 是指来自第二个输入矢量的值，依此类推。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inputs（输入） </td> 
   <td colname="col2"> <p>包含简单字符串或字符串矢量的字段。在将字符串矢量作为输入时，输出也将是字符串矢量，这些矢量通过将 <span class="wintitle">Format</span>（格式）参数应用到每组输入值而产生。 </p> <p> <p>注意：输入的编号从 0 开始，但格式替代值的编号从 %1% 开始。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 输出 </td> 
   <td colname="col2"> 创建的用于包含转换结果的字段名称。如果输入是字符串矢量，则输出字符串矢量的长度将是最长输入矢量的长度。如果某些输入字符串矢量长度较短，则会使用空字符串填充它们在格式字符串中的位置，直至达到输出矢量的长度。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

此示例中有两个矢量，一个是表示产品类别的字符串矢量，另一个是表示每种产品购买数量的对应字符串矢量，这两个矢量将分别转换为长度相同且采用以下形式的矢量：Product %1%, Quantity %2%。

![](assets/cfg_TransformationType_Format.png)

如果输入矢量包含产品类别 (683, 918) 和数量 (10, 4)，则结果将是一个包含以下两个字符串的最终输出矢量：(&quot;Product 683, Quantity 10&quot;, &quot;Product 918, Quantity 4&quot;)。
