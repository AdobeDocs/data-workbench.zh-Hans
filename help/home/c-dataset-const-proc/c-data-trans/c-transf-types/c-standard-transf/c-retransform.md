---
description: RETransform（正则表达式）转换是一种模式匹配转换，该转换使用正则表达式指定一个要在输入中查找和捕获的模式，并将捕获的字符串存储在指定的输出字段中。
title: RETransform
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
exl-id: 2595f782-0efb-4a2a-84bd-fdb04baf0852
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 89%

---

# RETransform{#retransform}

RETransform（正则表达式）转换是一种模式匹配转换，该转换使用正则表达式指定一个要在输入中查找和捕获的模式，并将捕获的字符串存储在指定的输出字段中。

正则表达式针对整个输入字符串进行计算。如果输入与正则表达式中指定的模式不匹配，则不会捕获任何数据。有关使用正则表达式的简要指南，请参阅 [正则表达式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

>[!NOTE]
>
>[!DNL RETransform]转换的操作与[!DNL REMatch]转换类似（请参阅[REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)），后者在常规表达式中为每个捕获子模式构建一个输出字段。 您可以将[!DNL RETransform]视为[!DNL REMatch]和[!DNL Format]转换的组合。 如果 Action（操作）参数（请参阅下表中的 Action（操作））设为“RESULTS”，则 [!DNL RETransform] 的运算方式类似于 [!DNL REMatch] 和 [!DNL Union] 转换的组合。

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
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
   <td colname="col2"> 在满足条件但输入值不可用或正则表达式与输入值不匹配时所使用的默认值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>指定如何看待结果。默认设置 RESULTS 仅获取匹配的模式，并从正在提取的模式创建字符串矢量。 </p> <p> 此外，操作也可以是一个格式设置字符串，用于创建特定格式的简单字符串输出。使用此技术，可以在 % 符号之间指定与每个匹配模式的“位置”对应的数字。例如，第 1 个匹配模式将是 %1%，第 3 个匹配模式将是 %3%。您可以在格式设置字符串中以文本形式指定其他字符。 </p> </td> 
   <td colname="col3"> RESULTS </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 表达式 </td> 
   <td colname="col2"> 用于匹配的正则表达式。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input（输入） </td> 
   <td colname="col2"> 计算正则表达式所针对的字段。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output（输出） </td> 
   <td colname="col2"> 输出字符串的名称。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] 转换可能非常慢，并且可能占据大量数据处理时间。

此示例隔离网站访客所使用的 Windows 操作系统版本，并从该值创建一个 x-windows-version 字段。在此情况下，输出值仅为版本号。

![](assets/cfg_TransformationType_RegularExpression.png)

如果您希望在版本号之前包括字符串“Version”以提高可读性，则需要将 Action（操作）参数从“RESULTS”更改为“Version %1%”。若要在输出中包括文本形式的百分号 (%)，请使用第二个百分号对其进行转义，如“%%”。
