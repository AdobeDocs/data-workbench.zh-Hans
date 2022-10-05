---
description: 有关传感器记录的基线事件数据记录字段的信息。
title: 基线事件数据记录字段
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 65%

---

# 基线事件数据记录字段{#baseline-event-data-record-fields}

{{eol}}

有关传感器记录的基线事件数据记录字段的信息。

<table id="table_E29606BB010E4DB48C463979B7BEC769">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 字段 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>向服务器发送的请求中所包含的客户端 IP 地址。 </p> <p>示例：207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>由客户端随请求一起发送的 cookie。 </p> <p>示例：v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM； </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>由客户端随请求一起向服务器发送的 HTTP 反向链接字符串。 </p> <p>示例：https://www.mysite.net/cgi-bin/websearch?qry </p> <p>如果您使用页面标记，则cs(referrer)是包含标记图像的文档的完整URL，包括HTTP或HTTP。 </p> <p>此外，您还可以配置Apache（1.3、2.0和2.2）和IIS传感器以捕获用于请求的端口，该端口可识别HTTP请求和HTTPS请求。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>由客户端随请求一起向服务器发送的字符串，用于指示客户端是何种类型的用户代理。 </p> <p>示例：Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>HTTP请求的方法类型 </p> <p>示例：GET </p> <p>引用：https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>URI的查询字符串部分（主体+查询字符串= URI） </p> <p>这部分的前面有一个问号 (?)，并且可能包含一个或多个由与号 (&amp;) 分隔的名称-值对。 </p> <p>示例：page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>URI的主干部分（主干+查询字符串= URI） </p> <p>主干是请求资源在服务器上的实际或逻辑路径。 </p> <p>示例：/index.asp </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>由服务器报告的客户端请求资源的内容类型。 </p> <p>示例：text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>为响应请求而从服务器向客户端发送的数据字节数。 </p> <p>示例：4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>由服务器返回到客户端的状态代码。 </p> <p>示例：200 </p> <p>引用：https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>请求资源主机的完全限定域名或 IP 地址。 </p> <p>示例：www.omniture.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-experiment </td>
   <td colname="col2"> <p>请求时客户端属于其中成员的所有受控试验名称和组的列表。 </p> <p>示例：Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>服务器接收到请求的日期和时间 (GMT)。 </p> <p>该时间以从 1600 年 1 月 1 日算起的总时间数表示（以 100 纳秒为单位）。 </p> <p>示例：127710989320000000是11的x-timestamp值:28:52.0000000 2005年9月13日星期二。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>在由<span class="wintitle">传感器</span>设置并由客户端随请求一起向服务器提供的永久性 cookie 中包含的唯一浏览器标识符的 64 位十六进制值。 </p> <p>示例：42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

的 [!DNL data workbench server] 可以从基线事件数据记录字段派生多个变量。 有关更多信息，请参阅 *数据集配置指南*.
