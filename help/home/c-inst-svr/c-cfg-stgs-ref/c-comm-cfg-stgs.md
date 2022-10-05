---
description: 有关为Insight Server或中继器配置通信的说明。
title: 通信配置设置
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 通信配置设置{#communications-configuration-settings}

{{eol}}

有关为Insight Server或中继器配置通信的说明。

完成以下文件中的参数：

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>在修改此表中未列出的任何参数之前，请联系Adobe。

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 访问控制文件 </td> 
   <td colname="col2"> <p>的位置 <span class="filepath"> Access Control.cfg </span> 文件。 默认位置为 <span class="filepath"> 访问控制 </span> 文件夹 <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中继器 </span> 安装目录。 </p> <p>示例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志目录 </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意：您可以将审核日志映射到其他本地驱动器(例如： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不要将审核日志映射到网络驱动器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志详细 </td> 
   <td colname="col2"> 此参数可设置为true或false。 用于启用和禁用审核日志过滤。 要确保记录每个请求，请将参数设置为True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP接口 </td> 
   <td colname="col2"> <p>两个网卡可用于访问两个不同网络时使用的IP地址。 </p> <p>示例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> <p>非安全(HTTP)端口，其上 <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中继器 </span> 监听。 默认端口为 80。输入值0将禁用非安全连接。 </p> <p>示例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL密码 </td> 
   <td colname="col2"> 某些环境需要比其他环境更强的通信安全性。 如果要使用特定的SSL密码包，可以使用此参数指定它。 <p>示例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL端口 </td> 
   <td colname="col2"> <p>安全（通过SSL）端口，其上 <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中继器 </span> 监听。 默认端口为 443。输入值0将禁用安全连接。 </p> <p>示例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> “日志记录服务器”设置的标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 客户名称 </td> 
   <td colname="col2"> <p>要在管理警报中显示未指定客户的客户名称，如以下示例所示： </p> <p>15中没有从传感器XYZ收到客户“未指定”的数据。 </p> <p>示例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>使用上面的示例，针对未指定客户的管理警报现在如下所示： </p> <p>“在15中，没有从传感器XYZ收到客户‘CompanyAB’的数据。” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>文件服务器： </p> <p> 本地路径=字符串：日志\\ </p> </td> 
   <td colname="col2"> <p>要在其中存储日志文件的文件夹。 </p> <p>示例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>从 <span class="wintitle"> 服务器文件管理器 </span>，则此参数中指定的位置必须与 <span class="filepath"> Log Processing.cfg </span> 文件。 有关修改 <span class="filepath"> Log Processing.cfg </span> 文件，请参阅 <i>数据集配置指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>文件服务器： </p> <p> 本地路径=字符串：审核\\ </p> </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注释：  <p>您可以将审核日志映射到其他本地驱动器(例如： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不要将审核日志映射到网络驱动器。 </p> <p>从 <span class="wintitle"> 服务器文件管理器 </span>，此参数中指定的位置必须与您在此文件的Access Log Directory（访问日志目录）参数中的位置匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>标准化服务器： </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>. </p> <p>有关为 <span class="keyword"> Insight Server </span> 群集，请参阅 <i>数据集配置指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI =字符串：/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>. </p> <p>允许您查看 <span class="keyword"> 报表 </span> 的详细状态界面中的状态 <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
