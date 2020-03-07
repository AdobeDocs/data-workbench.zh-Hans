---
description: 可计数维度的元素可由系统计算。
solution: Analytics
title: 可计数维度
topic: Data workbench
uuid: 3312f5eb-69b9-43af-b32a-5c40e3050b29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 可计数维度{#countable-dimensions}

可计数维度的元素可由系统计算。

可计数维度通常用于创建求和量度，这些量度会返回维度的所有元素计数或总和。您可以定义可计数维度来统计实例（如预订或产品订单数目）。例如，您可以定义可计数维度“订单”，该维度的元素（与来自在线商店的订单对应的日志条目）可以进行统计。如果您想要在可视化内显示订单计数，则需要定义“订单”求和量度，该量度可对维度进行计算，或对维度应用过滤器。

可计数维度可以是其他维度的父维度，也可以是其他可计数维度的子维度。

>[!NOTE]
>
>如果您需要一个只提供某项计数的维，则应使用一个数字维，并且运算为COUNT。 请参 [阅数字维](../../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)。

可计数维度由以下参数定义：

<table id="table_9F3F093F5B074EA68CA4DCE731161F6C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 默认值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 向 Data Workbench 中的用户显示的描述性维度名称。维度名称不能包含连字符 (-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments（备注） </td> 
   <td colname="col2"> 可选。有关扩展维度的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition（条件） </td> 
   <td colname="col2"> 输入字段可用于创建可计数维度的条件。如果指定，则会有一个条件限制可向数据集架构中的维度及其所有子项显示的日志条目集。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hidden（隐藏） </td> 
   <td colname="col2"> 确定维度是否显示在 Data Workbench 界面中。默认情况下，此参数设为 false。例如，如果维度仅用作量度的基础，则可以将此参数设为 true，以在 Data Workbench 显示中隐藏维度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 键 </td> 
   <td colname="col2"> <p>可选。用作键的字段名称。如果您定义此参数，则对于可计数维度的父项元素与指定为键的字段不同值的每个组合，可计数维度都将存在一个对应的元素。 </p> <p> 可计数维度的每个元素都需要与一组连续的日志条目相关联。因此，如果日志条目没有按照键进行排序，则每次键字段更改时，都会为可计数维度创建一个元素。为了防止出现这种情况，Adobe 建议您使用按时间顺序连续的唯一键。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent（父项） </td> 
   <td colname="col2"> <p>父维度的名称。任何可计数维度都可以是父维度。若要使维度成为数据集架构中的顶级维度，请将该参数设为“根”。已定义的维度将成为数据集的根可计数维度。例如，如果您使用 Site，则“访客”维度就是数据集的根可计数维度。 </p> <p> <p>注意：尽管根可计数维度不必与数据中的跟踪 ID 相关联，但 Adobe 建议您将数据集的根可计数维度配置为使用跟踪 ID 字段 (x-trackingid) 作为其“键”。这样，根可计数维度的每个元素都将与 x-trackingid 的唯一值相关联，并且有关每个元素的所有数据都会分到一组。如果您想要以不同的方式配置数据集，请联系 Adobe。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此示例使用从网站流量收集的事件数据说明对可计数维度的定义。可计数维度会统计指定会话中的 Web 营销活动事件。假定所有电子邮件营销活动资源都通过将“email=”作为 cs-uri-query 的一部分从 Web 服务器请求。在该示例中，主要关注的是访客在指定会话期间响应电子邮件营销活动的次数，而不是 cs-uri-query(email) 字段的实际值。

![](assets/cfg_Transformation_Dim_Countable.png)

此示例还使用从网站流量收集的事件数据说明对可计数维度的定义，但它有一个定义的 Key（键）参数。“会话”可计数维度使用 x-session-key 字段作为键。（x-session-key 字段是 [!DNL Sessionize] 转换的输出，并且对于每个会话都有一个唯一的值。）“访客”维度（父项）元素与 x-session-key 字段的每个唯一组合是“会话”维度的一个元素。

![](assets/cfg_Transformation_Dim_Countable2.png)

