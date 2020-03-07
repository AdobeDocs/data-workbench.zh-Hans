---
description: 浏览器请求页面的HTML后，浏览器会从Web服务器请求该页面的HTML中引用的嵌入对象以填充浏览器显示的页面。
solution: Analytics
title: 获取嵌入式对象请求（页面标记）
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 获取嵌入式对象请求（页面标记）{#acquiring-embedded-object-requests-page-tags}

浏览器请求页面的HTML后，浏览器会从Web服务器请求该页面的HTML中引用的嵌入对象以填充浏览器显示的页面。

这种嵌入式对象请求是对图像文件或JavaScript文件的最常见请求，尽管目前因特网上使用的嵌入式对象有成百上千种或数千种。 其中许多嵌入式对象请求通常在分析或报告因特网网站的业务活动时并不有用；因此，许多此类请求对于收购而言并不可取，除非它们具有特定的业务目的，例如展示广告或对网站活动进行其他衡量。

例如，图像可能是广告，您可能希望了解该广告对访客的印象。 JavaScript代码片断可用于测量特定浏览器具有特定特征，并将其传回以进行 [!DNL Sensor] 获取。 站点上的每个页面可能包含10或100个嵌入对象请求。 如果站点存储了这些请求中每个请求的日志信息，则使日志数据可供将来分析所需的数据存储量乘以请求的每个页面的嵌入式对象请求数。 因此，您可 [!DNL Site] 以保留对分析很重要的请求并丢弃其他请求，以免产生不必要的存储成本。

通过使用在嵌入式对象请求URL的查询字符串附加“Log=1”的内容类型过滤功能中提供的覆盖功能，可以获得特定嵌入式对象请求和相关测量数据，而不需要站点管理器存储该类型的所有请求(例如，所有 [!DNL Sensor] <image> 请求）的数量。

[!DNL Sensor] 在下表中为由Web服务器发出的每个嵌入对象请求收集测量数据，假设未配置为过滤它或过滤器已被覆盖 [!DNL Sensor] 。 通过x-trackingid或cs(cookie)日志字段条目收集的信息与访客和会话以及后续会话相关。

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
   <td colname="col2"> 跟踪标识符（唯一访客） </td> 
   <td colname="col3"> 传感器在初始请求时从用户浏览器中放置的cookie读取 <span class="wintitle"> 的标 </span> 识符 </td> 
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
   <td colname="col3"> 客户端发送的HTTP引用字段的内容 </td> 
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
   <td colname="col3"> 站点的所有用户Cookie的内容 </td> 
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

