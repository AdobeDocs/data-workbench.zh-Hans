---
description: 如果您要处理从网站流量收集的数据，则可以使用 Sessionize 转换确定如何定义会话。
solution: Analytics
title: Sessionize
topic: Data workbench
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sessionize{#sessionize}

如果您要处理从网站流量收集的数据，则可以使用 Sessionize 转换确定如何定义会话。

该转换获取时间戳和跟踪 ID 作为其输入，并为每个日志条目输出一个会话编号。对于具有给定跟踪 ID 的第一个会话，会话编号是“1”；对于具有相同跟踪 ID 的第二个会话，会话编号是“2”，依此类推。输出可以直接用作会话键，因为它对于每个会话都有一个唯一值。

>[!NOTE]
>
>若要使用 [!DNL Sessionize] 转换，数据必须按时间排序并按源数据中的跟踪 ID 分组。因此， [!DNL Sessionize] 仅当在文件或文件中定 [!DNL Transformation.cfg] 义时才可 [!DNL Transformation Dataset Include] 用。

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
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
   <td colname="col2"> 转换的描述性名称。可以在此处输入任何名称。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comments（备注） </td> 
   <td colname="col2"> 可选。有关转换的说明。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condition（条件） </td> 
   <td colname="col2"> 应用此转换的条件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Timestamp（输入时间戳） </td> 
   <td colname="col2"> 包含要使用的时间戳值的字段。 </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input Tracking ID（输入跟踪 ID） </td> 
   <td colname="col2"> <p>包含要使用的跟踪 ID 值的字段。该值必须是一个 64 位（16 位数）或更小的十六进制数字，或者 16 位数或更少的十进制整数。 </p> <p> <p>注意：如果您希望将 x-trackingid 以外的字段用于跟踪 ID，则需要首先获取该字段的散列值。请参阅 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> 哈希</a>。 </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximum Session Duration（最大会话时长） </p> </td> 
   <td colname="col2">启动新会话之前的最长会话长度（这可防止具有自动内容刷新功能的网页创建任意长度的会话）。如果满足<span class="wintitle">超时条件</span>，并且某个单击的反向链接设为 Internal Domains（内部域）参数中的条目之一，则将使用最大会话时长定义会话的结束。无论会话包含多少次单击，任何会话都不会长于指定的最大会话时长。建议的值为 48 小时。有关 Maximum Session Duration（最大会话时长）和 Internal Domains（内部域）参数的详细信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web 数据的配置设置</a>. </td> 
   <td colname="col3"> 48 小时 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output Session Number（输出会话编号） </td> 
   <td colname="col2"> 存储会话编号的字段。此字段对每位访客的每次会话都有一个唯一的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话超时 </td> 
   <td colname="col2"> <p>给定访客的日志条目之间需要经过的时间量，用于确定一个会话的结尾和新会话的开头（即用于定义用户会话的典型超时）。此参数的建议值是 30 分钟。如果不满足超时条件，并且某个单击的反向链接未设为 Internal Domains（内部域）参数中的反向链接之一，则将使用会话超时定义会话。 </p> <p> 如果满足超时条件并且某个日志条目的 cs(referrer-domain) 位于内部域列表中，则最大会话时长将确定当前日志条目是现有会话的一部分还是新会话的开头。 </p> <p> 有关 Session Timeout（会话超时）参数的详细信息，请参阅 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web 数据的配置设置</a>. </p> </td> 
   <td colname="col3"> 30 分钟 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout Condition（超时条件） </td> 
   <td colname="col2"> 日志条目被视为新会话的开始必须满足的条件。请注意，日志条目与上一日志条目之间经过的时间量必须至少为 Session Timeout（会话超时）参数的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

当发生以下任一情况时，新会话将会开始：

* 更改了跟踪 ID。
* 自上一个日志条目起持续的时间至少等于 Session Timeout（会话超时）参数的值并且满足超时条件。
* 自上一次会话的第一个日志条目起持续的时间超过 Maximum Session Duration（最大会话时长）参数的值。

>[!NOTE]
>
>If you have already defined Maximum Session Duration and Session Timeout as parameters in the [!DNL Session Parameters.cfg] file, do not enter values for them in the configuration. 如下例所示，可以通过键入 *$(参数名称)* 引用这些参数。有关这些参数的详细信息，请参阅 [Web 数据的配置设置](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

此示例中的 [!DNL Sessionize] 转换将 x-timestamp 和 x-trackingid 字段作为其输入，并在 x-session-key 字段中记录每个日志条目的会话编号。The transformation&#39;s [!DNL Timeout Condition] is based on a [!DNL Neither] condition: If the cs(referrer-domain) field for a log entry matches a member of the Internal Domains parameter, the condition evaluates to false. 请注意对 Internal Domains（内部域）和 Session Timeout（会话超时）参数的引用。

有关该工具的信 [!DNL NeitherCondition]息，请参阅 [条件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。 有关“内部域”和“会话超时”参数的信息，请参 [阅Web数据的配置设置](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

![](assets/cfg_TransformationType_Sessionize.png)

