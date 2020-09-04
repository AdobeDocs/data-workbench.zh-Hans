---
description: 为Insight Server或Repeater配置通信的说明。
solution: Insight
title: 通信配置设置
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: 638eca495223fc9d5326bf9462a9c289d6fe2d9e
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---


# 通信配置设置{#communications-configuration-settings}

为Insight Server或Repeater配置通信的说明。

在以下文件中填写参数：

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>在修改此表中未列出的任何参数之前，请与Adobe联系。

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
   <td colname="col2"> <p>访问控制.cfg <span class="filepath"> 文件的 </span> 位置。 默认位置是Insight Server <span class="filepath"> 或Repeater安 </span> 装目录中的 <span class="keyword"> 访问控制文 </span> 件夹， <span class="wintitle"> 该文 </span> 件夹位于Insight Server。 </p> <p>示例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志目录 </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意： 您可以将审核日志映射到另一个本地驱动器(示例： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不将审核日志映射到网络驱动器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志详细 </td> 
   <td colname="col2"> 此参数可设置为true或false。 它用于启用和禁用审核日志过滤。 要确保记录每个请求，请将参数设置为True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP接口 </td> 
   <td colname="col2"> <p>当两个网卡可用于访问两个不同网络时使用的IP地址。 </p> <p>示例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> <p>Insight Server或Repeater监听的非安 <span class="keyword"> 全(HTTP) </span> 端 <span class="wintitle"> 口 </span> 。 默认端口为 80。输入值0将禁用非安全连接。 </p> <p>示例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL密码 </td> 
   <td colname="col2"> 一些环境需要比其他公司更强大的通信安全。 如果要使用特定的SSL密码套件，可使用此参数指定它。 <p>示例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL端口 </td> 
   <td colname="col2"> <p>Insight Server或Repeater监听的安 <span class="keyword"> 全(通 </span> 过SSL <span class="wintitle"> )端 </span> 口。 默认端口为 443。输入值0将禁用安全连接。 </p> <p>示例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> “日志记录服务器”设置的标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 客户名称 </td> 
   <td colname="col2"> <p>管理警报中“未指定”客户显示的客户名称，如下例所示： </p> <p>“在15中，没有从传感器XYZ为客户“未指定”接收数据。” </p> <p>示例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>使用上面的示例，“未指定”客户的管理警报现在将如下所示： </p> <p>“15年内没有从传感器XYZ为客户‘CompanyAB’接收数据。” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=文</i>件服务器： </p> <p> 本地路径=字符串：日志\\ </p> </td> 
   <td colname="col2"> <p>要存储日志文件的文件夹。 </p> <p>示例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>要能够从服务器文件管理器 <span class="wintitle"> 访问此文 </span>件夹，此参数中指定的位置必须与您在Log Processing.cfg文件的Log Paths参数中指定的 <span class="filepath"> 位置相 </span> 匹配。 有关修改Log Processing.cfg文件中的Logs目 <span class="filepath"> 录的详细信 </span> 息，请参阅《数据集配置指南》的Log Processing Configuration File <i>一章</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=文</i>件服务器： </p> <p> 本地路径=字符串：审核\\ </p> </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注释：  <p>您可以将审核日志映射到另一个本地驱动器(示例： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不将审核日志映射到网络驱动器。 </p> <p>要能够从服务器文件管理器 <span class="wintitle"> 访问此文 </span>件夹，此参数中指定的位置必须与此文件中“访问日志目录”参数中的位置匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=标准</i>化服务器： </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>。 </p> <p>有关为Insight Server群集指定Centralized Normalization Server的更 <span class="keyword"> 多信 </span> 息，请参阅《数据集配置指南》的“日志处理配 <i>置文件”一章</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI =字符串：/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>。 </p> <p>允许您在Insight Server的 <span class="keyword"> 详细状 </span> 态界面中视图报表 <span class="keyword"> 的状态 </span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
