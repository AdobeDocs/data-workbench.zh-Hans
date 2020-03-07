---
description: 流量配置文件包含以下用于识别访客流量的指标。
solution: Analytics
title: 流量配置文件指标
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 流量配置文件指标{#traffic-profile-metrics}

流量配置文件包含以下用于识别访客流量的指标。

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 度量公式和级别 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 登录 </td> 
   <td colname="col2">公式： <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 在每页上进入站点的会话数。 此度量仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出率 </td> 
   <td colname="col2">公式： <span class="filepath"> Exits/Page_Views </span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 从每页退出站点的会话百分比。 退出率量度只能在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 从每个页面退出站点的会话数。 此度量仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">公式： <span class="filepath"> (原始（访客）-((原始（访客）+ .69)^0.5 * 1.281551 - 1.2269))*(访客／原始（访客）)</span><p>级别：访客 </p></td> 
   <td colname="col3"> 由Insight报告的最低可能访客数的度量。 从数学上讲，它指定概率为90%的最低访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看持续时间 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> sum(exact_page_duration, page_view)*0.1/Page_Views[任何Exact_Page_Duration]</span></p> <p>级别：页面视图 </p> </td> 
   <td colname="col3"> 在特定页面或页面组上花费的平均时长(MM:SS)。 此度量仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每个会话的页面查看次数 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> Page_Views/(Sessions by Page_View) </span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 具有页面查看次数的每个会话中的平均页面查看次数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看次数 </td> 
   <td colname="col2">公式：sum( <span class="filepath"> One, Page_View)</span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 页面查看次数。 页面查看是对定义页面的请求（不计算对图像和其他类型的筛选内容的访问）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看次数百分比 </td> 
   <td colname="col2">公式： <span class="filepath"> Page_Views/total(Page_Views) </span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 页面查看的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话数百分比 </td> 
   <td colname="col2">公式：会 <span class="filepath"> 话／总数（会话）</span><p>级别：会话 </p></td> 
   <td colname="col3"> 会话百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客百分比 </td> 
   <td colname="col2">公式：访 <span class="filepath"> 客／总数（访客） </span><p>级别：访客 </p></td> 
   <td colname="col3"> 访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用百分比的访客 </td> 
   <td colname="col2"> <p>公式：Referred_Visitors/Visitors </p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用的会话 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> Sessions[Referrer&lt;&gt; 'None' and Referrer&lt;&gt;'bookmarks']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引荐访客 </td> 
   <td colname="col2"> <p>公式：访 <span class="filepath"> 客[Visitor_Referrer&lt;&gt;'None'和Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维系 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> Sessions[shift(None,Ses,Visitor,1)= ""] / Sessions</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 不是访客上次会话的会话百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> (sum(Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3">访客在会话中所花费的平均时长(MM:SS)。 <p><p>注意：您可以将此指标与“区段导出 <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> ”功能结合使用</a> 。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按页面查看的会话数 </td> 
   <td colname="col2"> <p>公式：按页 <span class="filepath"> 面查看的会话数</span></p> <p> 级别：会话 </p> </td> 
   <td colname="col3"> 具有页面查看的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话 </td> 
   <td colname="col2"> <p>公式：sum( <span class="filepath"> 一个，会话)</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 访客会话计数。 会话是网站一位访客的活动期。 每个访客的各个会话都使用cookie、超时和其他启发式方法进行标识。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>公式：信 <span class="filepath"> 心（会话）* 1.281551 /会话</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 数据工作台报告的会话量度的置信度度量。 从数学上讲，它是一个+/-百分比，它指定了实际答案将占时间80%的范围。 按照经验法则，将SCI80百分比翻倍，将给出一个区间，实际答案将占99%的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> (((原始（访客）+ .68)^0.5 * 1.281551 + 1.2269)+原始（访客）)*(访客／原始（访客）)</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> Insight报告的最大可能访客数的度量。 从数学上讲，它指定概率为90%的最高访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">公式： <span class="filepath"> (原始（访客）+ .68)^0.5 * 1.281551 + 1.2269)/原始（访客）</span><p>级别：访客 </p></td> 
   <td colname="col3"> Insight报告的“访客”量度的置信度度量。 从数学上讲，它是一个+/-百分比，它指定了实际答案将占时间80%的范围。 根据经验法则，将VCI80百分比加倍将给出一个范围，实际答案将占时间的99%。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按页面视图的访客数 </td> 
   <td colname="col2"> <p>公式：按页 <span class="filepath"> 面查看的访客数</span></p> <p>级别：页面视图 </p> </td> 
   <td colname="col3"> 具有页面查看的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按会话划分的访客 </td> 
   <td colname="col2"> <p>公式：按会 <span class="filepath"> 话划分的访客 </span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 有会话的访客数。 </td> 
  </tr> 
 </tbody> 
</table>

