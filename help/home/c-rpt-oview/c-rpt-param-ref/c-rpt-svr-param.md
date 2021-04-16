---
description: 有关Report Server.cfg参数的信息。
title: Report Server.cfg 参数
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 8%

---

# Report Server.cfg 参数{#report-server-cfg-parameters}

有关Report Server.cfg参数的信息。

[配置与Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)的连接中显示的示例[!DNL Report Server.cfg]默认仅包含[!DNL Report Server.cfg]文件中包含的参数。

如果通过代理服务器与Adobe许可证服务器联系，则需要将许可矢量及其参数添加到[!DNL Report Server.cfg]。 以下是此矢量及其参数的一个示例，您可以将模型用于您的授权矢量：

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

下表提供了[!DNL Report Server.cfg]文件参数的说明：

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
   <td colname="col2"> <p>支持的Excel扩展包括： </p> <p>Excel Extension =字符串：<span class="filepath"> .xlsx </span> </p> <p>Excel Extension =字符串：<span class="filepath"> .xls </span>（这是默认设置） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts（字体） </td> 
   <td colname="col2"> <p>可选。列出<span class="keyword">报表服务器</span>应用于呈现基于UTF8的Unicode特殊字符的字体的矢量。 列表中字体的数量不受限制。 </p> <p>第一种字体应始终为 Lucida Sans Console。如果<span class="filepath"> Report Server.cfg </span>文件中未包含此参数，则<span class="keyword"> Report Server </span>仅使用Lucida Sans控制台显示文本。 </p> <p> <span class="keyword"> 报表服 </span> 务器使用列表中的第一种字体来呈现所有字符，直到遇到无法呈现的字符。然后，它使用列表中的第二种字体来渲染该字符。 如果该字体未呈现该字符，<span class="keyword">报表服务器</span>将使用列表中的第三种字体来呈现该字符，依此类推，直到该字体达到字体列表的末尾。 如果矢量中未列出正确的字体，<span class="keyword">报表服务器</span>将显示该字符的十六进制值。 </p> <p> <p>注意： 在<span class="keyword">报表服务器</span>运行时，请勿更改此参数。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma（伽马） </td> 
   <td colname="col2"> <p> <span class="wintitle"> . </span> png文件输 <span class="filepath"> 出的 </span> 灰度系数设置。默认值为 1.6。 </p> <p> <p>注意： Adobe不建议更改此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing（许可） </td> 
   <td colname="col2"> <p>可选。仅当您通过代理服务器与Adobe的许可证服务器联系时，才需要修改此矢量中的参数。 </p> <p>设置为通过代理服务器与Adobe的许可证服务器联系的参数的节标识符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address（代理地址） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>必须用来访问Adobe的许可证服务器的代理服务器地址。 </td> 
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
   <td colname="col2"> <span class="keyword">报表服务器</span>用来将服务器的公用名称解析为IP地址的网络位置。 网络位置在位于Data Workbench Server计算机上Addresses目录的地址文件中定义。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器 </td> 
   <td colname="col2"> <p>设置为配置哪些Data Workbench Server计算机<span class="keyword">报表服务器</span>必须连接才能生成报表的参数的节标识符。 这包括一个数字，指示此矢量中列出的项目数。 </p> <p>对于每台服务器，添加一个serverInfo条目并根据需要完成参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>必须连接到的Data Workbench Server计算机的IP地址，以生成报表。 </td> 
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
   <td colname="col2"> 代理服务器的密码。仅当需要代理服务器连接到Data Workbench Server计算机时才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port（代理端口） </td> 
   <td colname="col2"> 代理服务器的端口。默认值为 8080。仅当需要代理服务器连接到Data Workbench Server计算机时才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name（代理用户名） </td> 
   <td colname="col2"> 代理服务器的用户名。 仅当需要代理服务器连接到Data Workbench Server计算机时才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>计算机的SSL证书文件的名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
   <td colname="col2"> <span class="wintitle"> 服务器公 </span> 用名称，列在Data Workbench Server的数字证书上。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL（使用 SSL） </td> 
   <td colname="col2"> 指示是否使用SSL在Data Workbench Server和<span class="keyword">报表服务器</span>之间进行安全通信。 选项为 true 或 false。默认值为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 结果内存限制(KB) </td> 
   <td colname="col2"> <p>要用于报告和警报的内存量（以KB为单位）。 默认值为 50000。 </p> <p>运行报告时，<span class="keyword">报表服务器</span>首先检查此值，然后检查“最大切片大小”参数中的值。 例如，如果将此参数设置为50,000，将“最大切片大小”设置为50，则<span class="keyword">报表服务器</span>一次只运行50个工作区，即使有空间运行更多工作区也是如此。 </p> <p> <p>注意： 此限制不应超过Data Workbench Server的“查询内存限制”参数中设置的值，理想情况下，应将此限制设置为略低于<span class="wintitle">查询内存限制</span>，以便为可能同时运行报表的其他用户提供一些余地。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大切片大小 </td> 
   <td colname="col2"> <span class="keyword">报表服务器</span>可同时运行的最大报表工作区数。 默认值为 50。有关<span class="keyword">报表服务器</span>如何使用此设置的详细信息，请参阅<span class="wintitle">结果内存限制(KB)</span>参数说明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software（更新软件） </td> 
   <td colname="col2"> <p>指示是否允许Data Workbench Server更新此<span class="keyword">报表服务器的</span>软件。 选项为 true 或 false。默认值为 true。 </p> <p>以下是可以使用模型的此参数示例： </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用OpenGL硬件渲染 </td> 
   <td colname="col2"> <p>控制<span class="keyword">报表服务器</span>是否使用硬件渲染（如计算机的图形卡）生成报表输出。 选项为 true 或 false。默认值为 true。 </p> <p>仅当您遇到图形卡问题时，才应将此参数设置为false。 如果设置为false，则<span class="keyword">报表服务器</span>将不尝试使用硬件渲染，并默认使用软件渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 报表 </td> 
   <td colname="col2"> 设置为配置报告的参数的节标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成消息间隔 </td> 
   <td colname="col2"> <p>在报告或警报生成期间运行查询时，<span class="keyword">报表服务器</span>打印完成状态消息的频率（以秒为单位）。 默认值为 120 秒。 </p> <p>示例：工作区查询已完成62.145672%。 </p> <p>完成消息将写入<span class="filepath"> reportserver.log </span>并同步到服务器。 此设置控制每个报告集来回发送的<span class="filepath"> status.txt </span>文件，以便用缩略图显示完成百分比。 每当报表集完成或到达间隔时（以先到者为准）发送消息。 设置此较高值不会影响缩略图在客户端界面中生成的报表的查看速率，但会影响您看到的中间消息数。 指定低值可能会导致系统花费大量时间同步数据，因为每次<span class="filepath"> status.txt </span>消息发生更改时，数据会从<span class="keyword">报表服务器</span>服务器同步到用户档案，跨所有DPU和所有连接的客户端。 </p> <p>无论此配置参数的设置如何，系统始终在报告集完成时发送<span class="filepath"> status.txt </span>文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>指示此矢量中列出的项目数。 对于要为其创建报表的每个用户档案，在“用户档案”矢量中添加<span class="wintitle"> ReportProfile </span>条目，并填写服务器和用户档案参数。 </p> <p> <span class="wintitle"> 服务 </span> 器 — 报表服务 <span class="keyword"> 器内部 </span> 用于标识Data Workbench Server的名称。此名称必须是Data Workbench Server的SSL证书上列出的服务器通用名称。 </p> <p> <span class="wintitle"> 用户档案 </span>  — 要为其创建报表的用户档案的名称。此名称必须与Data Workbench Server计算机上的已命名用户档案匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误的SMTP服务器 </td> 
   <td colname="col2"> <p>要通过电子邮件发送<span class="wintitle">报告服务器</span>错误的SMTP服务器的地址。 </p> <p>示例：<span class="filepath"> mail.mycompany.com </span> </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器错误密码 </td> 
   <td colname="col2"> <p>用于登录到SMTP服务器的口令。 除非需要登录才能发送邮件，否则此参数是可选的。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送错误的SMTP服务器 </td> 
   <td colname="col2"> 要从中发送<span class="wintitle">报表服务器</span>错误的电子邮件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到的错误为SMTP服务器 </td> 
   <td colname="col2"> <p>接收警报的电子邮件地址。 </p> <p>示例：<span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 错误用户名的SMTP服务器 </td> 
   <td colname="col2"> <p>用于登录到SMTP服务器的用户名。 除非需要登录才能发送邮件，否则此参数是可选的。 </p> <p>使用所述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 状态间隔 </td> 
   <td colname="col2"> <p><span class="wintitle">报表服务器</span>生成状态信息并将状态信息发送到Data Workbench Server以在<span class="wintitle">详细状态</span>中显示的频率（以秒为单位）。 </p> <p>默认值为 120 秒。不建议将此值设置为较小的值（如2分钟），因为报告队列可能需要数小时才能运行。 在这种情况下，您可以考虑设置600到1200秒。 </p> <p>有关<span class="wintitle">详细状态</span>的详细信息，请参阅<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight用户指南</a>的“管理界面”一章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新间隔 </td> 
   <td colname="col2"> <p><span class="keyword">报表服务器</span>监视用户档案矢量中列出的所有报告和警报的频率（以分钟为单位）。 默认值为10分钟。 </p> <p>您指定的时间将被划分到列出的所有用户档案中。 例如，如果将间隔设置为10分钟，并且您正在监视两个用户档案，则每个用户档案将监视5分钟。 如果在将新的或修改的报告或警报保存到用户档案时监视用户档案，则报告或警报可立即生成。 </p> <p>如果将<span class="wintitle">更新间隔</span>配置为监视多个用户档案，则必须确保此设置足够高，以在配置的时间内加载所有用户档案。 在配置了许多大尺寸的系统中，例如，检索包含所有元素名称的初始数据连接可能需要几分钟时间，此设置必须足够长，才能进行完全同步。 否则，系统会发出用户档案同步错误。 </p> </td> 
  </tr> 
 </tbody> 
</table>
