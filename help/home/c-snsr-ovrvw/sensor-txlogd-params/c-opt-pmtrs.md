---
description: 有关可选传感器txlogd.conf文件参数的信息。
title: 可选的参数
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 2%

---

# 可选的参数{#optional-parameters}

有关可选传感器txlogd.conf文件参数的信息。

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>允许您过滤指定的IP地址。 </p> <p>过滤特定地址时，不会记录“数据包”。 该功能在日志处理之前消除内部或被监视的代理，从而提高日志处理的速度并减少数据存储要求。 在指定地址时，可以使用通配符。 </p> <p>示例：<span class="filepath"> AddressFilter 10.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>指定是否在日志记录中包含或排除某些类型的内容。 </p> <p>参数值与回复的内容类型进行前缀匹配。 </p> <p>例如，"image/"匹配所有图像内容类型，而"image/gif"仅匹配该类型。 当给定内容类型发生多个匹配时，将使用最具体的匹配。 因此，您可以将"image/gif"放在ContentFilterInclude参数中，将"image/gif"放在ContentFilterExclude参数中，并允许"image/gif"回复，但所有其他图像类型都会被过滤掉。 </p> <p>示例：<span class="filepath"> ContentFilterInclude *</span> </p> <p>示例：<span class="filepath"> ContentFilterExclude image/,text/css，application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>为Web模块和发射器启用调试日志记录。 </p> <p>当<span class="wintitle">传感器</span>不能正常工作时，请使用此参数。 设置此参数后，必须在指定的路径位置创建一个空文件，并为所有用户授予“写入”权限。 例如（在Web服务器上的unix外壳中）： 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>您应该只启用短时间的调试日志记录，之后应将日志文件发送到Adobe咨询服务部门进行分析。 </p> <p>示例：<span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe建议首先在测试环境中设置此参数，以确定对系统的影响。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>禁用指定字段 </p> <p>用户可以删除他们不使用或不想存储的字段。 如果字段取字符串值，则禁用该字段会传递一个空字符串。 如果字段取数值，则禁用该字段会传递数值零(0)。 您可以禁用以下字段： 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-访客 </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experiment </li> 
     </ul> </p> <p>示例：<span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>“受控实验”配置文件的路径。 </p> <p>示例：<span class="filepath"> C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>当请求时，导致生成新跟踪ID并将用户放置到实验组中的资源。 </p> <p> <p>注意： 此资源不必在Web服务器上实际存在。 </p> </p> <p>示例：<span class="filepath"> /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>如果要启用控制实验将整个站点或站点的整个子目录重新映射到另一个位置，请将此参数设置为“on”。 默认为“off”。 </p> <p>示例：<span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>注意： 将此参数设置为“on”时要非常小心。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>确定即使用户请求由ContentFilterExclude参数筛选出的文档类型，是否记录每个新用户的首次单击。 </p> <p>默认值为“no”。 </p> <p>通常，图像文件会通过ContentFilterExclude参数过滤掉。 如果LogAllNewUsers设置为“是”，且新用户从服务器获得的第一个文档是映像，则将记录该请求。 如果LogAllNewUsers参数设置为“no”或根本未设置（并假设图像被ContentFilterExclude参数过滤掉），且新用户从服务器获得的第一个文档是图像，则不记录该请求。 </p> <p>示例：<span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>发送器等待发送下一批数据包的时间（以秒为单位）。 </p> <p>默认值为 15。 </p> <p>示例：<span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>注意： 在未先联系Adobe咨询服务部门的情况下，请勿更改此参数值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隐私ID </td> 
   <td colname="col2"> <p>允许您禁用访客跟踪，它可用于遵守退出策略。 </p> <p>启用后，<span class="wintitle">传感器</span>不会为其V1st Cookie设置为指定的PrivacyID的任何访客记录“包”。 由于没有记录这些访客的信息，因此没有将这些访客的相关信息发送到<span class="keyword"> Data Workbench Server</span>以进行处理。 </p> <p>要启用此功能，您必须完成以下步骤： 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> 在<span class="wintitle">传感器</span>的<span class="filepath"> txlogd.conf</span>文件中，PrivacyID的值必须为0（零）。 <p>示例：<span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">网站所有者必须编写代码来设置访客(V1st)Cookie，以使Cookie ID值与定义的PrivacyID值“<span class="filepath"> txlogd.conf</span>”匹配。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>发射器(txlogd)定期向其发送请求的位置，以查看网站是否运行正确。 </p> <p>请注意，该位置是按以下格式指定的，而不是URL: </p> <p>http，<i>serverAddress，port，/resource</i> </p> <p>其中<i>serverAddress</i>是服务器名称或IP地址，<i>port</i>是服务器的HTTP侦听端口，而<i>resource</i>是要请求的特定资源(可以包括查询字符串)。 </p> <p>可以指定多条SiteTest行。 </p> <p>示例：<span class="filepath"> SiteTest http，localhost，80,/test.html</span> </p> <p> <p>注意： 此时仅支持http。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>在访客的浏览器上设置的Cookie的名称。 </p> <p>默认值为“v1st”。 </p> <p>示例：<span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>指示是否根据CertName参数验证服务器 </p> <p>默认为“on”。 </p> <p>示例：<span class="filepath"></span>上的VerifyCertName </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>告诉IIS <span class="wintitle"> Sensor</span> ，两个可能的日志记录“挂接”中哪个应用于记录数据包 </p> <p>当IIS <span class="wintitle">传感器</span>未正确记录数据包时，请使用此参数。 如果默认日志记录挂接不能正常工作，则此参数将设置为“off”。 默认为“on”。 </p> <p>示例：<span class="filepath">在</span>上发送的ISCaptureBytes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>告诉<span class="wintitle">传感器</span>应使用哪两个可能的“挂接”设置v1st cookie。 </p> <p>当IIS <span class="wintitle">传感器</span>未正确设置v1st Cookie时，请使用此参数。 如果默认挂接未正确设置v1st cookie，则此参数将设置为“yes”。 默认值为“no”。 </p> <p>示例：<span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>默认情况下，<span class="wintitle">传感器</span>会在每个请求上发送缓存控制响应标头。 启用缓存控制功能后，<span class="wintitle">传感器</span>将向浏览器发送一个Expires头，其值为Thu， 1994年12月01日16:00:00 GMT。 </p> <p>您可以根据需要修改响应字符串，方法是在<span class="filepath"> txlogd.conf</span>文件中编辑以下两行： </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>示例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl私有，max-age=0,must-revalidate</span> </p> <p>要禁用缓存控制响应头的发送，请为每行键入连字符，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此参数中…… </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>告诉<span class="wintitle">传感器</span>应使用哪两个可能的“挂接”设置v1st cookie。 </p> <p>当Apache <span class="wintitle"> Sensor</span>未正确设置v1st cookie时，请使用此参数。 如果默认挂接未正确设置v1st cookie，则此参数将设置为“yes”。 默认值为“no”。 </p> <p>示例：<span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>指示<span class="wintitle">传感器</span>尝试在两个挂钩中设置v1st cookie。 </p> <p>当Apache <span class="wintitle"> Sensor</span>未正确设置v1st cookie时，请使用此参数。 默认值为“是”。 </p> <p>如果设置为“是”，并且在第一个挂接中未正确设置v1st cookie，则使用第二个挂接。 如果设置为“no”，则应设置ApacheUseAlternateHandler参数以指示用于设置v1st cookie的挂钩。 </p> <p>示例：<span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>默认情况下，<span class="wintitle">传感器</span>会在每个请求上发送缓存控制响应标头。 启用缓存控制功能后，<span class="wintitle">传感器</span>将向浏览器发送一个Expires头，其值为Thu， 1994年12月01日16:00:00 GMT。 </p> <p>您可以根据需要修改响应字符串，方法是在<span class="filepath"> txlogd.conf</span>文件中编辑以下两行： </p> <p> <span class="filepath"> </span> <i>&lt;&gt; NewUserCacheControlstring1</span>&gt;</i><span class="filepath"> </span></p> <p> <span class="filepath"> </span> <i>&lt;&gt; CacheControlstring2</span>&gt;</i><span class="filepath"> </span></p> <p>示例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl私有，max-age=0,must-revalidate</span> </p> <p>要禁用缓存控制响应头的发送，请为每行键入连字符，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>注意： Adobe建议您不要禁用此功能。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此参数中…… </th> 
   <th colname="col2" class="entry"> 在“管理工具”中指定分类的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>告诉<span class="wintitle">传感器</span>应使用哪两个可能的“挂接”设置v1st cookie。 </p> <p>当Apache <span class="wintitle"> Sensor</span>未正确设置v1st cookie时，请使用此参数。 如果默认挂接未正确设置v1st cookie，则此参数将设置为“yes”。 默认值为“no”。 </p> <p>示例：<span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>仅在使用Adobe咨询服务时设置此参数。 </p> <p>指示<span class="wintitle">传感器</span>尝试在两个挂钩中设置v1st cookie。 </p> <p>当Apache <span class="wintitle"> Sensor</span>未正确设置v1st cookie时，请使用此参数。 默认值为“是”。 </p> <p>如果设置为“是”，并且在第一个挂接中未正确设置v1st cookie，则使用第二个挂接。 如果设置为“no”，则应设置ApacheUseAlternateHandler参数以指示用于设置v1st cookie的挂钩。 </p> <p>示例：<span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
