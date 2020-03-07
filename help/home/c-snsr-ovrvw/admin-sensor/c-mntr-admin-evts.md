---
description: 要尽快检测传感器错误并在造成严重问题或中断之前对其进行修复，您应定期监控事件日志。
solution: Insight
title: 监视管理事件
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 监视管理事件{#monitoring-administrative-events}

要尽快检测传感器错误并在造成严重问题或中断之前对其进行修复，您应定期监控事件日志。

**推荐频率：** 至少每小时

您可以使用Windows事件查看器或Unix Syslog文件以及默认位于安装目 [!DNL *.sensor-log] 录内文件夹中的文件来监 [!DNL Logs] 视这些 [!DNL Sensor] 事件。 这些文件表示在数据收集过程中存在错误，尤其是当无法连 [!DNL Sensor] 接到目标并开始排队 [!DNL data workbench server] 数据时。

## 在Windows上监视事件 {#section-7c0443a356af4381bf22259654f5cd17}

传感器将错误记录到源为“Adobe”的Windows事件查看器的“应用程序日志”中。

根据消息的严重性，消息将作为“信息”、“警告”或“错误”记录。

**打开Windows事件查看器**:

* 单击“ **开始”>“控制面板”>“管理工具”>“活动查看器**”。

## 在Unix上监视事件 {#section-5de3947891fb47ac88b7c855e545d54a}

传感器将错误记录到守护 [!DNL syslog] 程序。

syslog守护程序根据您在syslog.conf文件中指定的规则将错误消息写入日志文件。 根据严重性，错误会记录在标记“LOG_DAEMON”和“LOG_NOTICE”或“LOG_ERR”中。

**打开Unix syslog**

Unix syslog通常位于或 [!DNL /var/adm/messages] 中 [!DNL /var/log/messages]。

浏览到相应的位置并打开syslog。

## 了解消息格式 {#section-a0899add30fd4b2da58a23b9e3324693}

所有传感器消息都包含字符串“Sensor”，并且编号反映显示消息的重要性。

| 消息编号 | 消息含义 | 消息字符串 |
|---|---|---|
| 1xxx | 信息性 | 传感器信息编号 |
| 2xxx | 警告 | 传感器警告编号 |
| 3xxx | 配置错误 | 传感器错误编号 |
| 4xxx | 操作错误 | 传感器错误编号 |
| 5xxx | 内部错误 | 传感器错误编号 |

>[!NOTE]
>
>警告(2xxx)当前未使用。 这些数字留待将来使用。

网络管理工具可设置为每5-10分钟监视一次消息，以发现“传感器”源出现错误，并提醒相应人员可能需要干预的问题。 您可以选择仅监视系统中某些类型的事件消息，如“传感器错误”字符串。 或者，您也可以将不同的规则应用于以“传感器信息”、“传感器警告”和“传感器错误”字符串为前面的事件。

## 识别重要消息 {#section-5a20f5dc18ca4012931d194db855e54e}

在事件日志中，您应特别注意并立即处理与队列大小相关的任何消息。

例如，“”等消息 [!DNL Sensor Info 1012: Adobe disk queue is #% full]需要注意。

## 响应传感器事件消息 {#section-0004c4a169dc4a8882d9bd87dd326ad4}

描述传感器事件的表以及针对支持的Web服务器平台的建议操作。

**所有平台**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活动消息 </th> 
   <th colname="col2" class="entry"> 建议的操作 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 传感器信息1010:传感器已初始化。 </td> 
   <td colname="col2"> 无需执行任何操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1011:传感器已终止。 已排队的点击总数## </td> 
   <td colname="col2"> 无需执行任何操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1012:Adobe磁盘队列已满#% </td> 
   <td colname="col2"> 每次磁盘队列利用率超过10%阈值时都会记录此消息。 如果此百分比继续增加，则应在队列已满和数据丢失之前采取相应操作。 最有可能的问题是传感器已停止与Insight Server通信。 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1013:传感器配置已更改 </td> 
   <td colname="col2"> 无需执行任何操作。 传感器检测到其中一个配置文件发生更改，并将重新加载。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1014:问题播种随机数生成器 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1016:已加载配置文件文件名 </td> 
   <td colname="col2"> 无需执行任何操作。 传感器成功加载了列出的配置文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器信息1017:加载实验文件文件名 </td> 
   <td colname="col2"> 无需执行任何操作。 传感器成功加载了列出的实验文件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误3016:无法加载配置文件/mypath/myfile </td> 
   <td colname="col2"> 确认在Web服务器配置中指定的传感器配置文件存在，并且具有Web服务器进程读取所需的权限。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>传感器3017:无法加载受控实验配置文件/mypath/myfile </p> </td> 
   <td colname="col2"> <p>确认txlogd.conf中指定的受控实验文件存在，并且txlogd进程具有读取文件所需的权限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误3018:无法解析内容过滤器列表。 检查文本配置文件 </td> 
   <td colname="col2"> 验证txlogd.conf中ContentFilterInclude和ContentFilterExclude条目的语法。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误3023:无法创建锁定(g_lockThrottle) </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误3024:创建锁定失败(g_lockConfigCheck) </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误4014:无法打开磁盘队列。 </td> 
   <td colname="col2"> 验证txlogd.conf中的QueueFile文件名，如果认为正确，请与Adobe ClientCare联系。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误4020:不是队列文件 </td> 
   <td colname="col2"> 验证txlogd.conf中的QueueFile文件名，如果认为正确，请与Adobe ClientCare联系。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误4021:队列已满 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误4022:无法映射长度&lt;x&gt;在偏移&lt;y&gt;处的内存块 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5012:无法创建互斥体。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5013:无法获取互斥体。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5030:产生分叉错误。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5031:setsid失败。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5032:产生分叉错误。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5033:chdir失败。 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5034:接收的信号 </td> 
   <td colname="col2"> 程序可能由外部信号终止。 如果无法确定此信号的源，请与Adobe ClientCare联系。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5035:从外部主页调用退出 </td> 
   <td colname="col2"> 联系Adobe ClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 传感器错误5036:txlogd已在运行 </td> 
   <td colname="col2"> txlogd守护程序的另一个实例已在运行。 如果要运行新实例，请先停止另一个实例。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| 活动消息 | 建议的操作 |
|---|---|
| 传感器错误3015:httpd.conf中缺少VisualSciencesConfig指令。 | 这是配置错误。 VisualSciencesConfig指令必须位于httpd.conf中，并且参数为txlogd.conf的位置。 |
| 传感器错误3019:vys-log之前未调用vys-cookie。 请联系支持部门。 | 联系Adobe ClientCare。 |
| 传感器错误3025:子请求点返回到自身 | 联系Adobe ClientCare。 |

**AOL Server**

| 活动消息 | 建议的操作 |
|---|---|
| 传感器错误3015:ns/server/[server]/module/[module] section is missing in AOLServer config file. | 这是配置错误。 正确无误。 |
| 传感器错误3019:vys-log之前未调用vys-cookie。 请联系支持部门。 联系Adobe ClientCare。 | 请联系支持部门。 联系Adobe ClientCare。 |
| 传感器错误3020:VisualSciencesConfig缺少AOLServer配置文件“部 [分] ”部分中的第一个条目。 | 这是配置错误。 正确无误。 |
| 传感器错误3021:VisualSciencesConfig在AOLServer配置文件的 [section] 部分中缺少值。 | 这是配置错误。 正确无误。 |

**iPlanet和Java System Web Server**

| 活动消息 | 建议的操作 |
|---|---|
| 传感器错误3011:需要Init指令。 例如，Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | 这是配置错误。 缺少iPlanet init指令。 |
| 传感器错误3015:在iPlanet Init指令中未指定config-file | 这是配置错误。 在iPlanet Init指令中未提供配置文件的路径。 |
| 传感器错误3019:vys-log之前未调用vys-cookie。 请检查配置文件 | 必须将vys-cookie指定为每个软件虚拟服务器的first NameTrans指令。 |

