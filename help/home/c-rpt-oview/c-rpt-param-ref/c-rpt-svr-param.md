---
description: 有关Report Server.cfg参数的信息。
solution: Analytics
title: Report Server.cfg参数
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Report Server.cfg参数{#report-server-cfg-parameters}

有关Report Server.cfg参数的信息。

配置 [!DNL Report Server.cfg] 到Insight Server的 [连接中显示的示例默认情况下只包含文件中包含](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)[!DNL Report Server.cfg] 的参数。

如果通过代理服务器与Adobe许可证服务器联系，则需要将许可矢量及其参数添加到 [!DNL Report Server.cfg]。 以下是此矢量及其参数的一个示例，您可以将模型用于您的授权矢量：

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

下表提供了文件参数的 [!DNL Report Server.cfg] 说明：

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
   <td colname="col2"> <p>支持的Excel扩展包括： </p> <p>Excel Extension = string: <span class="filepath"> .xlsx </span> </p> <p>Excel Extension = string: <span class="filepath"> .xls </span> （这是默认设置） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fonts（字体） </td> 
   <td colname="col2"> <p>可选。Vector listing the fonts that <span class="keyword"> Report Server </span> should use to render UTF8-based unicode special characters. 列表中字体的数量不受限制。 </p> <p>第一种字体应始终为 Lucida Sans Console。If this parameter is not included in the <span class="filepath"> Report Server.cfg </span> file, <span class="keyword"> Report Server </span> uses only Lucida Sans console to display text. </p> <p> <span class="keyword"> 报表服 </span> 务器使用列表中的第一种字体渲染所有字符，直到遇到无法渲染的字符。 然后，它使用列表中的第二种字体来渲染该字符。 If that font does not render the character, <span class="keyword"> Report Server </span> uses the third font in the list to render that character, and so on, until it reaches the end of the font list. If the correct font is not listed in the vector, <span class="keyword"> Report Server </span> displays the hexidecimal value for the character. </p> <p> <p>注意： 在报告服务器运行时，请勿对 <span class="keyword"> 此参数 </span> 进行更改。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma（伽马） </td> 
   <td colname="col2"> <p> <span class="wintitle"> .png </span> 文件输出 <span class="filepath"> 的Gamma </span> 设置。 默认值为 1.6。 </p> <p> <p>注意： Adobe不建议更改此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licensing（许可） </td> 
   <td colname="col2"> <p>可选。仅当您通过代理服务器与Adobe的许可证服务器联系时，才需要修改此矢量中的参数。 </p> <p>设置为通过代理服务器与Adobe的许可证服务器联系的参数的章节标识符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address（代理地址） </td> 
   <td colname="col2"> The address of a proxy server that <span class="keyword"> Report Server </span> must use to access Adobe's license server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password（代理密码） </td> 
   <td colname="col2"> 可选。The password associated with the <span class="wintitle"> Proxy User Name </span>. </td> 
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
   <td colname="col2"> The network location that <span class="keyword"> Report Server </span> uses to resolve the server's common name to an IP address. 网络位置在位于Data Workbench Server计算机上“地址”目录的地址文件中定义。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 服务器 </td> 
   <td colname="col2"> <p>设置为配置Report Server的哪些Data Workbench Server计算机必须连接才能生成 <span class="keyword"> 报告的参数 </span> 的章节标识符。 这包括一个数字，用于指示在此矢量中列出的项目数。 </p> <p>对于每台服务器，添加一个serverInfo条目并根据需要完成参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 报表服务器必须连接到的Data Workbench Server计算 <span class="keyword"> 机以 </span> 生成报表的IP地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名称 </td> 
   <td colname="col2"> 报表服务器 <span class="keyword"> 内部用 </span> 于标识Data Workbench Server的名称。 这只是一个内部标签，因此您可以使用您喜欢的任何名称。 为保持一致性，我们建议您使用服务器数字证书上列出的通用名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> Report Server与Data Workbench Server通 <span class="keyword"> 过的 </span> 端口进行通信。 对于安全连接，此值通常为443。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Address（代理地址） </td> 
   <td colname="col2"> The address of a proxy server that <span class="keyword"> Report Server </span> must use to access the data workbench server. 仅当需要代理服务器连接到服务器计算机时才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Password（代理密码） </td> 
   <td colname="col2"> 代理服务器的密码。仅当需要代理服务器才能连接到Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy Port（代理端口） </td> 
   <td colname="col2"> 代理服务器的端口。默认值为 8080。仅当需要代理服务器才能连接到Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Proxy User Name（代理用户名） </td> 
   <td colname="col2"> 代理服务器的用户名。 仅当需要代理服务器才能连接到Data Workbench Server计算机时，才需要此参数。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Client Certificate（SSL 客户端证书） </td> 
   <td colname="col2"> 报告服务器计算机的SSL证 <span class="keyword"> 书文件 </span> 名称。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Server Common Name（SSL 服务器通用名称） </td> 
   <td colname="col2"> <span class="wintitle"> 服务器公 </span> 用名称列在Data Workbench Server的数字证书上。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Use SSL（使用 SSL） </td> 
   <td colname="col2"> Indicates whether SSL is used for secure communication between the data workbench server and <span class="keyword"> Report Server </span>. 选项为 true 或 false。默认值为 true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 结果内存限制(KB) </td> 
   <td colname="col2"> <p>要用于报告和警报的内存量（以KB为单位）。 默认值为 50000。 </p> <p>运行报告时， <span class="keyword"> Report Server首先 </span> 检查此值，然后检查“最大切片大小”参数中的值。 例如，如果将此参数设置为50,000，而将“最大切片大小”设置为50，则 <span class="keyword"></span> Report Server一次仅运行50个工作区，即使有空间运行更多工作区也是如此。 </p> <p> <p>注意： 此限制不应超过在Data Workbench Server的“查询内存限制”参数中设置的值，并且最好设置为略低于“查询内存限制”，以便为同时运行报告的其他用户提供一些余地。 <span class="wintitle"></span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大切片大小 </td> 
   <td colname="col2"> 报告服务器一次可运行 <span class="keyword"> 的最 </span> 大报告工作区数。 默认值为 50。有关报告服务器如 <span class="keyword"> 何使用此设 </span> 置的详细信息，请参阅“结果内 <span class="wintitle"> 存限制(KB)”参数 </span> 说明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Update Software（更新软件） </td> 
   <td colname="col2"> <p>Indicates whether to allow this <span class="keyword"> Report Server's </span> software to be updated by the data workbench server. 选项为 true 或 false。默认值为 true。 </p> <p>以下是此参数的一个示例，您可以使用模型： </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用OpenGL硬件渲染 </td> 
   <td colname="col2"> <p>控制报 <span class="keyword"> 告服务器 </span> 是否使用硬件渲染（如机器的图形卡）生成报告输出。 选项为 true 或 false。默认值为 true。 </p> <p>仅当您遇到图形卡问题时，此参数才应设置为false。 设置为false时，报 <span class="keyword"> 告服务器 </span> 不会尝试使用硬件渲染，默认情况下使用软件渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 报表 </td> 
   <td colname="col2"> 设置为配置报告的参数的章节标识符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成消息间隔 </td> 
   <td colname="col2"> <p>在报告或警报生成过程中运行 <span class="keyword"> 查询时，Report Server </span> 将打印完成状态消息的频率（以秒为单位）。 默认值为 120 秒。 </p> <p>示例：工作区查询完成率为62.145672%。 </p> <p>完成消息将写入 <span class="filepath"> reportserver.log中 </span> ，并同步到服务器。 此设置控制 <span class="filepath"> 每个报告集来回发 </span> 送的status.txt文件，以便用缩略图显示完成百分比。 每当报告集完成或到达时间间隔时（以先到者为准）发送消息。 将此值设置得较高不会影响缩略图在客户端界面中生成的报表的查看速率，但会影响您看到的中间消息数。 指定低值可能导致系统花费大量时间同步数据，因为每当 <span class="keyword"> status.txt消息发生更改时，数据会从 </span> Report Server <span class="filepath"></span> Server同步到所有DPU和所有连接的客户端的配置文件。 </p> <p>无论此配置参 <span class="filepath"> 数的设置如何，系统 </span> 始终会在报告集完成时发送status.txt文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 配置文件 </td> 
   <td colname="col2"> <p>指示此矢量中列出的项目数。 对于要为其创建报表的每个配置文件，在“配置文件”矢量中添 <span class="wintitle"> 加一个 </span> ReportProfile条目，并完成“服务器”和“配置文件”参数。 </p> <p> <span class="wintitle"> 服务 </span> 器——报表服务器内 <span class="keyword"> 部用 </span> 于标识Data Workbench Server的名称。 此名称必须是Data Workbench Server的SSL证书上列出的服务器通用名称。 </p> <p> <span class="wintitle"> 配 </span> 置文件——要为其创建报告的配置文件的名称。 此名称必须与Data Workbench Server计算机上的已命名配置文件相匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器出错 </td> 
   <td colname="col2"> <p>要通过电子邮件发送报告服务器错误的SMTP服 <span class="wintitle"> 务器 </span> 的地址。 </p> <p>示例： <span class="filepath"> mail.mycompany.com </span> </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器错误密码 </td> 
   <td colname="col2"> <p>登录SMTP服务器的口令。 除非发送邮件需要登录，否则此参数是可选的。 </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送错误的SMTP服务器 </td> 
   <td colname="col2"> 要从中发送报告服务器错误的电 <span class="wintitle"> 子邮件 </span> 地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 发送到的SMTP服务器有错误 </td> 
   <td colname="col2"> <p>发送警报的电子邮件地址。 </p> <p>示例： <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP服务器错误用户名 </td> 
   <td colname="col2"> <p>用于登录SMTP服务器的用户名。 除非发送邮件需要登录，否则此参数是可选的。 </p> <p>使用上述功能需要SMTP服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 状态间隔 </td> 
   <td colname="col2"> <p>报表服务器生成状态信息并将其发送 <span class="wintitle"> 到Data Workbench Server以在“详细状态”中显示的频率(以 </span> 秒为单位) <span class="wintitle"></span>。 </p> <p>默认值为 120 秒。不建议将此值设置为小值（如两分钟），因为报告队列可能需要数小时才能运行。 在这种情况下，您可以考虑将600到1200秒。 </p> <p>For more information about <span class="wintitle"> Detailed Status </span>, see the Administrative Interfaces chapter of the <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight User Guide </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新间隔 </td> 
   <td colname="col2"> <p>报告服务器监视“配置文件”矢量中列 <span class="keyword"> 出的所 </span> 有配置文件以获取新报告和警报的频率（以分钟为单位）。 默认值是10分钟。 </p> <p>您指定的时间被分配到列出的所有配置文件中。 例如，如果您的间隔设置为10分钟，并且您正在监视两个配置文件，则每个配置文件都会被监视5分钟。 如果在将新的或修改的报告或警报保存到配置文件时正在监视配置文件，则报告或警报可立即生成。 </p> <p>如果“更 <span class="wintitle"> 新间隔”配置 </span> 为监视多个配置文件，则此设置必须足够高，以在配置的时间内加载所有配置文件。 例如，在配置了许多大尺寸的系统中，检索包含所有元素名称的初始数据连接可能需要几分钟时间，此设置必须足够长，才能进行完全同步。 否则，系统会发出配置文件同步错误。 </p> </td> 
  </tr> 
 </tbody> 
</table>

