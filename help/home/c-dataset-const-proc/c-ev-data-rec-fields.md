---
description: 有关 Data Workbench Server 在构建数据集时可处理的数据字段的信息。
solution: Analytics
title: 事件数据记录字段
topic: Data workbench
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 事件数据记录字段{#event-data-record-fields}

有关 Data Workbench Server 在构建数据集时可处理的数据字段的信息。

* [关于事件数据](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [基准事件数据记录字段](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [派生字段](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## 关于事件数据 {#section-3a0705f8c1824017aa4effed9903efbe}

用于构建数据集的事件数据位于称为日志源的文件中。日志源中提供的数据称为事件数据，因为每条数据记录都表示一条交易记录，或一个具有相关时间戳的事件的单个实例。

A log source&#39;s event data is collected in real-time by [!DNL Sensors]. Event data collected by [!DNL Sensors] from HTTP and application servers is transmitted to data workbench servers, which convert the data into compressed log ( [!DNL .vsl]) files. Data Workbench Server 可读取位于无格式文件、XML 文件或 ODBC 数据源中的事件数据，并提供您定义的解码器来从这些不同的格式中提取通用的数据字段集。

The following sections provide information about the data fields (referred to as event data record fields or log entry fields ) that are collected by [!DNL Sensors] or read and made available to the data workbench server.

>[!NOTE]
>
>字段名称通常遵循W3C扩展日志文件格式的命名约定。 许多字段带有前缀，用于指示字段中所含信息的源：

* cs 指示从客户端到服务器的通信。
* sc 指示从服务器到客户端的通信。
* s 指示来自服务器的信息。
* c 指示来自客户端的信息。
* x 指示由 Adobe 软件产品创建的信息。

## 基准事件数据记录字段 {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Log ( [!DNL .vsl]) files contain the fields of event data that are collected from servers by [!DNL Sensors] and used by the data workbench server in the dataset construction process. The following table lists the fields in a typical event data record as recorded by [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>向服务器发送的请求中所包含的客户端 IP 地址。 </p> <p> 示例：207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>由客户端随请求一起发送的 cookie。 </p> <p> 示例：v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM； </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>由客户端随请求一起向服务器发送的 HTTP 反向链接字符串。 </p> <p> 示例：<span class="filepath">http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>由客户端随请求一起向服务器发送的字符串，用于指示客户端是何种类型的用户代理。 </p> <p> 示例：Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>HTTP 请求的方法类型。 </p> <p> 示例：GET </p> <p> 参考：<span class="filepath">http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>URI（主干 + 查询字符串 = URI）的查询字符串部分。这部分的前面有一个问号 (?)，并且可能包含一个或多个由与号 (&amp;) 分隔的名称-值对。 </p> <p> 示例：page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>URI（主干 + 查询字符串 = URI）的主干部分。主干是请求资源在服务器上的实际或逻辑路径。 </p> <p> 示例：<span class="filepath">/index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>由服务器报告的客户端请求资源的内容类型。 </p> <p> 示例：text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>为响应请求而从服务器向客户端发送的数据字节数 </p> <p> 示例：4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>由服务器返回到客户端的状态代码。 </p> <p> 示例：200 </p> <p> 参考：<span class="filepath">http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>请求资源主机的完全限定域名或 IP 地址。 </p> <p> 示例：<span class="filepath">www.adobe.com/cn/</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>请求时客户端属于其中成员的所有受控试验名称和组的列表。 </p> <p> 示例：VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>服务器接收到请求的日期和时间 (GMT)。该时间以从 1600 年 1 月 1 日算起的总时间数表示（以 100 纳秒为单位）。 </p> <p> 示例：127710989320000000 是 2005 年 9 月 13 日星期二 11:28:52.0000000 的 x-timestamp 值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>在由<span class="wintitle">传感器</span>设置并由客户端随请求一起向服务器提供的永久性 cookie 中包含的唯一浏览器标识符的 64 位十六进制值。 </p> <p> 示例：42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 派生字段 {#section-b6c57ee2aa31469fbd5dab90e52bc677}

下表列出了由 Data Workbench Server 从基准事件数据记录字段派生的字段示例：

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> cookie 内给定名称-值对的值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>HTTP 反向链接 URI 的域名或 IP 地址。 </p> <p> <p>注意：此字段为只读。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>反向链接的完整主机名。 </p> <p> 示例：如果 cs(referrer) 是 <span class="filepath">http://my.domain.com/my/page</span>，则 cs(referrer-host) 是 <span class="filepath">my.domain.com</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>反向链接查询字符串的值。 </p> <p> <p>注意：您无法使用 cs(referrer)(name) 字段访问反向链接查询字符串值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>完整的 URI（主干 + 查询字符串 = 完整 URI）。 </p> <p> 示例：<span class="filepath">/shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>与给定名称关联的值。如果给定名称存在多个值，则此字段返回其中最后一个值。 </p> 示例： 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> 对于 URI <span class="filepath">/shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd</span>，cs-uri-query(product3) 将返回 cd。 </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> 对于 URI <span class="filepath">/shopping/checkout.html?product1=8Track&amp;product1=casette</span>，<span class="wintitle">cs-uri-query(product1)</span> 将返回 casette。 </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp 以从 1970 年 1 月 1 日算起的总秒数表示。此字段也称为 x-unixtime。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> YYYY-MM-DD 格式的 x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> HH:MM:SS 格式的 x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>已转换为 <span class="filepath">Transformation.cfg</span> 文件中为数据集指定的本地时区的 x-timestamp。格式为 YYYY-MM-DD HH:MM:SS.mmm。 </p> <p> <p>注意：您还可以在 <span class="filepath">Log Processing.cfg</span> 文件中定义时间转换，如 x-local-timestring。有关信息，请参阅 <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 日志处理配置文件 </a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>与特定日志条目的日志源对应的标识符。对于要记录的标识符，您必须在定义<span class="wintitle">传感器</span>、日志文件或 ODBC 数据源时，在<span class="filepath"> Log Processing.cfg</span> 文件的<span class="wintitle">日志源 ID</span> 字段中指定它。有关详细信息，请参阅 <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 日志处理配置文件 </a>。 </p> <p> 示例：来自 VSensor01。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> <span class="wintitle">传感器</span>数据源的掩码模式（从 <span class="filepath">.vsl</span> 文件名派生）。对于名称格式为 <span class="filepath">YYYYMMDD–SENSORID.VSL</span> 的文件，x-mask 为 SENSORID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> YYYY-MM-DD HH:MM:SS.mmm 格式的 x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> 从 x-timestamp 派生的十进制 UNIX 时间。 </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor]在服务器上使用时，可以从任何有效的HTTP请求或响应头中收集事件数据的字段，或者通过服务器的API收集可用的变量。 To collect such fields of data, you must specify the desired header fields or variables in the [!DNL txlogd.conf]configuration file for [!DNL Sensor]. For more information, see the *Data Workbench[!DNL Sensor]Guide*.