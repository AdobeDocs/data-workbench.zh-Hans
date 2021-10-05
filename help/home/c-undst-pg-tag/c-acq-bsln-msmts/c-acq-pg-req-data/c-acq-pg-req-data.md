---
description: 传感器获取在对安装该数据的Web服务器发出的页面请求(GET请求)中携带的所有测量数据。
title: 获取页面请求数据
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 6%

---

# 获取页面请求数据{#acquiring-page-request-data}

传感器获取在对安装该数据的Web服务器发出的页面请求(GET请求)中携带的所有测量数据。

[!DNL Sensor] 直接从web服务器上运行的web服务器软件的实例或实例中，通过web服务器的应用程序编程接口获取此测量数据。[!DNL Sensor] 不访问web服务器生成的日志文件。事实上，在安装并测试[!DNL Sensor]和Data Workbench Server之后，可以禁用Web服务器的本机日志记录功能，而不会影响数据收集。 在很多情况下，禁用对Web服务器计算机本地磁盘的文件记录，会由于将此信息记录到Web服务器计算机本地磁盘所需的固定磁盘I/O量相对较大，从而提高这些Web服务器的页面服务容量。

[!DNL Sensor] 直接从每个web服务器进程和虚拟web服务器进程（如果适用）收集测量和web请求数据，并将数据临时写入web服务器计算机上具有固定磁盘备份的容错内存队列“队列文件”。传感器发送器服务（或根据平台而定的守护程序）从队列文件中检索数据，然后对其进行压缩和加密，然后再将其传输到Data Workbench Server以进行长期存储。 使用[!DNL Sensor]时，只有当您的网络或其他问题阻止其传输时，数据才会在队列文件中的Web服务器计算机上累积。 队列文件允许将数小时到数天的Web请求数据高效地本地存储，以在网络或系统故障不允许将数据实时传输到Data Workbench Server时保护数据。

[!DNL Sensor] 从每个物理和逻辑Web服务器进程中收集测量数据，按内容类型对其进行过滤、压缩、加密，并将其流式传输到Data Workbench Server。

下表包含[!DNL Sensor]为未基于[!DNL Sensor’s]配置文件过滤出的每个GET请求获取的日志信息字段：

<table id="table_5F65474150EC41648B35D0B031FB9B15">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C名称 </th>
   <th colname="col2" class="entry"> 收集的数据 </th>
   <th colname="col3" class="entry"> 说明 </th>
   <th colname="col4" class="entry"> 说明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> 跟踪标识符（独特访客） </td>
   <td colname="col3"> 在访客的初始请求中，传感器<span class="wintitle"> </span>从用户浏览器中放置的Cookie中读取的标识符 </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>日期 </p> <p>时间 </p> </td>
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
   <td colname="col3"> 由服务器生成的数字代码，用于记录HTTP服务器响应的状态 </td>
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI主体 </td>
   <td colname="col3"> 客户端请求的URI的主干部分 </td>
   <td colname="col4"> <span class="filepath"> pagedir/page.asp  </span> </td>
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
   <td colname="col4"> <span class="filepath"> www.domain.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 反向链接 URL </td>
   <td colname="col3"> 客户端发送的HTTP反向链接字段的内容 </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com  </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> 用户代理 </td>
   <td colname="col3"> 用于向HTTP服务器发出请求的设备 </td>
   <td colname="col4"> Mozilla/4.0+(兼容；+MSIE+6.0;+Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> 来自域的客户端Cookie </td>
   <td colname="col3"> 网站所有用户Cookie的内容 </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> 查询字符串 </td>
   <td colname="col3"> 客户请求的URI的查询字符串部分（如果有） </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
