---
description: 流量配置文件包含以下用于识别访客流量的量度。
title: 流量配置文件量度
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# 流量配置文件量度{#traffic-profile-metrics}

流量配置文件包含以下用于识别访客流量的量度。

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 量度公式和级别 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 登入次数 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None，Page_View， Session，-1)]</span><p>级别：页面查看 </p></td> 
   <td colname="col3"> 在每个页面上输入网站的会话数。 此量度仅通过“页面”维度计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出率 </td> 
   <td colname="col2">公式：<span class="filepath">退出/页面查看次数</span><p>级别：页面查看 </p></td> 
   <td colname="col3"> 从每个页面退出网站的会话的百分比。 “退出率”量度只能通过页面维度来评估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None，Page_View， Session，1)] </span><p>级别：页面查看 </p></td> 
   <td colname="col3"> 从每个页面退出网站的会话数。 此量度仅通过“页面”维度计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">公式：<span class="filepath">(原始（访客） — ((原始（访客）+ .69)^0.5 * 1.281551 - 1.2269))*(访客/原始（访客）)</span><p>级别：访客 </p></td> 
   <td colname="col3"> 由Insight报告的最低可能访客数的度量。 通过数学方法，它可以指定概率为90%的最低访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看持续时间 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">总和(exact_page_duration， page_view)*0.1/Page_Views[任何Exact_Page_Duration]</span></p> <p>级别：页面查看 </p> </td> 
   <td colname="col3"> 在特定页面或一组页面上花费的平均时间(MM:SS)。 此量度仅通过“页面”维度计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每个会话的页面查看次数 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Page_Views/（按Page_View划分的会话）</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 每个会话中具有页面查看次数的平均页面查看次数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看次数 </td> 
   <td colname="col2">公式：<span class="filepath"> sum(One， Page_View)</span><p>级别：页面查看 </p></td> 
   <td colname="col3"> 页面查看次数。 页面查看是对定义的页面的请求（不计算对图像和其他类型的过滤内容的访问）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看次数百分比 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views/total(Page_Views)</span><p>级别：页面查看 </p></td> 
   <td colname="col3"> 页面查看次数的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话数百分比 </td> 
   <td colname="col2">公式：<span class="filepath">会话/总数（会话）</span><p>级别：会话 </p></td> 
   <td colname="col3"> 会话的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客百分比 </td> 
   <td colname="col2">公式：<span class="filepath">访客/总数（访客）</span><p>级别：访客 </p></td> 
   <td colname="col3"> 访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用的访客百分比 </td> 
   <td colname="col2"> <p>公式：引荐的访客/访客 </p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他网站引荐到此网站的访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引荐的会话 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Sessions[Referrer&lt;&gt; 'None'和Referrer&lt;&gt;'bookmarks']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 从其他网站引荐到此网站的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引荐访客 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Visitors[Visitor_ Referrer&lt;&gt;'None'和Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他网站引荐到此网站的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维系 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Sessions[shift(None，Session，Visitor，1)= ""] / Sessions</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 不是访客上次会话的会话百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(sum(Exact_Page_Duration， Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3">访客在会话中所花费的平均时间(MM:SS)。 <p><p>注意：此量度可与<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external">区段导出</a>功能一起使用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按页面查看的会话数 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按Page_View划分的会话</span></p> <p> 级别：会话 </p> </td> 
   <td colname="col3"> 具有页面查看的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> sum(One， Session)</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 访客会话的计数。 会话是网站一位访客的活动时段。 使用Cookie、超时和其他启发式方法来识别每个访客的各个会话。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> confidence(sessions)* 1.281551 / Sessions</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> Data Workbench报告的“会话”量度的置信度度量。 从数学上讲，它是一个+/ — 百分比，用于指定实际答案将在80%的时间内的范围。 按经验法则，将SCI 80百分比加倍，将给出一个区间，实际答案将是99%的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(((原始（访客）+ .68)^0.5 * 1.281551 + 1.2269)+原始（访客）)*(访客/原始（访客）)</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 由Insight报告的可能最大访客数的度量。 通过数学方法，它可以指定概率为90%的最高访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">公式：<span class="filepath">((原始（访客）+ .68)^0.5 * 1.281551 + 1.2269)/原始（访客）</span><p>级别：访客 </p></td> 
   <td colname="col3"> 由Insight报告的“访客”量度的置信度度量。 从数学上讲，它是一个+/ — 百分比，用于指定实际答案将在80%的时间内的范围。 按经验法则，将VCI80百分比加倍，将会给出一个范围，实际答案将是99%的时间。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按页面查看划分的访客数 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按Page_View划分的访客</span></p> <p>级别：页面查看 </p> </td> 
   <td colname="col3"> 具有页面查看的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按会话划分的访客数 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按会话划分的访客数</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 有会话的访客数。 </td> 
  </tr> 
 </tbody> 
</table>
