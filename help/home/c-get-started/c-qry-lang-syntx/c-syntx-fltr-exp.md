---
description: 过滤器是定义数据集中数据子集的表达式。
title: 过滤器表达式的语法
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 94%

---

# 过滤器表达式的语法{#syntax-for-filter-expressions}

{{eol}}

过滤器是定义数据集中数据子集的表达式。

根据维度间的关系，过滤器会允许或拒绝每个维度的每个元素。

可以使用 [!DNL Filter Editor]. 请参阅 [过滤器编辑器](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

在下表中，每个语法描述包括一个使用该过滤器的量度表达式的示例。例如，“会话”[True] 是使用“True”过滤器定义的量度。 会话[True] 量度与“会话”量度相同，因为“true”过滤器允许“会话”维度的每个元素。

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>常量过滤器。允许每个维度的每个元素。 </p> <p>示例：Sessions[ True ] 与 Sessions 相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>常量过滤器。拒绝每个维度的每个元素。 </p> <p>示例：Sessions[ False ] 始终为零。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>not Filter </p> </td> 
   <td colname="col2"> <p>允许 Filter 拒绝的元素。 </p> <p>示例：Sessions[ not Page=”A” ] 是未访问页面 A 的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA and FilterB </p> </td> 
   <td colname="col2"> <p>允许 FilterA 和 FilterB 所允许的元素。 </p> <p>示例：Sessions[ Page=”A” and Page=”B” ] 是同时访问页面 A 和页面 B 的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA or FilterB </p> </td> 
   <td colname="col2"> <p>允许 FilterA 或 FilterB 所允许的元素。 </p> <p>示例：Sessions[ Page=”A” or Page=”B” ] 是访问页面 A 或页面 B 或者同时访问二者的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filter by Dim </p> </td> 
   <td colname="col2"> <p>允许 Filter 所允许的维度 Dim 的元素集。 </p> <p>示例：Sessions[ Page=”/home” by Visitor ] 是浏览“/home”页面的访客所进行的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标识符 </p> </td> 
   <td colname="col2"> <p>引用其他在配置文件中定义的过滤器。 </p> <p>示例：Sessions[ Broken_Session_Filter ] 是无效会话过滤器允许的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 的给定元素。 </p> <p>示例：Sessions[ Page=”A” ] 是访问页面 A 的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>Dim != "Value" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 的每个其他元素。 </p> <p>示例：Sessions[ Page&lt;&gt;”A” ] 是访问除页面 A 以外的任何页面的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>允许维度 Dim 中具有给定序数值的元素。 </p> <p>示例：Sessions[ Month=#0 ] 是数据集第一个月中的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>Dim != #Ordinal </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 的每个其他元素。 </p> <p>示例：Sessions[ Session_Value &lt;&gt; #0 ] 是具有非零会话值的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim matches "Expr" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 中与给定正则表达式相匹配的元素。Dim 不得为非正规或可计数的维度。 </p> <p>示例：Sessions[ URI matches “.*/product/.*” ] 是访问产品目录中任何页面的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim notmatches "Expr" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 中与给定正则表达式不相匹配的元素。Dim 不得为非正规或可计数的维度。 </p> <p>示例：Sessions[ URI notmatches “.*\.jsp” ] 是所访问页面不是 JSP 页面的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 中其序数值小于元素“Value”序数值的元素。如果“Value”不是维度的元素，则会假设它大于维度的任何当前元素。 </p> <p>示例：Sessions[ Month &lt; “Jul ‘04” ] 是 2004 年 7 月前发生的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; “Value” </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 中其序数值大于元素“Value”序数值的元素。如果“Value”不是维度的元素，则会假设它大于维度的任何当前元素。 </p> <p>示例：Sessions[ Month &gt; “Jul ‘04” ] 是 2004 年 7 月后发生的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 中其序数值小于或等于元素“Value”序数值的元素。如果“Value”不是维度的元素，则会假设它大于维度的任何当前元素。 </p> <p>示例：Sessions[ Session_Number &lt;= “2” ] 是作为访客发起的第一个或第二个会话的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= “Value” </td> 
   <td colname="col2"> <p>允许维度 Dim 中其序数值大于或等于元素“Value”序数值的元素。如果“Value”不是维度的元素，则会假设它大于维度的任何当前元素。 </p> <p>示例：Sessions[ Session_Number &gt;= “5” ] 是作为访客发起的第五个或更多会话的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>any Dim </p> </td> 
   <td colname="col2"> <p>允许维度 Dim 的所有元素。 </p> <p>示例：Sessions[ any Page_View ] 是至少具有一次页面查看的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>允许 any Dim 拒绝的元素。 </p> <p>示例：Sessions[ no Page_View ] 是没有页面查看的会话数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTER) </p> </td> 
   <td colname="col2"> <p>与 FILTER 相同，用于分组过滤器表达式的某一部分。 </p> </td> 
  </tr> 
 </tbody> 
</table>
