---
description: 流量用户档案包含以下量度以标识访客流量。
title: 流量配置文件量度
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# 流量配置文件量度{#traffic-profile-metrics}

流量用户档案包含以下量度以标识访客流量。

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 指标 </th> 
   <th colname="col2" class="entry"> 量度公式和级别 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 登入次数 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_视图[no shift(None，Page_视图, Session，-1)]</span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 在每个页面上输入站点的会话数。 此量度仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出率 </td> 
   <td colname="col2">公式：<span class="filepath"> Exits/Page_视图 </span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 从每个页面退出网站的会话百分比。 退出率量度只能在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_视图[no shift(None，Page_视图, Session，1)] </span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 从每个页面退出网站的会话数。 此量度仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">公式：<span class="filepath">(原始(访客)-((原始(访客)+ .69)^0.5 * 1.281551 - 1.2269))*(访客/原始(访客))</span><p>级别：访客 </p></td> 
   <td colname="col3"> 由Insight报告的最低可能访客数的度量。 从数学上讲，它指定概率为90%的最低访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面视图持续时间 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> sum(exact_page_duration， page_视图)*0.1/Page_视图[任何Exact_Page_Duration]</span></p> <p>级别：页面视图 </p> </td> 
   <td colname="col3"> 在特定页面或一组页面上花费的平均时间长度(MM:SS)。 此量度仅在页面维度上计算。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每个会话的页面视图 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Page_视图s/(Sessions by Page_视图)</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 每个会话中具有页面视图的平均页面视图数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面查看次数 </td> 
   <td colname="col2">公式：<span class="filepath"> sum(One， Page_视图)</span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 页面视图数。 页面视图是对定义页面的请求（不计算对图像和其他类型的筛选内容的访问权限）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 页面视图百分比 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_视图/total(Page_视图)</span><p>级别：页面视图 </p></td> 
   <td colname="col3"> 页面视图百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话数百分比 </td> 
   <td colname="col2">公式：<span class="filepath">会话/总计（会话）</span><p>级别：会话 </p></td> 
   <td colname="col3"> 会话的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客百分比 </td> 
   <td colname="col2">公式：<span class="filepath">访客/total(访客)</span><p>级别：访客 </p></td> 
   <td colname="col3"> 访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用百分比访客 </td> 
   <td colname="col2"> <p>公式：引用的访客/访客 </p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的访客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用的会话 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">会话[推荐人&lt;&gt; '无'和推荐人&lt;&gt;'bookmarks']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 引用访客 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">访客[访客_推荐人&lt;&gt;'无'和访客_推荐人&lt;&gt;'book marks']</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 从其他站点引用到此站点的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 维系 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">会话[shift(None，Ses，访客,1)= ""] /会话</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 不是上次会话的访客的会话百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 会话持续时间 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(sum(Exact_Page_Duration， Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3">访客在会话中所花费的平均时长(MM:SS)。 <p><p>注意：您可以将此量度与<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external">区段导出</a>功能一起使用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按页面列出的会话视图 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按Page_视图</span></p> <p> 级别：会话 </p> </td> 
   <td colname="col3"> 具有页面视图的会话数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> sum(One， Session)</span></p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 访客会话计数。 会话是网站一访客的活动期。 每个访客的各个会话使用cookie、超时和其他启发式方法进行标识。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">置信度（会话）* 1.281551 / Sessions</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 由Data Workbench报告的会话量度的置信度度量。 从数学上讲，它是一个+/ — 百分比，它指定实际答案将占时间80%的范围。 根据经验法则，将SCI80百分比翻一番，将给出一个范围，实际答案将占时间的99%。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(((raw(访客)+ .68)^0.5 * 1.281551 + 1.2269)+ raw(访客))*(访客/raw(访客))</span></p> <p>级别：访客 </p> </td> 
   <td colname="col3"> 由Insight报告的最大可能访客数的度量。 从数学上讲，它指定概率为90%的最大访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">公式：<span class="filepath">((原始(访客)+ .68)^0.5 * 1.281551 + 1.2269)/原始(访客)</span><p>级别：访客 </p></td> 
   <td colname="col3"> 由Insight报告的访客量度的置信度度量。 从数学上讲，它是一个+/ — 百分比，它指定实际答案将占时间80%的范围。 根据经验法则，将VCI80百分比加倍将给出一个范围，实际答案将占时间的99%。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客（按页面）视图 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按页面视图的访客</span></p> <p>级别：页面视图 </p> </td> 
   <td colname="col3"> 具有页面视图的访客数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访客（按会话） </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按会话</span>访客</p> <p>级别：会话 </p> </td> 
   <td colname="col3"> 具有会话的访客数。 </td> 
  </tr> 
 </tbody> 
</table>
