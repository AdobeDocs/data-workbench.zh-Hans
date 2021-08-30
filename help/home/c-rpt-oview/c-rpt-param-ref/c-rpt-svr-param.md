---
description: 有关Report Server.cfg参数的信息。
title: Report Server.cfg 参数
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 8%

---

# Report Server.cfg 参数{#report-server-cfg-parameters}

有关Report Server.cfg参数的信息。

[配置与Insight Server的连接](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)中显示的示例[!DNL Report Server.cfg]默认仅包含[!DNL Report Server.cfg]文件中包含的参数。

如果您通过代理服务器与Adobe许可证服务器联系，则需要将授权矢量及其参数添加到[!DNL Report Server.cfg]中。 以下是此矢量及其参数的示例，您可以将模型用于授权矢量：

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

下表提供了[!DNL Report Server.cfg]文件参数的描述：

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel扩展 </td> 
   <td colname="col2"> <p>支持的Excel扩展包括： </p> <p>Excel Extension = string:<span class="filepath"> .xlsx </span> </p> <p>Excel Extension = string:<span class="filepath"> .xls </span>（默认设置） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts（字体） </td> 
   <td colname="col2"> <p>可选。列出<span class="keyword">报表服务器</span>应用于呈现基于UTF8的Unicode特殊字符的字体的矢量。 列表中字体的数量不受限制。 </p> <p>第一种字体应始终为 Lucida Sans Console。如果此参数未包含在<span class="filepath"> Report Server.cfg </span>文件中，则<span class="keyword"> Report Server </span>仅使用Lucida Sans控制台来显示文本。 </p> <p> <span class="keyword"> 报表服 </span> 务器使用列表中的第一种字体来渲染所有字符，直到遇到无法渲染的字符。然后，它使用列表中的第二种字体来渲染该字符。 如果该字体未呈现该字符，则<span class="keyword">报表服务器</span>会使用列表中的第三种字体来呈现该字符，依此类推，直到该字体列表到达结尾。 如果矢量中未列出正确的字体，则<span class="keyword"> Report Server </span>将显示该字符的十进制值。 </p> <p> <p>注意： 运行<span class="keyword">报表服务器</span>时，请勿更改此参数。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma（伽马） </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma设 </span> 置.png文 <span class="filepath"> 件 </span> 输出。默认值为 1.6。 </p> <p> <p>注意： Adobe不建议更改此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing（许可） </td> 
   <td colname="col2"> <p>可选。仅当您通过代理服务器联系Adobe的许可证服务器时，才需要修改此矢量中的参数。 </p> <p>节标识符，用于您设置为通过代理服务器与Adobe的许可证服务器联系的参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address（代理地址） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>必须用来访问Adobe许可证服务器的代理服务器的地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password（代理密码） </td> 
   <td colname="col2"> 可选。与<span class="wintitle">代理用户名</span>关联的密码。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port（代理端口） </td> 
   <td colname="col2"> 代理服务器的端口。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name（代理用户名） </td> 
   <td colname="col2"> 可选。用于访问代理服务器的用户名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Network Location（网络位置） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>用来将服务器的通用名称解析为IP地址的网络位置。 网络位置在位于Data Workbench Server计算机上的Addresses目录的地址文件中定义。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器 </td> 
   <td colname="col2"> <p>为配置哪些Data Workbench Server计算机<span class="keyword">报表服务器</span>必须连接才能生成报表而设置的参数的区域标识符。 这包括一个数字，用于指示此矢量中列出的项目数。 </p> <p>对于每个服务器，添加一个serverInfo条目，并根据需要完成参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>必须连接到的Data Workbench Server计算机的IP地址，才能生成报表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>在内部用于标识Data Workbench Server的名称。 这只是一个内部标签，因此您可以使用任何您喜欢的名称。 为保持一致性，我们建议您使用服务器数字证书上列出的通用名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>与Data Workbench Server通信的端口。 对于安全连接，此值通常为443。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address（代理地址） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>必须用来访问Data Workbench Server的代理服务器的地址。 仅当需要代理服务器连接到服务器计算机时才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password（代理密码） </td> 
   <td colname="col2"> 代理服务器的密码。仅当需要代理服务器才能连接到您的Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port（代理端口） </td> 
   <td colname="col2"> 代理服务器的端口。默认值为 8080。仅当需要代理服务器才能连接到您的Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name（代理用户名） </td> 
   <td colname="col2"> 代理服务器的用户名。 仅当需要代理服务器才能连接到您的Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>计算机的SSL证书文件的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
   <td colname="col2"> <span class="wintitle"> Data Workbench Server的 </span> 数字证书上列出的服务器通用名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL（使用 SSL） </td> 
   <td colname="col2"> 指示SSL是否用于Data Workbench Server与<span class="keyword">报表服务器</span>之间的安全通信。 选项为 true 或 false。默认值为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 结果内存限制(KB) </td> 
   <td colname="col2"> <p>要用于报告和警报的内存量（以KB为单位）。 默认值为 50000。 </p> <p>运行报表时，<span class="keyword">报表服务器</span>首先检查此值，然后检查“最大片段大小”参数中的值。 例如，如果将此参数设置为50,000，最大切片大小设置为50，则<span class="keyword">报表服务器</span>一次只运行50个工作区，即使有空间可运行更多工作区也是如此。 </p> <p> <p>注意： 此限制不得超过Data Workbench Server的“查询内存限制”参数中设置的值，理想情况下，应将该值设置为略低于<span class="wintitle">查询内存限制</span> ，以便为可能同时运行报表的其他用户提供一些余地。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大切片大小 </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>一次可运行的最大报表工作区数。 默认值为 50。有关<span class="keyword"> Report Server </span>如何使用此设置的详细信息，请参阅<span class="wintitle">结果内存限制(KB)</span>参数说明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software（更新软件） </td> 
   <td colname="col2"> <p>指示是否允许Data Workbench Server更新此<span class="keyword">报表服务器的</span>软件。 选项为 true 或 false。默认值为 true。 </p> <p>以下是可使用模型的此参数示例： </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用OpenGL硬件渲染 </td> 
   <td colname="col2"> <p>控制<span class="keyword"> Report Server </span>是否使用硬件渲染（如计算机的图形卡）来生成报告输出。 选项为 true 或 false。默认值为 true。 </p> <p>仅当您遇到图形卡问题时，此参数才应设置为false。 当设置为false时，<span class="keyword">报表服务器</span>不会尝试使用硬件渲染，默认情况下会使用软件渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 报表 </td> 
   <td colname="col2"> 设置为配置报表的参数的区域标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成消息间隔 </td> 
   <td colname="col2"> <p>当在报告或警报生成期间运行查询时，<span class="keyword">报表服务器</span>打印完成状态消息的频率（以秒为单位）。 默认值为 120 秒。 </p> <p>示例：工作区查询完成率为62.145672%。 </p> <p>完成消息将写入<span class="filepath"> reportserver.log </span>，并同步到服务器。 此设置控制每个报表集来回发送的<span class="filepath"> status.txt </span>文件，以便可以使用缩略图显示完成百分比。 当报表集完成或到达间隔（以先到者为准）时，会发送消息。 将此值设置为较高值不会影响缩略图在客户端界面中生成报表的速率，但会影响您看到的中间消息数。 指定低值可能会导致系统花费大量时间来同步数据，因为每次<span class="filepath"> status.txt </span>消息发生更改时，数据会从<span class="keyword"> Report Server </span>服务器同步到配置文件、跨所有DPU和所有连接的客户端。 </p> <p>无论此配置参数的设置如何，在报表集完成时，系统始终会发送<span class="filepath"> status.txt </span>文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>表示此矢量中列出的项目数。 对于要为其创建报表的每个配置文件，在“配置文件”矢量中添加<span class="wintitle"> ReportProfile </span>条目，并填写Server和Profile参数。 </p> <p> <span class="wintitle"> 服务 </span> 器 — 报表服 <span class="keyword"> 务器在 </span> 内部用于标识Data Workbench Server的名称。此名称必须是Data Workbench Server的SSL证书上列出的服务器通用名称。 </p> <p> <span class="wintitle"> 配 </span> 置文件 — 要为其创建报表的配置文件的名称。此名称必须与Data Workbench Server计算机上的已命名配置文件匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误的SMTP服务器 </td> 
   <td colname="col2"> <p>要通过电子邮件发送<span class="wintitle">报表服务器</span>错误的SMTP服务器的地址。 </p> <p>示例：<span class="filepath"> mail.mycompany.com </span> </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误密码的SMTP服务器 </td> 
   <td colname="col2"> <p>登录到SMTP服务器的密码。 此参数是可选的，除非发送邮件时需要登录。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 从发送错误的SMTP服务器 </td> 
   <td colname="col2"> 要从中发送<span class="wintitle">报表服务器</span>错误的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到的错误为SMTP服务器 </td> 
   <td colname="col2"> <p>接收警报的电子邮件地址。 </p> <p>示例：<span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误用户名的SMTP服务器 </td> 
   <td colname="col2"> <p>登录到SMTP服务器的用户名。 此参数是可选的，除非发送邮件时需要登录。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 状态间隔 </td> 
   <td colname="col2"> <p><span class="wintitle"> Report Server </span>生成状态信息并将其发送到Data Workbench Server的频率（以秒为单位），以在<span class="wintitle">详细状态</span>中显示。 </p> <p>默认值为 120 秒。不建议将此值设置为小值（如2分钟），因为报表队列可能需要数小时才能运行。 在这种情况下，您可以考虑将设置为600到1200秒。 </p> <p>有关<span class="wintitle">详细状态</span>的更多信息，请参阅《Insight用户指南》 </a>的“管理界面”一章。<a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> </a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新间隔 </td> 
   <td colname="col2"> <p><span class="keyword"> Report Server </span>使用的频率（以分钟为单位）监视“配置文件”矢量中列出的用于获取新报告和警报的所有配置文件。 默认值为10分钟。 </p> <p>指定的时间将被划分到列出的所有用户档案中。 例如，如果将间隔设置为10分钟，并且您监视两个用户档案，则每个用户档案都会被监视5分钟。 如果在将新的或已修改的报表或警报保存到用户档案时正在监控用户档案，则该报表或警报可立即生成。 </p> <p>如果将<span class="wintitle">更新间隔</span>配置为监视多个配置文件，则此设置必须足够高，以便在配置的时间内加载所有配置文件。 例如，在配置了许多大型维度的系统中，如果需要几分钟时间才能检索到具有所有元素名称的初始数据连接，则此设置必须足够长，才能进行完全同步。 否则，系统会发出配置文件同步错误。 </p> </td> 
  </tr> 
 </tbody> 
</table>
