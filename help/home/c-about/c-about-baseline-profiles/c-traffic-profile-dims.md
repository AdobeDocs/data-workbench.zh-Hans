---
description: 流量配置文件包含以下维度，以帮助识别访客操作。
title: 流量配置文件维度
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 10%

---

# 流量配置文件维度{#traffic-profile-dimensions}

{{eol}}

流量配置文件包含以下维度，以帮助识别访客操作。

下表中的维度在Traffic\Dataset\Transformation目录的转换数据集包含文件中定义。

| 名称 | 类型 | 级别 | 描述 |
|---|---|---|---|
| 日 | 简单 | 会话 | 会话中第一个日志条目的日期。 |
| 每周时间 | 简单 | 会话 | 会话中第一个日志条目的每周时间。 |
| 确切的页面持续时间（隐藏） | 数值 | 页面查看 | 页面查看的持续时间（以毫秒为单位），通过从该页面查看的时间中减去下一页面查看的时间来测量。 会话中最后一页查看的确切持续时间始终为0。 |
| 小时 | 简单 | 会话 | 会话中第一个日志条目的小时。 |
| 小时 | 简单 | 会话 | 会话中第一个日志条目的小时数。 |
| 月 | 简单 | 会话 | 会话第一个日志条目的月份。 |
| 页面查看 | 可计数 | 会话 | 满足页面查看条件的日志条目或“事件数据记录”。 |
| Referrer | 简单 | 会话 | 会话第一个日志条目反向链接的二级域（如果是内部反向链接域，则为“无”）。 |
| 会话 | 可计数 | 访客 | 访客的相关连续活动的时段。 它以30分钟的非活动状态时段和外部反向链接域或最长48小时的会话持续时间分隔。 可以在 [!DNL Transformation.cfg] 文件。 |
| URI | 简单 | 页面查看 | 页面查看的URI主体。 URI维度可以使用ReplaceURI、PrependURI和AppendURI转换重新定义。 |
| 访客 | 可计数 | 不适用 | x-trackingid的唯一值。 如果使用永久性Cookie，则通常对应于唯一的浏览器。 x-trackingid可能基于IP号或其他一些唯一标识符（如x.509通用名称）。 |
| 周 | 简单 | 会话 | 会话第一个日志条目的周。 |

下表中的维度在流量配置文件的Dimension目录中定义：

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
   <td colname="col3"> 访客使用的用户代理类型（例如MSIE）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 访客从指定的搜索引擎中搜索时访客会话中的第一个搜索引擎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下一个URI </td> 
   <td colname="col2"> 派生（基于URI维度的ShiftDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 当前选定的URI之后的下一个URI的URI。 此派生维度用于分析访客在任何给定URI后接执行的操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Onetime与Repeat </td> 
   <td colname="col2"> 派生（基于重复访客和一次性访客量度的SegmentDim） </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客类型：一次或重复。 一次性访客在网站上只有一个会话，而重复访客有多个会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面 </td> 
   <td colname="col2"> 派生（基于URI维度的RenameDim） </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 会话期间访问的每个页面的名称。 最初，每个页面的名称与URI相同，但可以更改以便于解释。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向链接 </td> 
   <td colname="col2"> 从内置反向链接维度继承 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 首次将会话引荐到网站的网站的二级域名（由访客的浏览器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索短语 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03">会话 <p>第一行 </p></td> 
   <td colname="col3"> 当访客从指定的搜索引擎中搜索时，搜索引擎传递的访客会话中的第一个搜索短语。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索词 </td> 
   <td colname="col2"> 多对多 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 当访客具有来自命名搜索引擎的搜索反向链接点进时，搜索引擎传递的每个搜索词。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> 派生（根据“确切页面持续时间”量度确定的MetricDim） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话的持续时间，以30秒为增量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话编号 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 访客访问网站的次数。 例如，首次访客的会话数为“1”，第二次访客的会话数为“2”，等等。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话页面查看次数 </td> 
   <td colname="col2"> 派生（基于页面查看次数量度的MetricDim） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话中的页面查看次数。 例如，在“会话页面查看次数”维度中选择“3”将只选择具有3个页面查看次数的所有会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜索引擎 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 第一个网站的第二级域名，该网站是指在会话期间将访客引荐到网站的命名搜索引擎（由访客的浏览器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间维度 </td> 
   <td colname="col2"> 简单 </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> 会话开始的时、日、日、日、周、日、月、季或年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 时间报表Dimension </td> 
   <td colname="col2"> 派生（基于内置时间维度的LastN和重命名维度） </td> 
   <td colname="col03"> 会话 </td> 
   <td colname="col3"> Dimension包括天前、上月日、上周日、本月日、本周日、今天小时、昨天小时、最近12个月、最近2个月、最近2周、最近24小时、最近3个月、最近4周、最近7天、最近7天、今天、最近8周、上9个月、上周、上月、本月、上周、本月、上周此和过去14天、此和过去6个月、此和过去8周、今天、今天、今天和过去30天、几周之前和昨天提供了一种构建工作区或报表的便捷方法，该工作区或报表始终显示数据集中的一部分数据。 每个任务都基于会话开始的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 从内置DimensionURI继承 </td> 
   <td colname="col03"> 页面查看 </td> 
   <td colname="col3"> 查看的每个页面的URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客页面查看次数 </td> 
   <td colname="col2"> 派生（基于页面查看次数量度的MetricDim） </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 访客迄今为止的页面查看次数。 例如，在“访客页面查看次数”维度中选择“3”，将选择所有会话中页面查看次数恰好为3的所有访客。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客反向链接 </td> 
   <td colname="col2"> 继承自内置维度反向链接 </td> 
   <td colname="col03"> 访客 </td> 
   <td colname="col3"> 首次将访客引荐到网站进行其第一个会话的网站的二级域名（由访客的浏览器提供）。 </td> 
  </tr> 
 </tbody> 
</table>
