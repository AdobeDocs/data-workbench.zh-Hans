---
description: 浏览器请求页面的HTML后，浏览器会从Web服务器请求该页面HTML中引用的嵌入对象来填充浏览器显示的页面。
solution: Analytics
title: 获取嵌入式对象请求（页面标记）
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 6%

---


# 获取嵌入式对象请求（页面标记）{#acquiring-embedded-object-requests-page-tags}

浏览器请求页面的HTML后，浏览器会从Web服务器请求该页面HTML中引用的嵌入对象来填充浏览器显示的页面。

此类嵌入式对象请求是最常见的图像文件或JavaScript文件请求，尽管目前因特网上使用的嵌入式对象有成百上千种。 这些嵌入式对象请求中的许多通常不适用于分析或报告因特网网站的业务活动;因此，许多此类请求在收购时是不可取的，除非它们具有特定的业务目的，如展示广告或采用其他网站活动计量。

例如，图像可能是广告，您可能希望知道广告对访客印象深刻。 JavaScript片段可用于测量特定浏览器具有特定特征并将其传回以进行 [!DNL Sensor] 获取。 站点上的每个页面可能包含10或100个嵌入对象请求。 如果站点存储了每个请求的日志信息，则使日志数据在未来分析可用所需的存储量乘以每个请求页面的嵌入式对象请求数。 因此，您可 [!DNL Site] 以保留对分析重要的请求，并在产生不必要的存储成本之前丢弃其他请求。

通过使用在内容类型过滤功能中提供的覆盖功能(将“Log= [!DNL Sensor] 1”附加到嵌入式对象请求URL的查询字符串)，可以获得该特定嵌入式对象请求和相关测量数据，而不需要站点管理器存储该类型的所有请求(例如，所有请 `<image>` 求)。

[!DNL Sensor] 为web服务器发出的每个嵌入对象请求收集下表中的测量数据，假定 [!DNL Sensor] 未配置为筛选它或筛选器已被覆盖。 通过x-trackingid或cs(cookie)日志字段条目收集的信息与访客、会话和后续会话相关。

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C名称 </th> 
   <th colname="col2" class="entry"> 收集的数据 </th> 
   <th colname="col3" class="entry"> 说明 </th> 
   <th colname="col4" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> 跟踪标识符(唯一访客) </td> 
   <td colname="col3"> 初始请求时传感器从用户浏览器中放置的cookie读取 <span class="wintitle"> 的 </span> 标识符 </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 </p> <p>时间 </p> </td> 
   <td colname="col2"> 时间戳 </td> 
   <td colname="col3"> 服务器处理请求的时间(精度为100ns;准确性取决于服务器环境和NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> 内容类型 </td> 
   <td colname="col3"> 从服务器返回的对象类型 </td> 
   <td colname="col4"> text/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP响应状态代码 </td> 
   <td colname="col3"> 由服务器生成并记录HTTP服务器响应状态的数字代码 </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> 客户端请求的URI的“stem”部分 </td> 
   <td colname="col4"> pagedir/page.asp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> 客户端IP </td> 
   <td colname="col3"> 请求客户端的IP地址 </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> 服务器域名 </td> 
   <td colname="col3"> 处理请求的Web服务器的域名 </td> 
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 反向链接 URL </td> 
   <td colname="col3"> 客户端发送的HTTP推荐人字段的内容 </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> 用户代理 </td> 
   <td colname="col3"> 用于向HTTP服务器发出请求的设备 </td> 
   <td colname="col4"> <p>Mozilla/4.0+(兼容；+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> 来自域的客户端Cookie </td> 
   <td colname="col3"> 网站所有用户Cookie的内容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> 查询字符串 </td> 
   <td colname="col3"> 客户端请求的URI的查询字符串部分（如果有） </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

