---
description: 为Insight Server或Repeater配置通信的说明。
solution: Insight
title: 通信配置设置
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 通信配置设置{#communications-configuration-settings}

为Insight Server或Repeater配置通信的说明。

在以下文件中完成参数：

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
   <td colname="col2"> <p>Access Control.cfg <span class="filepath"> 文件的位 </span> 置。 默认位置是Insight Server或 <span class="filepath"> Repeater安装目 </span> 录中的“访问控 <span class="keyword"> 制”文件 </span><span class="wintitle"></span> 夹。 </p> <p>示例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志目录 </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例： <filepath></filepath> </p> <p> <p>注意： 您可以将审核日志映射到另一个本地驱动器(例如： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不要将审核日志映射到网络驱动器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 访问日志详细 </td> 
   <td colname="col2"> 此参数可以设置为true或false。 它用于启用和禁用审核日志筛选。 要确保记录每个请求，请将该参数设置为True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP接口 </td> 
   <td colname="col2"> <p>当两个网卡可用于访问两个不同网络时使用的IP地址。 </p> <p>示例：我 <filepath></filepath><i>&lt; <span class="filepath"> IP 地址 </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port（端口） </td> 
   <td colname="col2"> <p>Insight Server或Repeater监听的非安全(HTTP)端 <span class="keyword"> 口 </span> 的 <span class="wintitle"></span> 端口。 默认端口为 80。输入值0将禁用非安全连接。 </p> <p>示例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL密码 </td> 
   <td colname="col2"> 某些环境需要比其他环境更强的通信安全性。 如果要使用特定的SSL密码套件，可使用此参数指定它。 <p>示例： <filepath></filepath> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL端口 </td> 
   <td colname="col2"> <p>Insight Server或Repeater监听的安全（通过SSL）端 <span class="keyword"> 口 </span> 端 <span class="wintitle"></span> 口。 默认端口为 443。输入值0将禁用安全连接。 </p> <p>示例：<span class="filepath"></span> </p> <filepath></filepath> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> “记录服务器”设置的标题。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 客户名称 </td> 
   <td colname="col2"> <p>要在管理警报中显示“未指定”客户的客户名称，如下例所示： </p> <p>“在15中，没有从传感器XYZ收到客户“未指定”的数据。” </p> <p>示例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>使用上面的示例，“未指定”客户的管理警报现在将如下： </p> <p>“在15年内，没有从传感器XYZ为客户‘CompanyAB’接收数据。” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> 本地路径=字符串：日志\\ </p> </td> 
   <td colname="col2"> <p>要存储日志文件的文件夹。 </p> <p>示例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>要能够从“服务器文件管理器”访问此文件夹 <span class="wintitle"> ，在此参数中指定的位置必须与您在 </span>Log Processing.cfg文件的Log Paths（日志路径）参数中指定的位置相 <span class="filepath"></span> 匹配。 有关修改Log Processing.cfg文件中的Logs目录的更 <span class="filepath"> 多信息，请参 </span> 阅《数据集配置指南》的Log Processing Configuration File <i>一章</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> 本地路径=字符串：审核\\ </p> </td> 
   <td colname="col2"> <p>要将审核日志映射到的文件夹。 </p> <p>示例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注释:  <p>您可以将审核日志映射到另一个本地驱动器(例如： <span class="filepath"> 字符串：P:\\Audit\\ </span>)，但不要将审核日志映射到网络驱动器。 </p> <p>要能够从“服务器文件管理器”访问此文件夹， <span class="wintitle"></span>此参数中指定的位置必须与您在此文件的“访问日志目录”参数中的位置相匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=标准</i>化服务器： </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>。 </p> <p>有关为 <span class="keyword"> Insight Server群集指定Centralized Normalization Server（集中标准化服务器）的更多信息，请参阅《数据集配置指南》的“日志处理配 </span> 置文件”一章 <i></i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string:/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>此参数仅适用于 <span class="keyword"> Insight Server </span>。 </p> <p>允许您在 <span class="keyword"> Insight Server的详细状 </span> 态界面中查看报表的状态 <span class="keyword"></span>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

