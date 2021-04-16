---
description: 流量用户档案包含以下维度，以帮助识别访客操作。
title: 流量配置文件维度
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 10%

---

# 流量配置文件维度{#traffic-profile-dimensions}

流量用户档案包含以下维度，以帮助识别访客操作。

下表中的维度是在Traffic\Dataset\Transformation directory文件夹中的转换数据集包含文件中定义的。

| 名称 | 类型 | 级别 | 描述 |
|---|---|---|---|
| 日 | 简单 | 会话 | 会话的第一个日志条目的日期。 |
| 每周时间 | 简单 | 会话 | 会话的第一个日志条目的星期。 |
| 确切页面持续时间（隐藏） | 数值 | 页面查看 | 页面视图的持续时间（以毫秒为单位），通过从该页面视图的时间中减去下一页面视图的时间来度量。 会话中最后一页视图的确切持续时间始终为0。 |
| 几 | 简单 | 会话 | 会话的第一个日志条目的小时数。 |
| 小时 | 简单 | 会话 | 会话的第一个日志条目的一天中的小时。 |
| 月 | 简单 | 会话 | 会话的第一个日志条目的月份。 |
| 页面查看 | 可计数 | 会话 | 满足页面事件条件的日志条目或“视图数据记录”。 |
| 反向链接 | 简单 | 会话 | 会话第一个日志条目推荐人的第二级域(如果是内部推荐人域，则为“无”)。 |
| 会话 | 可计数 | 访客 | 由访客关联的连续活动的周期。 它以30分钟不活动时间和外部推荐人域或最长48小时会话持续时间分隔。 可以在[!DNL Transformation.cfg]文件中配置这些超时和被认为是内部的域集。 |
| URI | 简单 | 页面查看 | 页面视图的URI茎。 可以使用ReplaceURI、PrependURI和AppendURI转换重新定义URI维。 |
| 访客 | 可计数 | 不适用 | x-trackingid的唯一值。 通常对应于使用永久cookie的唯一浏览器。 x-trackingid可能基于IP号或某些其他唯一标识符（如x.509通用名称）。 |
| 周 | 简单 | 会话 | 会话的第一个日志条目的周。 |

下表中的维在“流量”用户档案的Dimension目录中定义：

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
   <td colname="col3"> 访客使用的用户代理类型，包括版本号（例如MSIE 6.0）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 浏览器类型 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客使用的用户代理类型（例如MSIE）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 当访客从指定的搜索引擎中搜索时，访客会话中的第一个搜索引擎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下一个URI </td> 
   <td colname="col2"> 派生（基于URI维度的ShiftDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 当前选定的URI之后下一个URI的URI。 此派生维度用于分析在任何给定URI之后访客接下来会执行什么操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime与Repeat </td> 
   <td colname="col2"> 派生(基于重复访客和一次性访客量度的SegmentDim) </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客类型：一次或重复。 一次性访客在网站上只有一次会话，而重复访客有多次会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面 </td> 
   <td colname="col2"> 派生（基于URI维的RenameDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 会话期间访问的每个页面的名称。 最初，每个页面的名称与URI相同，但可以更改以便更轻松地进行解释。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向链接 </td> 
   <td colname="col2"> 从内置推荐人维继承 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 首先将会话引荐给网站的网站的二级域名(由访客的浏览器提供)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索短语 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 当访客从指定的搜索引擎搜索时，搜索引擎传递的访客会话中的第一个搜索短语。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索词 </td> 
   <td colname="col2"> 多对多 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 当访客具有来自命名搜索引擎的搜索推荐人点进时，搜索引擎传递的每个搜索词。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> 派生（基于“确切页面持续时间”量度的MetricDim） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 以30秒为增量的会话持续时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话编号 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 访客访问该站点的次数。 例如，首次访客的会话编号为“1”，第二次访客的会话编号为“2”，等等。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话页视图 </td> 
   <td colname="col2"> 派生(基于页面视图量度的MetricDim) </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话中的页面视图数。 例如，在“会话页面视图”维中选择“3”将选择所有具有3个页面视图的会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 第一个网站的第二级域名，该网站是命名的搜索引擎，在会话期间(由访客的浏览器提供)将访客引用到该网站。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间维度 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话开始的时、日、时、周、周、日、月、季或年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间报告Dimension </td> 
   <td colname="col2"> 派生（基于内置时间维度的LastN和重命名维度） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> Dimension包括天前，上个月的天，上个月的天，本月的天，本周的天，今天的小时，昨天的小时，过去12个月，过去2个月，过去2周，过去24小时，过去3个月，过去4周，过去6个月，7天，过去7天，今天，过去8周，过去9个月，上个月，上周，几个月前，本月，本周，这和过去14天，这和过去6个月，今天，今天，报告，今天和过去30天，Ago和Yesterday为构建总是显示数据集中一部分数据的工作区或报表提供了一种简便的方法。 每个会话都基于会话开始的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 从内置DimensionURI继承 </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 查看的每个页面的URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客页面视图 </td> 
   <td colname="col2"> 派生(基于页面视图量度的MetricDim) </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客的迄今页面视图数。 例如，在“访客页面视图”维中选择“3”，将选择所有访客，其所有会话中只有3个页面视图。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客反向链接 </td> 
   <td colname="col2"> 继承自内置维度推荐人 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 网站的第二级域名，该网站首先将访客引荐到其第一个会话的网站(由访客的浏览器提供)。 </td> 
  </tr> 
 </tbody> 
</table>
