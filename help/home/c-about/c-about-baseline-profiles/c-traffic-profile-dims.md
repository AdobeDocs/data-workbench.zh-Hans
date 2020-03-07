---
description: 流量配置文件包含以下维度以帮助识别访客操作。
solution: Analytics
title: 流量配置文件维度
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 流量配置文件维度{#traffic-profile-dimensions}

流量配置文件包含以下维度以帮助识别访客操作。

下表中的维在Traffic\Dataset\Transformation directory中的转换数据集包含文件中定义。

| 名称 | 类型 | 级别 | 描述 |
|---|---|---|---|
| 日 | 简单 | 会话 | 会话的第一个日志条目的日期。 |
| 每周时间 | 简单 | 会话 | 会话的第一个日志条目的星期。 |
| 确切的页面持续时间（隐藏） | 数值 | 页面查看 | 页面视图的持续时间（以毫秒为单位），通过从该页面视图的时间中减去下一页面视图的时间来度量。 会话中最后一个页面视图的确切持续时间始终为0。 |
| 小时 | 简单 | 会话 | 会话的第一个日志条目的小时数。 |
| 每天时间 | 简单 | 会话 | 会话的第一个日志条目的一小时。 |
| 月 | 简单 | 会话 | 会话的第一个日志条目的月份。 |
| 页面查看 | 可计数 | 会话 | 满足“页面查看条件”的日志条目或“事件数据记录”。 |
| 反向链接 | 简单 | 会话 | 会话第一个日志条目的引荐的二级域（如果是内部引荐域，则为“无”）。 |
| 会话 | 可计数 | 访客 | 访客的相关连续活动的时间段。 它由30分钟不活动时间和外部引用域或最长48小时的会话持续时间分隔。 可以在文件中配置这些超时和被视为内部的域集。 [!DNL Transformation.cfg] |
| URI | 简单 | 页面查看 | 页面查看的URI主干。 可以使用ReplaceURI、PrependURI和AppendURI转换重新定义URI维。 |
| 访客 | 可计数 | 不适用 | x-trackingid的唯一值。 通常对应于使用永久cookie的唯一浏览器。 x-trackingid可能基于IP编号或某些其他唯一标识符（如x.509通用名称）。 |
| 周 | 简单 | 会话 | 会话的第一个日志条目的周。 |

下表中的维在流量配置文件的维目录中定义：

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 维度 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col03" class="entry"> 级别 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 浏览器 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客使用的用户代理类型，包括版本号（例如，MSIE 6.0）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 浏览器类型 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客使用的用户代理类型（例如，MSIE）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 访客从指定搜索引擎搜索时访客会话中的第一个搜索引擎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下一个URI </td> 
   <td colname="col2"> 派生（基于URI维的ShiftDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 当前选定URI之后的下一个URI的URI。 此派生维度用于分析访客在任何给定URI后接下来的操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一次性与重复 </td> 
   <td colname="col2"> 派生（基于重复访客和一次性访客量度的SegmentDim） </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客类型：一次或重复。 一次访问者在网站上只有一个会话，而重复访问者有多个会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面 </td> 
   <td colname="col2"> 派生（基于URI维的RenameDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 会话期间访问的每个页面的名称。 最初，每个页面的名称与URI相同，但可以更改以便更轻松地进行解释。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向链接 </td> 
   <td colname="col2"> 从内置参照维继承 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 首先将会话引用到站点的网站的二级域名（由访客的浏览器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索短语 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 当访客从指定的搜索引擎进行搜索时，搜索引擎传递的访客会话中的第一个搜索短语。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索词 </td> 
   <td colname="col2"> 多对多 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 当访客通过指定搜索引擎的搜索引擎点进进行搜索时，搜索引擎传递的每个搜索词。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> 派生（基于“确切页面持续时间”度量的MetricDim） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话的持续时间（以30秒为增量）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话编号 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 访客访问网站的次数。 例如，首次访问者的会话编号为“1”，第二次访问者的会话编号为“2”，等等。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话页面查看次数 </td> 
   <td colname="col2"> 派生（基于页面查看次数的MetricDim） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话中的页面查看次数。 例如，在“会话页面视图”维中选择“3”将选择具有3个页面视图的所有会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 第一个网站的第二级域名，该网站是指定的搜索引擎，在会话期间（由访客的浏览器提供）将访客引用到该站点。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间维度 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话开始的小时、日、小时、周、周、日、月、季或年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间报表维 </td> 
   <td colname="col2"> 派生（基于内置时间维的LastN和重命名维） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 维度包括天前、上个月的天、上周的天、本月的天、本周的天、今天的小时、昨天的小时、过去12个月、过去2个月、过去2周、过去24小时、最后3个月、最后4周、最后6个月7天，过去7天和今天，过去8周，过去9个月，上个月，上周，几个月前，本月，本周，这和过去14天，这和过去6个月，今天和过去8周，今天，今天，今天和过去30天，Ago和Yesterday为构建总是显示数据集中一部分数据的工作区或报告提供了一种便捷的方法。 每个会话都基于会话开始的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 从内置的维URI继承 </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 查看的每个页面的URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客页面查看次数 </td> 
   <td colname="col2"> 派生（基于页面查看次数的MetricDim） </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客迄今为止的页面查看次数。 例如，在“访客页面查看次数”维度中选择“3”将选择所有会话中具有3次页面查看次数的所有访客。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客反向链接 </td> 
   <td colname="col2"> 从内置维度引用继承 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 首先将访客引用到网站进行其第一个会话的网站的二级域名（由访客的浏览器提供）。 </td> 
  </tr> 
 </tbody> 
</table>

