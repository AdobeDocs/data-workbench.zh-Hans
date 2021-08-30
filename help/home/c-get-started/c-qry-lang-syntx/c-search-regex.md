---
description: Data Workbench 利用正则表达式 (regex) 执行搜索和分类操作。
title: 正则表达式
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 68%

---

# 正则表达式{#regular-expressions}

Data Workbench 利用正则表达式 (regex) 执行搜索和分类操作。

在&#x200B;**[!UICONTROL Search]**&#x200B;字段中，您可以使用常用表达式执行“re：”语句后面的搜索，例如：

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元字符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>。（点号） </p> </td> 
   <td colname="col2"> <p>匹配单个字符，例如：<span class="filepath">re:x.z</span> 匹配“xyz”或“xxz”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>*（星号） </p> </td> 
   <td colname="col2"> <p>匹配一个或多个字符，例如：<span class="filepath">re:Z*</span> 匹配“ZZZ”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? （通配符） </p> </td> 
   <td colname="col2"> <p>匹配 0 个或 1 个字符以执行最低匹配，例如：<span class="filepath">xy?z</span> 匹配“xy”和“xyz”。 </p> </td> 
  </tr> 
 </tbody> 
</table>

其他常见的正则表达式也可以用于创建更加复杂的搜索字符串。正则表达式可用于所有Data Workbench搜索字段，包括查询实体面板。

请参阅[正则表达式](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)了解详细信息。
